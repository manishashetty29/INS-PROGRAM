# Hill Cipher 
Encryption and Decryption

This repository contains a Python implementation of the **Hill Cipher** encryption and decryption algorithm using NumPy. The program encrypts a plaintext message using a **3x3 key matrix** and then decrypts it back to the original text.

## How the Code Works

### Encryption Process:
1. Convert the plaintext to uppercase and remove spaces.
2. Ensure the plaintext length is a multiple of the key matrix size by padding with 'X' if necessary.
3. Convert the characters to numerical values (A=0, B=1, ..., Z=25).
4. Break the plaintext into blocks of size `n` (size of the key matrix).
5. Multiply each block with the key matrix and take modulo 26.
6. Convert the resulting numbers back to characters to get the ciphertext.

### Decryption Process:
1. Compute the determinant of the key matrix.
2. Find the modular inverse of the determinant (mod 26).
3. Compute the inverse of the key matrix in modulo 26.
4. Convert the ciphertext into numerical values.
5. Multiply each block with the inverse key matrix and take modulo 26.
6. Convert the resulting numbers back to characters.
7. Remove any padding 'X' added during encryption.

## Installation and Execution

### Cloning the Repository
To get the code, clone this repository using the following command:
```sh
 git clone https://github.com/manishashetty29/INS-PROGRAM.git
```

### Running the Code in Google Colab
1. Open the repository on GitHub.
2. Click on the **"Open in Colab"** button to directly open the script in Google Colab.
3. Run the script by clicking on **Runtime > Run all** or executing each cell individually.
4. Enter the plaintext when prompted.
5. The script will display the encrypted and decrypted text.

Alternatively, you can open Google Colab manually and run the following command to access the script:
```sh
git clone https://github.com/manishashetty29/INS-PROGRAM.git
cd INS-PROGRAM
python hill_cipher.ipynb
```
link for colab

### Example Usage
#### Input:
```
Enter text: HELLO
```
#### Output:
```
Encrypted: ZEBBWX
Decrypted: HELLO
```
(Note: Padding 'X' is added if needed.)

## Requirements
This script runs on **Python 3** and requires **NumPy**. These are pre-installed in Google Colab. If running locally, install NumPy using:
```sh
pip install numpy
```

## Contributing
Feel free to fork the repository, submit issues, or contribute improvements.




