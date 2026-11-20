# Lab06 – Secrets Management using GPG

## Objective
Understand the risks of storing secrets in plaintext and learn to protect sensitive information using GPG symmetric and asymmetric encryption.

## 1. Creating Dummy Secrets
Created a temporary file named `secrets.env` containing dummy API key and database password values.

## 2. Symmetric Encryption
Encrypted the file using GPG symmetric encryption:

`gpg -c secrets.env`

This generated `secrets.env.gpg`. GPG used a passphrase and AES encryption to protect the contents.

## 3. Symmetric Decryption
Decrypted the encrypted file using:

`gpg -d secrets.env.gpg`

The dummy values were successfully recovered by entering the passphrase.

## 4. Asymmetric Encryption
Encrypted the plaintext file using my GPG public key:

`gpg -e -r rishalbecker5@gmail.com secrets.env`

The encrypted output was saved as `secrets_asymmetric.gpg`.

## 5. Asymmetric Decryption
Decrypted the asymmetric file using:

`gpg -d secrets_asymmetric.gpg`

The original dummy values were successfully recovered using my private key.

## 6. Removing Plaintext
Removed the plaintext file:

`rm secrets.env`

Only the encrypted files remained in the directory.

## 7. Reflection

- **Why should secrets not be stored in source code?** Secrets stored in source code can be exposed through repositories, logs, backups or unauthorized access.
- **Symmetric vs asymmetric encryption:** Symmetric encryption uses the same passphrase/key to encrypt and decrypt. Asymmetric encryption uses a public key to encrypt and a private key to decrypt.
- **What happens if a private key is lost?** Data encrypted for that key may no longer be decryptable, so private keys must be protected and backed up securely.
- **Why is secrets management important?** It reduces the risk of credential exposure and unauthorized access to systems and services.

## Conclusion
Successfully demonstrated GPG symmetric and asymmetric encryption and decryption using dummy secrets. Removed the plaintext file and retained encrypted copies.
