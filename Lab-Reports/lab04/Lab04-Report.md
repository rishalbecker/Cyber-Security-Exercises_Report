# Lab04 – GPG: Key Generation, Encryption, and Signing

## Objective
To generate a GPG key pair, export a public key, encrypt and decrypt a file, and digitally sign a message.

## 1. Key Generation
Generated an RSA 4096-bit key pair using GPG.
- Name: Rishal
- Key type: RSA 4096
- Expiration: 1 year

## 2. Public Key Export
Exported the public key in ASCII-armored format to public_key.asc.

## 3. Message Creation
Created message.txt containing a test confidential message.

## 4. Encryption
Encrypted the test message using my own public key. The encrypted file was generated in ASCII-armored format.

## 5. Decryption
Decrypted the encrypted message using my private key. The decrypted output matched the original message.

## 6. Digital Signature
Created a cleartext digital signature using GPG.

## Analysis
Encryption protects confidentiality by allowing only the intended private-key holder to decrypt a message. Digital signatures help verify the identity of the signer and detect changes to the signed message.

The public key can be shared, while the private key must remain protected. If a signed message is modified, signature verification should fail.

## Conclusion
This exercise demonstrated GPG key generation, public-key export, encryption, decryption, and digital signing.
