## Cryptography
**Definition**: Converts data to unitelligible form.

**Q**: If cryptography is combined with compression, what is the right order?\
**A**: We should first compress first. This is because compression typically needs a pattern to reduce the message size; running a message through a crpyt-system will generate a random message that will be uncompressable.

### Cryptography vs Steganography
- Steganography concerns existence. It conceals the very existence of communication. In other words, it hides the secret message in plain sight.

insert 001.png

### Encryption and Decryption
- **Plaintext**: the original message
- **Ciphertext**: a message in the transformed, unrecognized form
- **Encryption**: the process that transforms a plaintext to ciphertext
- **Decryption**: the process that transforms a ciphertext to plaintext
- **Key**: the value that is used to control encryption and decryption

insert 002.png

### Cryptanalysis
**Definition**: The art of defeating cryptsystems to gain access to the real contents of encrypted messages. The difficulty depends on the sophistication of the cryptsystem and the amount of information available to the breaker.


**Ciphertext Only Attacks**: Eve intercepts a set of ciphertexts, and to break the cipher she must analyze patters in the ciphertext which can provide clues about the plaintext and keys.

**Known Plaintext Attacks**: Eve has simples of both the plaintext and the ciphertext, which makes some ciphers easy to break (e.g. mono-aphabetic ciphers).

**Chosen Plaintext Attacks**: Eve has the ability to choose arbitrary plaintexts to be encrypted and obtain the corresponding ciphertexts.

### Perfectly Secure Ciphers
Two requirements:
1. Ciphertext does not reveal any information about which plaintexts are more likely to have produced it.
2. Plaintext does not reveal any information about which ciphertexts are more likely to be produced.

### Computationally Secure Ciphers
Requirements:
1. The cost of breaking the cipher exceeds the value of the encrypted information.\
AND / OR
2. The time required to break tghe cipher exceed the useful lifetime of the information.

### Secret Keys vs. Secret Algorithms
- We can keep algorithms secret, which can achieve better security, but it is often harder to keep secret if used widely.
- We can also publish the algorithms. In this case, the security depends on the secrecy of the keys. Since the algorithm is public, several people can examine the algorithms and discover vulnerabilities that can quickly be assessed.

### Caesar Cipher
Here's an example of a Caesar Cipher where we replace each letter with the one 3 letters down the alphabet:

insert 003.png

### Mono-Alphabetic Ciphers
This is a generalized substitution cipher, which is done by randomly mapping one letter to another.

insert 004.png

There are 26! (approximately 2<sup>88</sup>) different combination possibilities. 

The key must specify the permutation used. How many bits does that take?\
It takes log<sub>2</sub>(26!) = approximately 88 bits.
