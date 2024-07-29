subject:: [[subject/math]]

- Each private key has an associated public key. It's possible to generate the public key from the private key, but you cannot generate the private key from the public key.
- Asymmetric cryptography: encrypt with one key and decrypt with the other.
- A couple uses are public key encryption and public key signatures.
- Public key encryption: is when you encrypt data using the public key so only the entity with access to the private key can read the data. The ensures the data is "secret".
- Public key signatures: Encrypt hash of file using the private key to create a "signature". Recipient decrypts signature using public key. The decrypted message should match the hash of the corresponding file to ensure that it was the same file sent by the original entity.