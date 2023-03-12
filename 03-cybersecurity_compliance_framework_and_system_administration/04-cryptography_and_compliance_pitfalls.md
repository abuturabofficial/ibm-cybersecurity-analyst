<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**

- [Cryptography Terminology](#cryptography-terminology)
    - [Hash Function](#hash-function)
    - [Digital Signature](#digital-signature)
- [Common Cryptography Pitfalls](#common-cryptography-pitfalls)
    - [Pitfall: Missing Encryption of Data and Communication](#pitfall-missing-encryption-of-data-and-communication)
    - [Pitfall: Missing Encryption of Data and Communication](#pitfall-missing-encryption-of-data-and-communication-1)
    - [Pitfall: Implementing Your Own Crypto](#pitfall-implementing-your-own-crypto)
    - [Pitfall: Relying on Algorithms Being Secret](#pitfall-relying-on-algorithms-being-secret)
    - [Pitfall: Using Hard-coded/Predictable/Weak Keys](#pitfall-using-hard-codedpredictableweak-keys)
    - [Pitfall: Ignoring Encryption Export Regulation Rules](#pitfall-ignoring-encryption-export-regulation-rules)
- [Data Encryption](#data-encryption)
  - [Encryption Data at rest](#encryption-data-at-rest)
      - [Pitfalls and Recommendations](#pitfalls-and-recommendations)
  - [Encryption Data in Use](#encryption-data-in-use)
  - [Encryption Data in Transit](#encryption-data-in-transit)
    - [Pitfalls](#pitfalls)
- [Hashing Considerations](#hashing-considerations)
  - [Hashing](#hashing)
    - [Pitfalls: Using Weak or Obsolete Functions](#pitfalls-using-weak-or-obsolete-functions)
      - [Additional Considerations](#additional-considerations)
    - [Message Authentication Codes (MACs)](#message-authentication-codes-macs)
- [Digital Signatures and Encryption Keys](#digital-signatures-and-encryption-keys)
  - [Digital Signatures](#digital-signatures)
  - [Safeguarding Encryption Keys](#safeguarding-encryption-keys)
    - [Securing KEK](#securing-kek)
- [Impact of Quantum Computing](#impact-of-quantum-computing)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# Cryptography Terminology

- Encryption only provides confidentiality, but no integrity.
- Data can be encrypted
	- At rest
	- In use
	- In transit
- Common types of encryption algorithms
	- Symmetric Key (AES, DES, IDEA, …)
	- Public key (RSA, Elliptic Curve, DH, …)
 ![](images/Pasted%20image%2020230311172541.png)

### Hash Function

Maps data of arbitrary size to data of a fixed size.
- Provides integrity, but not confidentiality
- MD5, SHA-1, SHA-2, SHA-3, and others
- Original data deliberately hard to reconstruct
- Used for integrity checking and sensitive data storage (e.g., passwords)

### Digital Signature

“A mathematical scheme for verifying the authenticity of digital messages and documents.”
- Uses hashing and public key encryption
- ensures authentication, non-repudiation, and integrity.

# Common Cryptography Pitfalls

### Pitfall: Missing Encryption of Data and Communication

- Products handle sensitive business and personal data.
- Data is often the most valuable asset that the business has.
- When you store or transmit it in clear text, it can be easily leaked or stolen.
- In this day and age, there is no excuse for not encrypting data that's stored or transmitted.
- We have the cryptographic technology that is mature, tested, and is available for all environments and programming languages.

**Encrypt all sensitive data you are handling (and also ensure its integrity).**

### Pitfall: Missing Encryption of Data and Communication

- Some products owners that we talk to don't encrypt stored data because “users don't have access to the file system.”
- There are plenty of vulnerabilities out there that may allow exposure of files stored on the file system.
- The physical machine running the application maybe stolen, hard disk can be then accessed directly.

**You have to assume that the files containing sensitive information may be exposed and analyzed.**

### Pitfall: Implementing Your Own Crypto

- Often developers use Base64 encoding, simple xor encoding, and similar obfuscation schemes.
- Also, occasionally we see products implement their own cryptographic algorithms.
**Please don't do that!**

**Schneier's Law:**
> Anyone, from the most clueless amateur to the best cryptographer, can create an algorithm that he himself can't break. It's not even hard. What is hard is creating an algorithm that no one else can break, even after years of analysis.

**Rely on proven cryptography, that was scrutinized by thousands of mathematicians and cryptographers.**

- Follow recommendations of NIST.

### Pitfall: Relying on Algorithms Being Secret

- We sometimes hear dev teams tell us that “the attacker will never know our internal algorithms.”
	- **Bad news** – they can and will be discovered; it's only a question of motivation.
- A whole branch of hacking – **Reverse Engineering** – is devoted to discovering hidden algorithms and data.
- Even if your application is shipped only in compiled form, it can be “decompiled”.
- Attackers may analyze trial/free versions of the product, or get copies on the Dark Web.
- “Security by obscurity” is not a good defense mechanism.
- The contrary is proven true all the time.
	- All algorithms that keep us safe today are open source and very well-studied: AES, RSA, SHA*, ….

**Always assume that your algorithms will be known to the adversary.**

A great guiding rule is Kerckhoffs’s Principle:
> A cryptosystem should be secure even if everything about the system, except the key, is public knowledge.

### Pitfall: Using Hard-coded/Predictable/Weak Keys

- Not safeguarding your keys renders crypto mechanisms useless.
- When the passwords and keys are hard-coded in the product or stored in plaintext in the config file, they can easily be discovered by an attacker.
- An easily guessed key can be found by trying commonly used passwords.
- When keys are generated randomly, they have to be generated from a cryptographically-secure source of randomness, not the regular RNG.

**Rely on hard to guess, randomly generated keys and passwords that are stored securely.**

### Pitfall: Ignoring Encryption Export Regulation Rules

- Encryption is exported controlled.
- All code that…
	- **Contains** encryption (closed or open source).
	- **Calls** encryption algorithms in another library or component.
	- **Directs** encryption functionality in another product.
- … must be classified for export **before** being released.

# Data Encryption

## Encryption Data at rest

- The rule of thumb is to encrypt all sensitive data at rest: in files, config files, databases, backups.
- Symmetric key encryption is most commonly used.
- Follow NIST Guidelines for selecting an appropriate algorithm – currently it’s AES (with CBC mode) and Triple DES.

#### Pitfalls and Recommendations

- **Some algorithms are outdated and no longer considered secure** – phase them out
	- examples include DES, RC4, and others.
- **Using hard-coded/easily guessed/insufficiently random keys** – Select cryptographically-random keys, don’t reuse keys for different installations.
- **Storing keys in clear text in proximity to data they protect** (“key under the doormat”)
	- stores keys in secure key stores.
- **Using initialization vectors (IVs) incorrectly**.
	- Use a new random IV every time.
- Preferable to select the biggest key size you can handle (but watch out for export restrictions).

## Encryption Data in Use

- Unfortunately, a rarely-followed practice.
- Important, nonetheless, memory could be leaked by an attacker.
	- A famous 2014 Heartbleed defect leaked memory of processes that used OpenSSL.
- The idea is to keep data encrypted up until it must be used.
- Decrypt data as needed, and then promptly erase it in memory after use.
- Keep all sensitive data (data, keys, passwords) encrypted except a brief moment of use.
- Consider Homomorphic encryption if it can be applied to your application.

## Encryption Data in Transit

- In this day and age, there is **no excuse for communicating in cleartext**.
- There is an industry consensus about it; Firefox and Chrome now mark HTTP sites as insecure.
- Attackers can easily snoop on unprotected communication.
- All communications (not just HTTP) should be encrypted, including: RPCs, database connections, and others.
- TLS/SSL is the most commonly used protocol.
	- Public key crypto (e.g., RSA, DH) for authentication and key exchange; Symmetric Key crypto to encrypt the data.
	- Server Digital Certificate references certificate authority (CA) and the public key.
- Sometimes just symmetric key encryption is employed (but requires pre-sharing of keys).

### Pitfalls

- **Using self-signed certificates**
	- Less problematic for internal communications, but still dangerous.
	- Use properly generated certificates verified by established CA.
- **Accepting arbitrary certificates**
	- Attacker can issue their own certificate and snoop on communications (MitM attacks).
	- Don’t accept arbitrary certificates without verification.
- **Not using certificate pinning**
	- Attacker may present a properly generated certificate and still snoop on communications.
	- Certificate pinning can help – a presented certificate is checked against a set of expected certificates.
- **Using outdated versions of the protocol or insecure cipher suites**
	- Old versions of SSL/TLS are vulnerable. (DROWN, POODLE, BEAST, CRIME, BREACH, and other attacks)
	- **TLS v1.1-v1.3 are safe to use (v1.2 is recommended, with v1.3 coming)**
	- Review your TLS support; there are tools that can help you:
		- Nessus, Qualys SSL Server Test (external only), sslscan, sslyze.
- **Allowing TLS downgrade to insecure versions, or even to HTTP**
	- Lock down the versions of TLS that you support and don’t allow downgrade; disable HTTP support altogether.
- **Not safeguarding private keys**
	- Don’t share private keys between different customers, store them in secure key stores.
- **Consider implementing Forward Secrecy**
	- Some cipher suites protect past sessions against future compromises of secret keys or passwords.
- **Don’t use compression under TLS**
	- CRIME/BREACH attacks showed that using compression with TLS for changing resources may lead to sensitive data exposure.
- **Implement HTTP Strict Transport Security (HSTS)**
	- Implement Strict-Transport-Security header on all communications.
- **Stay informed of latest security news**
	- A protocol or cipher suite that is secure today may be broken in the future.

# Hashing Considerations

## Hashing

- Hashing is used for a variety of purposes:
	- Validating passwords (salted hashes)
	- Verifying data/code integrity (messages authentication codes and keyed hashes)
	- Verifying data/code integrity and authenticity (digital signatures)
- Use secure hash functions (follow NIST recommendations):
	- SHA-2 (SHA-256, SHA-384, SHA-512, etc.) and SHA-3

### Pitfalls: Using Weak or Obsolete Functions

- There are obsolete and broken functions that we still frequently see in the code – **phase them out**.
- Hash functions for which it is practical to generate collisions (two or more different inputs that correspond to the same hash value) are not considered robust.
- **MD5** has been known to be broken for more than 10 years, collisions are fairly easily generated.
- **SHA-1** was recently proven to be unreliable.
- **Using predictable plaintext**
	- Not quite a cryptography problem, but when the plaintext is predictable it can be discovered through brute forcing.
- **Using unsalted hashes when validating passwords**
	- Even for large issue spaces, rainbow tables can be used to crack hashes.
	- When salt is added to the plaintext, the resulting hash is completely different, and rainbow tables will no longer help.

#### Additional Considerations

- Use key stretching functions (e.g., PBKDF2) with numerous iterations.
	- Key stretching functions are deliberately slow (controlled by number of iterations) in order to make brute forcing attacks impractical, both online and offline (aim 750ms to complete the operation).
- Future-proof your hashes – include an algorithm identifier, so you can seamlessly upgrade in the future if the current algorithm becomes obsolete.

### Message Authentication Codes (MACs)

- MACs confirm that the data block came from the stated sender and hasn’t been changed.
- Hash-based MACs (HMACs) are based on crypto hash functions (e.g., HMAC-SHA256 or HMAC-SHA3).
- They generate a hash of the message with the help of the secret key.
- If the key isn’t known, the attacker can’t alter the message and be able to generate another valid HMAC.
- HMACs help when data may be maliciously altered while under temporary attacker’s control (e.g., cookies, or transmitted messages).
- Even encrypted data should be protected by HMACs (to avoid bit-flipping attacks).

![](images/Pasted%20image%2020230312120420.png)

# Digital Signatures and Encryption Keys

## Digital Signatures

- Digital signatures ensure that messages and documents come from an authentic source and were not maliciously modified in transit.
- Some recommended uses of digital signatures include verifying integrity of:
	- Data exchanged between nodes in the product.
	- Code transmitted over network for execution at client side (e.g., JavaScript).
	- Service and fix packs installed by customer.
	- Data temporarily saved to customer machine (e.g., backups).
- Digital signatures must be verified to be useful.

## Safeguarding Encryption Keys

- Encryption is futile if the encryption keys aren’t safeguarded.
- **Don’t store** them in your code, in plaintext config files, in databases.
- Proper way to store keys and certificates is in secure cryptographic storage, e.g, keystores
	- For examples, in Java you can use Java Key Store (JKS).
- **There is a tricky problem of securing key encrypting key (KEK)**.
	- This is a key that is used to encrypt the keystore. But how do we secure it?

### Securing KEK

- Use hardware secure modules (HSM).
- Use Virtual HSM (Unbound vHSM).
- Derive KEK for user-entered password.
	- An example of this can be seen in Symantec Encryption Desktop Software, securing our laptops.
- Derive KEK from data unique to the machine the product is running on.
	- This could be file system metadata (random file names, file timestamps).
	- An attacker that downloads the database or the keystore will not be able to as easily obtain this information.

# Impact of Quantum Computing

- Quantum computing is computing using quantum-mechanical phenomena. Quantum computing may negatively affect cryptographic algorithms we employ today.
- We are still 10–15 years away from quantum computing having an effect on cryptography.
- **Risks to existing cryptography:**
	- Symmetric encryption (e.g., AES) will be **weakened**.
		- To maintain current levels of security, double the encryption key size (e.g., got from 128-bit to 256-bit keys).
	- Public key encryption that relies on prime number factorization (e.g., RSA used in SSL/TLS, blockchain, digital signatures) will be **broken**.
		- Plan on switching to quantum-resistant algorithms – e.g., Lattice-based Cryptography, Homomorphic Encryption.
- Attacker can capture conversations now and decrypt them when quantum computing becomes available.
- **General Good practice** – make your encryption, hash, signing algorithms “replaceable”, so that you could exchange them for something more robust if a weakness is discovered.