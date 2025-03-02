# DES Implementation

This repository contains a Python implementation of the Data Encryption Standard (DES). The code generates an 8-round key schedule based on bitwise operations and randomization techniques.

## Getting Started

To run this implementation, you can use Google Colab, an online platform for executing Python code in a cloud-based Jupyter Notebook environment.

### Google Colab Link
https://colab.research.google.com/github/manishashetty29/INS-PROGRAM/blob/main/DataEncryptionStandard/DES.ipynb


## How It Works

1. Binary Conversion: The input string is converted into an 8-bit binary representation.
2. Splitting: The binary string is divided into left and right halves.
3. Bitwise Shifting: Each half undergoes left shifts based on predefined values.
4. Key Generation: Randomized bits are selected from the shifted values to generate 8 subkeys.

## Prerequisites

Ensure that you have Python 3 installed or run the code in Google Colab.

## Running the Code

1. Open the provided Google Colab link.
2. Copy and paste the Python script into a new Colab notebook or run the provided notebook directly.
3. Execute the code to generate DES subkeys.

## Output
The script will output 8 different keys generated from the input string, displayed in binary format.



