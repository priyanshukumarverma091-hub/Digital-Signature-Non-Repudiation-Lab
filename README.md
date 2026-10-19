# Digital Signature and Non-Repudiation Lab

A Python-based cybersecurity project demonstrating RSA digital signatures, message integrity verification, and tampering detection using public-key cryptography.

## Overview

Digital signatures are a fundamental component of modern cybersecurity. They help verify the authenticity and integrity of digital messages and can provide evidence supporting non-repudiation.

This project implements a simple digital-signature workflow using RSA cryptography, RSA-PSS padding, and the SHA-256 hash function. It generates a public-private key pair, signs a message using the private key, and verifies the signature using the corresponding public key.

The implementation also demonstrates message tampering by modifying the original message and attempting to verify it against the original signature.

## Objectives

* Understand the fundamentals of public-key cryptography.
* Generate an RSA public-private key pair.
* Create digital signatures using a private key.
* Verify digital signatures using a public key.
* Detect unauthorized modifications to signed messages.
* Understand the relationship between digital signatures, integrity, authentication, and non-repudiation.

## Technologies Used

| Component             | Technology                               |
| --------------------- | ---------------------------------------- |
| Programming Language  | Python                                   |
| Cryptographic Library | `cryptography`                           |
| Asymmetric Algorithm  | RSA                                      |
| Key Size              | 2048 bits                                |
| Signature Scheme      | RSA-PSS                                  |
| Hash Function         | SHA-256                                  |
| Execution Environment | Google Colab or Local Python Environment |

## System Workflow

The application follows these steps:

1. Generate an RSA public-private key pair.
2. Create an original message.
3. Generate a digital signature using the private key.
4. Verify the original message using the public key.
5. Modify the original message to simulate tampering.
6. Attempt to verify the modified message using the original signature.
7. Report the verification results.

### Workflow Diagram

```text
                 Original Message
                        |
                        v
                 RSA Key Generation
                        |
                        v
                Digital Signature
                 Using Private Key
                        |
                        v
               Signature Verification
                 Using Public Key
                        |
                +-------+-------+
                |               |
                v               v
        Original Message    Modified Message
                |               |
                v               v
        Verification Pass   Verification Fails
```

## Installation

### Option 1: Google Colab

1. Open [Google Colab](https://colab.research.google.com/).

2. Create a new notebook.

3. Install the required dependency:

   ```python
   !pip install cryptography
   ```

4. Add the project implementation to a new code cell.

5. Execute the cell and inspect the verification results.

### Option 2: Local Environment

**Prerequisites**

* Python 3.9 or later
* pip package manager

Install the required library:

```bash
pip install cryptography
```

Save the Python implementation as `digital_signature.py` and execute it:

```bash
python digital_signature.py
```

## Expected Results

| Test Case                     | Expected Outcome  |
| ----------------------------- | ----------------- |
| RSA key generation            | Successful        |
| Digital signature creation    | Successful        |
| Original message verification | Valid signature   |
| Modified message verification | Invalid signature |
| Message tampering detection   | Detected          |

### Sample Output

```text
RSA Key Pair Generated Successfully!
Digital Signature Created Successfully!

VERIFYING ORIGINAL MESSAGE
RESULT: SIGNATURE VALID
Message integrity check: PASSED

TAMPERING TEST
Modified Message: Approve payment of Rs. 50000
RESULT: SIGNATURE INVALID
Message integrity check: FAILED

LAB COMPLETED SUCCESSFULLY
```

The output illustrates that the original message passes signature verification, while the modified message fails verification against the original signature.

## Core Cybersecurity Concepts

### 1. Public-Key Cryptography

Public-key cryptography uses a mathematically related pair of keys:

* **Private key:** Used to generate digital signatures and must remain confidential.
* **Public key:** Used to verify digital signatures and can be distributed to other parties.

### 2. Digital Signatures

A digital signature allows a recipient to verify that a signature corresponds to a particular message and public key.

In this implementation, RSA-PSS is used as the signature scheme, with SHA-256 as the hash function.

### 3. Message Integrity

Integrity ensures that modifications to a message can be detected.

When the original message is changed, its existing signature no longer verifies successfully against the modified content.

### 4. Authentication

Signature verification establishes that the signature is mathematically valid for the message and the public key used for verification.

To authenticate a real-world signer, the public key must also be reliably associated with that person's or organization's identity.

### 5. Non-Repudiation

Non-repudiation involves providing reliable evidence that supports the origin or occurrence of a digitally signed action.

Digital signatures can contribute to non-repudiation, but a valid signature alone does not establish who controlled the private key or satisfy every legal or operational requirement.

Reliable identity verification, private-key protection, and appropriate supporting records are also important.

## Security Considerations

* Protect private keys against unauthorized access.
* Verify public-key ownership before relying on a signature as proof of identity.
* Use secure key-storage mechanisms in production environments.
* Preserve relevant audit records when implementing real-world signing workflows.
* Remember that digital signatures provide integrity and authenticity properties, not message confidentiality.
* Do not use this educational implementation as a production payment-approval or identity-verification system.

The current implementation generates a new RSA key pair each time it runs. Consequently, the generated keys are suitable for demonstration rather than persistent identity verification.

## Limitations

This project is a proof of concept designed to demonstrate cryptographic fundamentals.

It does not implement:

* Persistent key management.
* Certificate-based identity verification.
* Trusted timestamping.
* Secure audit-log storage.
* Production-grade identity or authorization controls.

These capabilities would be necessary considerations for a more complete digital-signature system.

## Future Enhancements

Potential improvements include:

* Exporting and importing public keys.
* Signing and verifying files.
* Persisting signatures for subsequent verification.
* Implementing certificate-based public-key verification.
* Adding trusted timestamps and audit logs.
* Developing a web interface for document-signature verification.
* Generating detailed reports for successful and failed verification attempts.

## Learning Outcomes

Upon completing this project, learners should be able to:

* Explain the purpose of digital signatures.
* Distinguish between public and private keys.
* Implement RSA-based signing and verification in Python.
* Demonstrate message-tampering detection.
* Explain how digital signatures support integrity, authentication, and non-repudiation.

## Disclaimer

This project is intended for educational purposes and authorized cybersecurity training. It is not a production-grade cryptographic or identity-verification system.

## Author

**Priyanshu Kumar Verma**

B.Tech Computer Science and Engineering

Areas of Interest: Artificial Intelligence, Machine Learning, Cybersecurity, and Research.
