## Key Sizes
Ideally, a key should be selected from a large set to prevent brute force attacks.
- For example, if a key is of size 3 bits, the possible keys are 000, 001, 010, 011, 100, 101, 110, 111. This is not big enough because an attacker can do a brute force search to find the key.

### Secret Key Sizes
If computers increase in power by 40% per year, a key would need 5 more bits per decade to stay secure.
- 40 bits were adequate in the 1970s.
- 56 bits used by DES was adequate in the 1980s.
- 128 bits is adequate now.

## Two Principles of Cipher Design
1. Confusion: Makes the relationship between the plaintext and the ciphertext as complex as possible. Mainly accomplished by substitutions.
2. Diffusion: Spreads the influence of each input bit across many output bits. Mainly accomplished by permutations.

### Exploiting the Principles
The idea is to use multiple, alternating permutations and substitutions. Note that they _must_ alternate because consecutive permuations or consecutive substitutions do not improve security.

![](https://github.com/stinsan/CS-5173-Computer-Security/blob/master/Screenshots/019.PNG)

## Feistel Ciphers
Feistel ciphers serve as a template for designing a block cipher. A major benefit is that encryption and decryption take the same amount of time.
Examples of Feistel ciphers include DES and RC5.

### One Round of Feistel Encryption
1. Break the input block _i_ into a left and right partition, _L<sub>i</sub>_ and _R<sub>i</sub>_, respectively.
2. Copy _R<sub>i</sub>_ to create the left partition of the output, _L<sub>i + 1</sub>_.
3. The right input partition _R<sub>i</sub>_ and a key _K<sub>i</sub>_ are scrambled by a function _f_.
4. To create the right output partition _R<sub>i + 1</sub>_, we calculate _f(R<sub>i</sub> , K<sub>i</sub>)_ ⊕ _L<sub>i</sub>_.

![](https://github.com/stinsan/CS-5173-Computer-Security/blob/master/Screenshots/020.PNG)

### One Round of Feistel Decryption
Just reverse the arrows in the previous figure!

![](https://github.com/stinsan/CS-5173-Computer-Security/blob/master/Screenshots/021.PNG)

### Complete Feistel Encryption
![](https://github.com/stinsan/CS-5173-Computer-Security/blob/master/Screenshots/022.PNG)

### Complete Feistel Decryption
![](https://github.com/stinsan/CS-5173-Computer-Security/blob/master/Screenshots/023.PNG)

### Notes About the Final Swap
- There must be a final swap so that decryption works.
- However, if we swap at the end of every round, the right partition of the input will never get encrypted.
