# Secure Password Generator

## Introduction

The Secure Password Generator is a Python script that creates strong, encrypted passwords for secure logins. It uses a combination of letters, numbers, and special characters to generate complex passwords that are difficult to crack. Additionally, it employs cryptographic techniques to encrypt these passwords, which can then be safely stored or used as needed.

## Features

- **Customizable Password Count and Length**: Users can specify the number of passwords and their lengths.
- **Strong Encryption**: Uses Fernet symmetric encryption to securely encrypt and decrypt passwords.
- **Secure Randomness**: Leverages the `secrets` module for cryptographically strong random number generation.
- **Complex Passwords**: Includes a mix of ASCII letters, digits, and punctuation for password complexity.
- **Key Derivation**: Employs PBKDF2HMAC with a SHA-256 hash function to derive encryption keys from a user-provided passphrase and a salt.

## Prerequisites

- Python 3.6 or higher.
- `cryptography` library installed (install via `pip install cryptography`).

## Usage

1. **Run the Script**: Start the program by running `PasswordGenerator.py` in your Python environment.
   
2. **Password Count**: Enter the number of passwords you want to generate when prompted.

3. **Password Length**: Specify the length for each password, ensuring it does not exceed the set maximum length for security and usability.

4. **Secure Passphrase**: Input a secure passphrase that will be used to encrypt your passwords. Remember this passphrase, as you will need it to decrypt the passwords later.

5. **Encryption and Salt**: The program will output encrypted passwords and a salt value. Store these securely.

## Security Considerations

- **Passphrase Security**: The passphrase should be kept secure and private, as it is crucial for decrypting the passwords.
- **Salt Storage**: The salt used for key derivation is unique and must be saved to decrypt the passwords in the future.
- **Encrypted Passwords**: Encrypted passwords are output as base64-encoded strings, which need to be stored securely to prevent unauthorized access.

## FAQs

**Q: Why encrypt passwords?**
A: Encryption protects the passwords in case the storage medium is compromised. Only someone with the key (derived from the passphrase and salt) can decrypt and use them.

**Q: What is a salt in cryptography?**
A: A salt is random data that is used as an additional input to a one-way function that hashes a password or passphrase. The salt is used to prevent dictionary attacks and rainbow table attacks.

**Q: Can I use longer passwords for better security?**
A: Yes, the script allows for passwords up to a specified maximum length. Longer passwords are generally more secure.

**Q: How do I use the generated passwords?**
A: You can use the generated passwords by decrypting them with the script's decryption function and the correct passphrase and salt.

## Troubleshooting

- **Invalid Characters in Passphrase**: Ensure that the passphrase contains only characters that can be encoded properly.
- **Incorrect Salt or Passphrase**: Without the correct salt or passphrase, the decryption process will fail.
- **Module Not Found Errors**: Make sure all required Python modules are installed.

For further assistance or to report bugs, please reach out to the repository maintainers or open an issue on the project's issue tracker.
