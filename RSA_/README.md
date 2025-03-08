# RSA Encryption and Decryption

This repository contains a simple implementation of the RSA encryption and decryption algorithm using Python. The script allows users to input two prime numbers and a message, then encrypts and decrypts the message using the RSA technique.

## How the Code Works

### 1. **Greatest Common Divisor Function**
```python
def gcd(a, b):
    while b:
        a, b = b, a % b
    return a
```
- This function calculates the greatest common divisor (GCD) of two numbers using the Euclidean algorithm.
- It is used to find a value `e` that is coprime with `phi(n)`.

### 2. **RSA Function**
```python
def RSA(p, q, msg):
```
- The function takes three inputs: two prime numbers (`p`, `q`) and the message (`msg`).

#### **Step 1: Compute `n` and `phi(n)`**
```python
n = p * q
phi = (p - 1) * (q - 1)
```
- `n` is the product of the two prime numbers, used as the modulus for encryption and decryption.
- `phi(n)` is the totient function, which represents the count of numbers less than `n` that are coprime to `n`.

#### **Step 2: Find Public Key Exponent (`e`)**
```python
for i in range(2, phi):
    if gcd(i, phi) == 1:
        e = i
        break
```
- The public exponent `e` is chosen such that it is coprime with `phi(n)`.
- The first integer `i` that satisfies `gcd(i, phi) == 1` is selected.

#### **Step 3: Compute Private Key Exponent (`d`)**
```python
j = 0
while True:
    if (j * e % phi) == 1:
        d = j
        break
    j += 1
```
- The private key exponent `d` is computed as the modular inverse of `e` with respect to `phi(n)`.
- It satisfies the equation `(d * e) % phi(n) = 1`.

#### **Step 4: Encrypt and Decrypt the Message**
```python
c = (msg ** e) % n
print("Encrypted message:", c)
d = (c ** d) % n
print("Decrypted message:", d)
```
- The message `msg` is encrypted using `c = (msg^e) % n`.
- The encrypted message `c` is decrypted using `d = (c^d) % n`.

### 3. **User Input and Execution**
```python
p = int(input("Enter the value of p:"))
q = int(input("Enter the value of q:"))
msg = int(input("Enter the message:"))
RSA(p, q, msg)
```
- The user inputs two prime numbers and a message, which is then passed to the `RSA()` function.

## How to Clone and Run the Code

### Clone the Repository
To get a local copy of the code, run the following command:
```sh
git clone <your-repository-url>
```
Replace git clone <your-repository-url> with the actual GitHub repository link.

### Open in Google Colab
This repository includes an option to open the script directly in Google Colab. Click the following link to run the code in Colab:

### https://colab.research.google.com/github/manishashetty29/INS-PROGRAM/blob/main/RSA_/RSA.ipynb

### Run the Code
After cloning the repository, navigate to the project directory and execute:
```sh
python RSA.ipynb
```

## Requirements
- Python 3.x
- Google Colab (Optional for online execution)

## Conclusion
This project demonstrates a simple RSA encryption and decryption implementation in Python. The script finds public and private keys, encrypts a message, and then decrypts it back to the original form.

