subject:: [[subject/math]]
parents:: [[cryptography]]

- Fascinating applications of prime numbers and modulus to provide an unparalleled layer of security in otherwise dangerous interactions.
- *Asymmetric cryptography*: encrypt with one key and decrypt with the other.
- **Public key encryption**
	- Why: To send data over a network without letting others read it.
	- How: Encrypt data using the public key so only the entity with access to the private key can read the data. The ensures the data is "secret".
	- Analogy: A public key is like a "custom public lock" that can be attached to a message such that only the entity with access to the corresponding private key can unlock the message.
- **Public key signatures**
	- Why: To ensure that information is sent by the intended entity and that the information hasn't been modified in transit.
	- How it works: Encrypt hash of file using the private key to create a "signature". Recipient decrypts signature using public key. The decrypted message should match the hash of the corresponding file to ensure that it was the same file sent by the original entity.
	- Analogy: In this case, the private key serves as a "custom private lock" that can only be unlocked by the public key. If the public key can successfully unlock the message, it verifies that the correct private key locked the message. Furthermore, the message itself corresponds to unique* number identifying the original file, so if the original file does not match that unique number, the original file must have been modified in some way according to the original entity.
	  *ignoring hash collisions.
- Each private key has an associated public key. It's possible to generate the public key from the private key, but you cannot generate the private key from the public key.
- Reflections
	- Everything relies on Rather than try to steal the private keys, it might be easier for malicious actors to simply inject incorrect public keys for which they have the correspoding