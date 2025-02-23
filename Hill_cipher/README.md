# Hill Cipher 

This repository contains a simple Python program that implements the Hill Cipher encryption algorithm using NumPy. The code is designed to be executed in Google Colab and can also be cloned from GitHub for local execution.

 About the Code

The Hill Cipher is a polygraphic substitution cipher that uses matrix multiplication for encryption. This program takes a plaintext input and encrypts it using a predefined key matrix.

 Logic of the Code

## Encryption:

The hill_cipher_encrpt() function takes plaintext and a key matrix as input.

The plaintext is converted into numerical values (A=0, B=1, ..., Z=25).

It ensures the plaintext length is a multiple of the key matrix size by appending 'X' if necessary.

The numerical values are grouped into blocks, multiplied with the key matrix, and taken modulo 26.

The transformed numerical values are converted back into letters to produce the encrypted text.

 Example Execution

Enter the plaintext: HELLO
Encrypted Text: ZEBBW
## How to Run the Code

Option 1: Open in Google Colab

To directly open the notebook in Google Colab, click the button below:
### https://colab.research.google.com/github/manishashetty29/INS-PROGRAM/blob/main/Hill_cipher/hill_cipher.ipynb



Option 2: Clone the Repository and Run Locally

Clone the repository using Git:

git clone https://github.com/manishashetty29/INS-PROGRAM.git

Navigate to the project directory:

cd Hill_cipher

Run the script in Python:

python hill_cipher.ipynb

## Code Explanation

import numpy as np

def hill_cipher_encrpt(plaintext, key_matrix):
    n = len(key_matrix)
    plaintext = plaintext.upper().replace(" ", "")
    if len(plaintext) % n != 0:
        plaintext += "X" * (n - len(plaintext) % n)
    
    plaintext_vector = [ord(char) - ord('A') for char in plaintext]
    ciphertext = ""
    
    for i in range(0, len(plaintext_vector), n):
        block = plaintext_vector[i:i+n]
        result = np.dot(key_matrix, block) % 26
        ciphertext += "".join(chr(num + ord('A')) for num in result)
    
    return ciphertext

plaintext = input("Enter the plaintext: ")
key_matrix = np.array([[6, 24, 1], [13, 15, 10], [20, 17, 15]])
print("Encrypted:", hill_cipher_encrpt(plaintext, key_matrix))

key_matrix: A predefined 3x3 key matrix for encryption.

plaintext: User input, which is cleaned and processed.

hill_cipher_encrpt(): Encrypts the text using matrix multiplication.

The encrypted text is displayed as output.

## Features

1) Implements Hill Cipher encryption using matrix operations
2) Automatically pads plaintext if its length is not a multiple of the key matrix size
3) Works on Google Colab & locally
4) Simple and easy-to-run script

