## Cryptography

notes from [this Khan Academy article](https://www.khanacademy.org/computing/computers-and-internet/xcae6f4a7ff015e7d:online-data-security/xcae6f4a7ff015e7d:data-encryption-techniques/a/encryption-decryption-and-code-cracking)

[this one](https://thebestvpn.com/cryptography/)

and Geeks for Geeks on [computer generated random numbers](https://www.howtogeek.com/183051/htg-explains-how-computers-generate-random-numbers/)

### Caeser Cypher (Shift Cypher)

- If you've ever watched Wheel of Fortune, you know the most common letters are R, S, T, N, L, ....and you want to buy an E. Looking at an English language frequency graph supports what contestants have come to learn.

- The Caeser Cypher is a simple alphabet shift where original letters in a message are replaced with the new, shifted letters.  A +5 shift, for example makes A = F, B = G, and so on. (write out the grid) 

- Once you find a common pattern...looking for E, the common letters, repeat letters, and short words that follow their English language pattern, you can likely figure out the shift and "unshift" the letters to reveal the original message (the plaintext).

- Thanks to this exploration of the Caesar Cipher, we now understand the three key aspects of data encryption:

    1. Encryption: scrambling the data according to a secret key (in this case, the alphabet shift).

    2. Decryption: recovering the original data from scrambled data by using the secret key.

    3. Code cracking: uncovering the original data without knowing the secret, by using a variety of clever techniques.

- Jefferson used a cylinder cypher (like in the DaVinci code)

- Modern cyphers often use `Polymorphism`, changing itself with each use.  Think of the little black fob used in some Gov't offices.

- Other modern crytography systems:
    1. Hashing: changes a message into an unreadable string of text for the purpose of verifying the message’s contents, not hiding the message itself (MD5, SHA-1, SHA-256)

    2. Symmetric: uses a single key to encrypt a message and then decrypt that message upon delivery (AES or Advanced Encryption Standards)

    3. Asymmetric: uses two different keys for encryption and decryption, as opposed to the single key used in symmetric cryptography

    4. Key Exchange: A key exchange algorithm, like Diffie-Hellman, is used to safely exchange encryption keys with an unknown party (like highlighting a cypher primer in a book)

Four Cryptographic Function:  Authentication, Nonrepudiation, Confidentiality, Integrity

Modern digital cryptography uses VPN, HTTPS, Bitlocker(Windows) or FileVault2(Mac) for hard drive encryption

Computer-generated We generally group the random numbers computers generate into two types, depending on how they’re generated: “True” random numbers and pseudo-random numbers.

    - To generate a “true” random number, the computer measures some type of physical phenomenon that takes place outside of the computer.
