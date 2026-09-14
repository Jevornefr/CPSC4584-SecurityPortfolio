# Interencdec

## Challenge Overview

Interencdec is a cryptography challenge involving multiple layers of encoding and encryption.

## Security Concept

Encoded or encrypted information may be processed through multiple transformations. Identifying each transformation and reversing them in the correct order is important when analyzing protected or obfuscated data.

## Investigation

I examined the provided encoded text and identified Base64 encoding.

After decoding the first layer, I discovered another encoded value. I decoded the additional Base64 layer and obtained text that was still unreadable.

I determined that the remaining text used a Caesar cipher. I tested the appropriate shift and recovered readable plaintext.

## Tools Used

- CyLab Security Academy WebShell
- Linux command line
- Base64
- Caesar cipher analysis

## What I Learned

I learned how to work through multiple layers of encoding and encryption instead of assuming that one decoding operation will reveal the final plaintext.

The challenge also improved my ability to recognize Base64 data and Caesar cipher patterns.

## Security Takeaway

Encoding should not be treated as encryption. Multiple layers of simple encoding or weak ciphers may make information harder to read, but they do not necessarily provide strong security.
