# Mind Your Ps and Qs

## Challenge Overview

This challenge demonstrated how RSA encryption can be broken when the RSA modulus can be factored into its two prime numbers.

## Security Concept

RSA uses two prime numbers, commonly represented as `p` and `q`, to create the modulus:

n = p × q

If an attacker can factor `n` and recover `p` and `q`, they can calculate the private key and decrypt the ciphertext.

## Investigation

I examined the provided RSA values, including the modulus, public exponent, and ciphertext.

I factored the modulus to recover the two prime numbers. I verified that multiplying the two primes produced the original modulus.

Using Python, I calculated Euler's totient and determined the RSA private exponent. I then decrypted the ciphertext and converted the resulting integer into readable text.

## Tools Used

- CyLab Security Academy WebShell
- Python 3
- Linux command line
- RSA calculations

## What I Learned

I learned how the security of RSA depends heavily on the difficulty of factoring the modulus.

This challenge also helped me understand the relationship between the public key, private key, prime factors, and Euler's totient.

## Security Takeaway

RSA keys must use sufficiently large and securely generated prime numbers. If the modulus can be factored, an attacker may be able to reconstruct the private key and decrypt protected information.
