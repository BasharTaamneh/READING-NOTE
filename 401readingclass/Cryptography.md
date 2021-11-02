
# Cryptography

## Readings from [Encryption, decryption, and cracking](https://www.khanacademy.org/computing/computers-and-internet/xcae6f4a7ff015e7d:online-data-security/xcae6f4a7ff015e7d:data-encryption-techniques/a/encryption-decryption-and-code-cracking)


### Encrypting a message


> Imagine Caesar wants to send this message:

> `SECRET MEETING AT THE PALACE`.

> Here's what that might look like encrypted:

> `YKIXKZ SKKZOTM GZ ZNK VGRGIK`.

> The Caesar Cipher is a simple substitution cipher which replaces each original letter with a different letter in the alphabet by shifting the alphabet by a certain amount.

> To make the encrypted message above, shift the alphabet by 6.


### Decrypting a message

<br>

> According to historical records, Caesar always used a shift of 3.

> As long as his message recipient knew the shift amount, it was trivial for them to decode the message.

<br>

### Cracking the cipher

<br>

> There are three main techniques he could use: `frequency analysis`, `known plaintext`, and `brute force`.

<br>

- Frequency analysis
 
> Human languages tend to use some letters more than others.
 
> For example, "E" is the most popular letter in the English language.
 
> We can analyze the frequency of the characters in the message and identify the most likely "E" and narrow down the possible shift amounts based on that.

<br>

- Known plaintext

> Another term for the original unencrypted message is plaintext. If the enemy already knew some part of the plaintext, it will be easier for them to crack the rest of the encrypted version.

> For example, messages tend to start with similar beginnings. In WWII, encrypted German messages always started with a weather forecast, which ultimately made them easier for British mathematician Alan Turing to crack.

<br>

- Brute force

> There are only 25 possible shifts (not 26 — why not?).

> The enemy could take some time to try out each of them and find one that yielded a sensible message.

> They wouldn't even need to try the shifts on the entire message, just the first word or two.

<br>

### Encryption, decryption, and cracking

<br>

> `Encryption`: scrambling the data according to a secret key (in this case, the alphabet shift).

> `Decryption`: recovering the original data from scrambled data by using the secret key.

> `Code cracking`: uncovering the original data without knowing the secret, by using a variety of clever techniques.

<br>

## Readings from [Caesar cipher](https://en.wikipedia.org/wiki/Caesar_cipher)

<br>

### Encrypting a message

<br>

> In cryptography, a Caesar cipher, also known as Caesar's cipher, the shift cipher, Caesar's code or Caesar shift, is one of the simplest and most widely known encryption techniques.

> It is a type of substitution cipher in which each letter in the plaintext is replaced by a letter some fixed number of positions down the alphabet.

> For example, with a left shift of 3, D would be replaced by A, E would become B, and so on. The method is named after Julius Caesar, who used it in his private correspondence.

<br>

> The encryption can also be represented using modular arithmetic by first transforming the letters into numbers, according to the scheme, `A → 0, B → 1, ..., Z → 25`.

> Encryption of a letter x by a shift n can be described mathematically as: `En(x)=(x+n) mod {26}`.

> Decryption is performed similarly, `Dn(x)=(x-n) mod 26`.

<br>

![](https://cdn.ttgtmedia.com/rms/onlineImages/security_cissp_cryptography_mobile.jpg)

![](https://lh3.googleusercontent.com/proxy/aqidFduJjNlv4B5bV7gVd0gHmIKDZe8s04Ihsj5fiBK4txrWMAJwbhklj16p-W2BS18n6K_KBZs1zS567DEFAhQ5EWEZhZsiyg)