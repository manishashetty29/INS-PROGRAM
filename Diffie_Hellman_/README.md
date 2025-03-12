# Diffie-Hellman Key


This repository contains a Python implementation of the Diffie-Hellman key exchange algorithm, which allows two parties to securely generate a shared secret key over an insecure channel.

## Overview
The Diffie-Hellman algorithm is a cryptographic method for securely exchanging cryptographic keys. It relies on modular exponentiation and the difficulty of the discrete logarithm problem to ensure security.

## How the Code Works

### 1. **User Input:**
   - The user inputs a prime number `q`, which serves as the modulus.
   - The user provides a primitive root `a` of `q`.
   - Each user selects a private key (`Xa` for user A and `Xb` for user B).

### 2. **Public Key Calculation:**
   - User A computes their public key: `Ya = (a^Xa) % q`.
   - User B computes their public key: `Yb = (a^Xb) % q`.

### 3. **Exchange of Public Keys:**
   - Both users exchange their public keys.

### 4. **Shared Key Computation:**
   - User A computes the shared key: `Ka = (Yb^Xa) % q`.
   - User B computes the shared key: `Kb = (Ya^Xb) % q`.
   - Since `Ka` and `Kb` are mathematically equivalent, both parties obtain the same secret key.

## Python Code
```python
import math

q = int(input("Enter the prime number: "))
a = int(input("Enter the primitive root: "))
Xa = int(input("Enter the private key of A: "))
Xb = int(input("Enter the private key of B: "))

Ya = math.pow(a, Xa) % q
Yb = math.pow(a, Xb) % q

print("Public key of A:", Ya)
print("Public key of B:", Yb)

Ka = math.pow(Yb, Xa) % q
Kb = math.pow(Ya, Xb) % q

print("Shared key for A:", Ka)
print("Shared key for B:", Kb)
```

## How to Run
1. Clone the repository:
   ```bash
   git clone <your-repo-url>
   cd <your-repo-folder>
   ```
2. Run the Python script:
   ```bash
   python diffie_helman.py
   ```
3. Follow the prompts to enter the prime number, primitive root, and private keys.
4. Observe the computed public and shared keys.

## Google Colab Link
You can run this code in Google Colab using the following link:
[Google Colab Notebook](YOUR_COLAB_LINK_HERE)


