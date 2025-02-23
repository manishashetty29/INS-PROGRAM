# Feistel Cipher Implementation in Python

## Overview
This repository contains an implementation of a simple Feistel cipher in Python. The program takes an input string and a key, converts them into binary, applies the Feistel encryption rounds, and then decrypts the ciphertext back to the original text. The code has been executed in Google Colab and is available on GitHub for easy access.

## Code Explanation
The implementation follows these steps:

1. **User Input:**
   - The program takes a string (`s`) as input.
   - It also takes a key (`k`) for encryption.

2. **Binary Conversion:**
   - The input string is converted into an 8-bit binary representation.
   - Example: If the input string is `ABC`, the binary conversion would be:
     ```
     A -> 01000001
     B -> 01000010
     C -> 01000011
     ```
   - The key is also converted into an 8-bit binary representation.

3. **Splitting the Data:**
   - The binary string is divided into two halves: `left` and `right`.

4. **First Round of Feistel Cipher:**
   - The right half is added to the binary key.
   - The result is XORed with the left half.
   - The left and right halves are swapped.

5. **Second Round of Feistel Cipher:**
   - The new right half is again added to the binary key.
   - The result is XORed with the new left half.
   - The left and right halves are swapped again.

6. **Ciphertext Generation:**
   - The final encrypted binary string (`cipher`) is created.
   - If the length of the cipher text does not match the original binary input, padding is applied.

7. **Decryption:**
   - The encrypted binary is converted back into characters.
   - The decrypted text is displayed.

## How to Clone the Repository
To use this implementation, clone the repository using the following command:
```sh
git clone https://github.com/manishashetty29/INS-PROGRAM.git
```
Replace `<repository_url>` with the actual URL of your GitHub repository.

## Running the Code
### Option 1: Google Colab
### https://colab.research.google.com/github/manishashetty29/INS-PROGRAM/blob/main/Feistel_Cipher11/Feistel_Cipher11.ipynb

### Option 2: Run Locally
If you prefer running the code on your local machine, follow these steps:
1. Clone the repository.
2. Open a terminal or command prompt in the cloned repository directory.
3. Run the script using Python:
   ```sh
   python feistel_cipher.py
   ```
4. Enter the required input (plaintext and key) when prompted.

## Example Execution
```
Enter a string: HELLO
Enter a key: KEY
Cipher Text: 0101011101010101...
Decrypted Text: HELLO
```

## Notes
1) This is a simplified implementation of the Feistel cipher.
2)The script is for educational purposes and does not include advanced cryptographic security measures.



