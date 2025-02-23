# Hill Cipher 

## Overview
This repository contains a Python implementation of the Hill Cipher encryption and decryption technique using a 2x2 key matrix. The Hill Cipher is a polygraphic substitution cipher based on linear algebra, where plaintext is encrypted using matrix multiplication over modular arithmetic.

This implementation includes:
- **Encryption function** (`hill_cipher_encrypt`) that converts plaintext into ciphertext using matrix multiplication.
- **Decryption function** (`hill_cipher_decrypt`) that retrieves plaintext by computing the modular inverse of the key matrix.
- **Modular inverse function** (`mod_inverse_matrix`) that calculates the modular inverse of a matrix under modulo 26.

## Code Explanation

### 1. Modular Inverse of the Key Matrix
Before decryption, we need the inverse of the key matrix under modulo 26. This is done using the function:
```python
mod_inverse_matrix(matrix, modulus)
```
Steps:
- Compute the determinant of the key matrix.
- Find the modular inverse of the determinant under modulo 26.
- Compute the adjugate matrix.
- Multiply the adjugate matrix by the modular inverse of the determinant, then take modulo 26.

### 2. Encryption Function
```python
hill_cipher_encrypt(plaintext, key_matrix)
```
Steps:
- Convert plaintext to uppercase and remove spaces.
- Convert characters into numerical values (A=0, B=1, ..., Z=25).
- Break plaintext into blocks of size 2 (matching the key matrix size).
- Multiply the plaintext vector by the key matrix and apply modulo 26.
- Convert the numerical values back into characters to form the ciphertext.

### 3. Decryption Function
```python
hill_cipher_decrypt(ciphertext, key_matrix)
```
Steps:
- Compute the modular inverse of the key matrix.
- Convert ciphertext characters into numerical values.
- Break ciphertext into blocks of size 2.
- Multiply each block by the inverse key matrix and apply modulo 26.
- Convert the numerical values back into characters to retrieve plaintext.

## Example Usage
### Given:
Plaintext: `HELP`  
Key Matrix:
```
[[3, 3],
 [2, 5]]
```
**Encryption Output:** `ZEBB`  
**Decryption Output:** `HELP`

## How to Clone and Run the Code
### Clone the Repository
To get the code on your local machine, use the following command:
```sh
git clone https://github.com/yourusername/hill-cipher.git
cd hill-cipher
```

### Run the Code in Google Colab
You can directly open and execute the code in Google Colab by clicking the button below:

### https://colab.research.google.com/github/manishashetty29/INS-PROGRAM/blob/main/Hill_cipher/Hill_cipher.ipynb

### Running in Colab:
1. Click the "Open in Colab" button above.
2. Once Colab opens, click on `Runtime > Run all` to execute the entire notebook.
3. Modify the `plaintext` and `key_matrix` values as needed and re-run the cells.

## Requirements
This code requires Python and NumPy. In Colab, these are pre-installed. If running locally, install NumPy using:
```sh
pip install numpy
```

## License
This project is open-source under the MIT License.

---
Enjoy using the Hill Cipher for encryption and decryption! If you have any issues, feel free to open an issue on GitHub.

