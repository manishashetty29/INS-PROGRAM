# MONOALPHABETIC CIPHER

This repository contains a simple Python program that implements a **substitution cipher** to encrypt and decrypt text. The code is designed to be executed in **Google Colab** and can be cloned from GitHub for local execution.

##  About the Code
This program replaces each letter of the alphabet with another letter based on a predefined mapping (`keys` dictionary). The encrypted text can be reversed to its original form using a reverse mapping (`reverse_key` dictionary).

###  Logic of the Code
- **Encryption**:
  - The `encrypt()` function takes plain text as input and replaces each letter with its corresponding encrypted letter using the `keys` dictionary.
- **Decryption**:
  - The `decipher()` function takes the encrypted text and restores it to the original by using the `reverse_key` dictionary.

###  Example Execution
```
Enter the plain text: hello
Encrypted Text: itssg
Decrypted Text: hello
```

##  How to Run the Code
### Option 1: Open in Google Colab
To directly open the notebook in Google Colab, click the button below:

### https://colab.research.google.com/github/manishashetty29/-Monoalphabetic-cipher/blob/main/Monoalphabetic_cipher.ipynb

### Option 2: Clone the Repository and Run Locally
1. **Clone the repository** using Git:
   ```sh
   git clone https://github.com/manishashetty29/INS-PROGRAM.git
   ```
2. **Navigate to the project directory**:
   ```sh
   cd Monoalphabetic_cipher
   ```
3. **Run the script** in Python:
   ```sh
   python Monoalphabetic cipher.ipynb
   ```

##  Code Explanation
```python
keys = {
    'a': 'q', 'b': 'w', 'c': 'e', 'd': 'r', 'e': 't', 'f': 'y', 'g': 'u', 'h': 'i', 'i': 'o', 'j': 'p',
    'k': 'a', 'l': 's', 'm': 'd', 'n': 'f', 'o': 'g', 'p': 'h', 'q': 'j', 'r': 'k', 's': 'l', 't': 'z',
    'u': 'x', 'v': 'c', 'w': 'v', 'x': 'b', 'y': 'n', 'z': 'm'
}

# Reverse mapping for decryption
reverse_key = {v: k for k, v in keys.items()}
```
- **`keys` dictionary** maps each letter to a different letter for encryption.
- **`reverse_key` dictionary** is generated dynamically by swapping key-value pairs from `keys` to allow decryption.

```python
def encrypt(text):
    text = text.lower()
    return ''.join(keys.get(l, l) for l in text)

def decipher(text):
    text = text.lower()
    return ''.join(reverse_key.get(l, l) for l in text)
```
- **`encrypt(text)`** iterates through the input text, replacing characters based on `keys`.
- **`decipher(text)`** restores the original text using `reverse_key`.

```python
x = input("Enter the plain text: ")
encrypting_text = encrypt(x)
decrypting_text = decipher(encrypting_text)

print("Encrypted Text:", encrypting_text)
print("Decrypted Text:", decrypting_text)
```
- Takes user input.
- Encrypts and then decrypts the text.
- Prints the results.

##  Features
1) Simple substitution cipher logic
2) Encryption and decryption functions
3) Works on Google Colab & locally
4) Easy to clone and run
