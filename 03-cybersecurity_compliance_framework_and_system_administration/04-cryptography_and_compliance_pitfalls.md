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
