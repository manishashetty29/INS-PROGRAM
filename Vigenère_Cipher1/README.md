# Vigenère Cipher 

## Overview
This repository contains an implementation of the **Vigenère Cipher**, a classical encryption technique that uses a keyword to encrypt and decrypt text. The program allows users to input plaintext and a key to generate encrypted text and subsequently decrypt it back to its original form.

## Code Explanation
The code consists of two primary functions:

### 1. `vigenere_encrypt(plaintext, key)`
- This function takes the plaintext input and a keyword.
- It iterates through each character of the plaintext:
  - If the character is alphabetical, it is shifted forward by the corresponding character in the key.
  - Non-alphabetic characters are directly appended to the ciphertext without encryption.
- The encryption formula used:
  ```
  Encrypted Character = (Plaintext Character ASCII - 'A' + Key Character ASCII - 'A') % 26 + 'A'
  ```
- The key cycles through its characters as needed.
- Returns the encrypted ciphertext.

### 2. `vigenere_decrypt(ciphertext, key)`
- This function decrypts the ciphertext using the same keyword.
- It reverses the encryption process by shifting the characters backward:
  ```
  Decrypted Character = (Ciphertext Character ASCII - 'A' - (Key Character ASCII - 'A')) % 26 + 'A'
  ```
- The decrypted text should match the original plaintext.

### User Input
- The program takes user input for plaintext and key.
- It first encrypts the plaintext using the Vigenère cipher.
- Then, it decrypts the ciphertext back to the original plaintext.
- The results are displayed as encrypted and decrypted text.

## How to Run the Code

### Option 1: Run in Google Colab
To run this code in **Google Colab**, click the following link:

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](YOUR_COLAB_LINK_HERE)

This will open the notebook in Colab, where you can execute the code without any local setup.

### Option 2: Clone the Repository
If you want to run the code locally, follow these steps:

#### Step 1: Clone the repository
```bash
  git clone YOUR_GITHUB_REPOSITORY_LINK_HERE
  cd YOUR_REPOSITORY_NAME
```

#### Step 2: Run the script
Execute the Python script using:
```bash
  python vigenere_cipher.py
```

You will be prompted to enter the plaintext and the key.

## Example Execution
**Input:**
```
Enter the plaintext: HELLO
Enter the key: KEY
```

**Output:**
```
Encrypted text: RIJVS
Decrypted text: HELLO
```

## Notes
1)Ensure you enter only alphabetic characters for the key.
2)The code automatically converts all text to uppercase.
3)Non-alphabetic characters remain unchanged in the encryption and decryption process.

