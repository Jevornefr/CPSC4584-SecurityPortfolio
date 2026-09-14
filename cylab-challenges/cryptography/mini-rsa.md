# Mini RSA

## Challenge Overview

Mini RSA is a cryptography challenge that demonstrates a weakness that can occur when RSA is implemented with a small public exponent and without proper padding.

## Security Concept

RSA encryption uses the relationship:

c = m^e mod n

where:

- `c` is the ciphertext
- `m` is the plaintext represented as an integer
- `e` is the public exponent
- `n` is the RSA modulus

In this challenge, the public exponent was `e = 3`.

## Investigation

I first examined the RSA parameters provided by the challenge. The small public exponent was an important clue that a low-exponent RSA attack might be possible.

Because the plaintext was small enough, I tested whether the ciphertext had an exact integer cube root.

Using Python, I calculated the integer cube root and verified that the result was exact.

I then converted the recovered plaintext integer into bytes and decoded the bytes into readable text.

## Tools Used

- CyLab Security Academy WebShell
- Python 3
- SymPy
- Linux command line

## What I Learned

I learned that RSA can become vulnerable when a small public exponent such as `e = 3` is used without proper padding and the plaintext is sufficiently small.

This challenge also showed me that examining cryptographic parameters before attempting more complicated attacks can reveal important clues about a vulnerability.

## Security Takeaway

Strong cryptography depends not only on the encryption algorithm but also on implementing it correctly. Proper padding and secure parameter choices are important for preventing attacks against RSA.
