# Elliptic Curve Diffie-Hellman (ECDH) Key Exchange

This repository contains a Python implementation of Elliptic Curve Diffie-Hellman (ECDH) key exchange using the `tinyec` library. The algorithm enables two parties to securely exchange cryptographic keys over an insecure channel.

## Overview
Elliptic Curve Cryptography (ECC) is a modern approach to public-key cryptography that provides high security with smaller key sizes. In this implementation:
- We use the `brainpoolP256r1` elliptic curve from the `tinyec` library.
- Both sender and receiver generate their private and public keys.
- Encryption keys are derived from public-private key multiplication.

## How the Code Works

### 1. **Install Dependencies and Restart Runtime**
```python
!pip install tinyec
import os
os._exit(0)  # This forces a runtime restart
```
- Installs the `tinyec` library for elliptic curve cryptography.
- Restarts the runtime to ensure proper installation.

### 2. **Import Required Libraries**
```python
import tinyec
from tinyec import registry
import secrets
```
- `tinyec`: Provides elliptic curve operations.
- `registry`: Manages predefined elliptic curves.
- `secrets`: Generates cryptographic random numbers.

### 3. **Select an Elliptic Curve**
```python
curve = registry.get_curve("brainpoolP256r1")
```
- Chooses the `brainpoolP256r1` curve for key generation and encryption.

### 4. **Point Compression Function**
```python
def compress_point(point):
    return hex(point.x) + hex(point.y % 2)[2:]
```
- Converts an elliptic curve point into a compressed hexadecimal format.

### 5. **Encryption Key Generation Function**
```python
def getEnKey(pubKey):
    ciPrivateKey = secrets.randbelow(curve.field.n)
    ciPublicKey = ciPrivateKey * curve.g
    enKey = ciPublicKey * ciPrivateKey
    return (enKey, ciPublicKey)
```
- Generates a random encryption private key.
- Computes the corresponding public key.
- Derives the encryption key by multiplying the encryption private key with the cipher public key.

### 6. **Sender's Key Generation**
```python
senderPrivateKey = secrets.randbelow(curve.field.n)
senderPublicKey = senderPrivateKey * curve.g
```
- Generates a random private key for the sender.
- Computes the corresponding public key.

```python
print("Sender's private key : ", hex(senderPrivateKey))
print("Sender's public key : ", compress_point(senderPublicKey))
```
- Displays the sender’s private and public keys.

### 7. **Sender's Encryption Key Computation**
```python
(enKeySender, ciPublicKeySender) = getEnKey(senderPublicKey)
print("Sender's ciphertext public key : ", compress_point(ciPublicKeySender))
print("Sender's encryption key : ", compress_point(enKeySender))
```
- Computes and prints the sender’s encryption key and ciphertext public key.

### 8. **Receiver's Key Generation**
```python
receiverPrivateKey = secrets.randbelow(curve.field.n)
receiverPublicKey = receiverPrivateKey * curve.g
```
- Generates a random private key for the receiver.
- Computes the corresponding public key.

```python
print("Receiver's private key : ", hex(receiverPrivateKey))
print("Receiver's public key :", compress_point(receiverPublicKey))
```
- Displays the receiver’s private and public keys.

### 9. **Receiver's Encryption Key Computation**
```python
(enKeyReceiver, ciPublicKeyReceiver) = getEnKey(receiverPublicKey)
print("Receiver's ciphertext public key : ", compress_point(ciPublicKeyReceiver))
print("Receiver encryption key : ", compress_point(enKeyReceiver))
```
- Computes and prints the receiver’s encryption key and ciphertext public key.

## How to Run the Code
1. Clone the repository:
   ```bash
   git clone <your-repo-url>
   cd <your-repo-folder>
   ```
2. Run the script in a Jupyter Notebook or Google Colab.
3. Install dependencies:
   ```python
   !pip install tinyec
   ```
4. Restart the runtime (Colab automatically does this after installation).
5. Run the script and observe the generated keys.

## Google Colab Link
To run this code in Google Colab, click the link below:
[Google Colab Notebook](YOUR_COLAB_LINK_HERE)


