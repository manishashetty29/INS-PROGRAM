# CAESER CIPHER


This repository contains a simple Python program that implements a **Caesar Cipher** to encrypt and decrypt text. The code is designed to be executed in **Google Colab** and can be cloned from GitHub for local execution.

##  About the Code
This program shifts each letter in the input text by a given key using the **Caesar Cipher** method. Encryption moves letters forward in the alphabet, while decryption moves them backward.

###  Logic of the Code
- **Encryption**:
  - The `encrypt()` function shifts each letter forward by the key value.
  - It differentiates between uppercase and lowercase letters.
  - Non-alphabetic characters remain unchanged.
- **Decryption**:
  - The `decrypt()` function shifts each letter backward by the key value to restore the original text.

###  Example Execution
```
Enter the encrypt: hello
Enter the key: 3
Cipher text: khoor

Enter the cipher text: khoor
Enter the key: 3
Plain text: hello
```

##  How to Run the Code
### Option 1: Open in Google Colab
To directly open the notebook in Google Colab, click the button below:

###  https://colab.research.google.com/github/manishashetty29/Caeser-cipher/blob/main/caeser_cipher.ipynb

### Option 2: Clone the Repository and Run Locally
1. **Clone the repository** using Git:
   ```sh
   git clone https://github.com/manishashetty29/Caeser-cipher.git
   ```
2. **Navigate to the project directory**:
   ```sh
   cd Caeser-cipher
   ```
3. **Run the script** in Python:
   ```sh
   python caeser-cipher.ipynb
   ```

##  Code Explanation
```python
def encrypt(plain_text, key):
    cipherText = ""
    for char in plain_text:
        if char.isalpha():
            shift_base = ord('A') if char.isupper() else ord('a')
            cipherText += chr((ord(char) - shift_base + key) % 26 + shift_base)
        else:
            cipherText += char
    return cipherText

def decrypt(text, key):
    pText = ""
    for char in text:
        if char.isalpha():
            shift_base = ord('A') if char.isupper() else ord('a')
            pText += chr((ord(char) - shift_base - key) % 26 + shift_base)
        else:
            pText += char
    return pText
```
- **`encrypt(plain_text, key)`** iterates through each character, shifting letters forward.
- **`decrypt(text, key)`** reverses the process, shifting letters backward.
- Non-alphabetic characters remain unchanged.

```python
plain_text=input("Enter the encrypt:")
key=int(input("Enter the key:"))
print("Cipher text:",encrypt(plain_text,key))

text=input("Enter the cipher text:")
key=int(input("Enter the key:"))
print("Plain text:",decrypt(text,key))
```
- Takes user input.
- Encrypts and then decrypts the text.
- Prints the results.

##  Features
1)Simple Caesar Cipher implementation
2) Encryption and decryption functions
3) Works on Google Colab & locally
4) Easy to clone and run
