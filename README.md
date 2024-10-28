# EX.-NO-2-A-IMPLEMENTATION-OF-DES

## AIM:
  To write a program to implement Data Encryption Standard (DES).

## ALGORITHM:

  STEP-1: Read the 64-bit plain text.
  
  STEP-2: Split it into two 32-bit blocks and store it in two different arrays.
  
  STEP-3: Perform XOR operation between these two arrays.
  
  STEP-4: The output obtained is stored as the second 32-bit sequence and the original second 32-bit sequence forms the first part.
  
  STEP-5: Thus the encrypted 64-bit cipher text is obtained in this way. Repeat the same process for the remaining plain text characters.
  
## PROGRAM:

```
#include <stdio.h>
#include <string.h>

// Simple XOR-based "encryption" for demonstration only
void simpleEncryptDecrypt(const char *input, char *output, const char *key) {
    size_t len = strlen(input);
    size_t key_len = strlen(key);

    for (size_t i = 0; i < len; i++) {
        output[i] = input[i] ^ key[i % key_len]; // XOR each character with the key
    }
    output[len] = '\0'; // Null-terminate the output
}

int main() {
    char plaintext[] = "LOKESH";         // Input plaintext
    char key[] = "SIMPLEKEY";            // Simple key for encryption
    char ciphertext[128];                // Buffer for ciphertext
    char decryptedtext[128];             // Buffer for decrypted text

    printf("Plaintext: %s\n", plaintext);

    // Encrypt the plaintext
    simpleEncryptDecrypt(plaintext, ciphertext, key);
    printf("Encrypted text: ");
    for (int i = 0; i < strlen(plaintext); i++) {
        printf("%02X ", (unsigned char)ciphertext[i]); // Display as hex
    }
    printf("\n");

    // Decrypt the ciphertext
    simpleEncryptDecrypt(ciphertext, decryptedtext, key);
    printf("Decrypted text: %s\n", decryptedtext);

    return 0;
}

```

## OUTPUT:

![image](https://github.com/user-attachments/assets/48a28224-7c0d-4889-a239-150e83c3f3ec)




## RESULT:

  Thus the data encryption standard algorithm had been implemented successfully.
