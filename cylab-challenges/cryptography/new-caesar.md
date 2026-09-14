# New Caesar

## Challenge Overview

New Caesar is a cryptography challenge that uses a modified Caesar cipher combined with a custom base-16 encoding method.

## Security Concept

The challenge used a custom alphabet containing only 16 lowercase letters. The plaintext was first encoded using this 16-character alphabet and then shifted using a single-character key.

Because the key could only be one of 16 possible characters, the keyspace was small enough to test every possible key.

## Investigation

I reviewed the provided Python source code to understand how the custom encoding and encryption functions worked.

I identified that the encryption process used a single-character key selected from a 16-character alphabet.

Instead of trying to guess the key, I used Python to test all 16 possible keys. For each possible key, I reversed the Caesar-style shift and decoded the resulting base-16 data.

One of the possible keys produced readable plaintext, confirming the correct decryption method.

## Tools Used

- CyLab Security Academy WebShell
- Python 3
- Linux command line
- Source code analysis

## What I Learned

I learned how examining an encryption program's source code can reveal weaknesses in the way a cipher is designed.

This challenge also demonstrated why a small keyspace is insecure because an attacker can quickly test every possible key.

## Security Takeaway

Custom encryption methods can introduce serious weaknesses when they use predictable algorithms or very small keyspaces. Strong cryptographic systems should use well-tested algorithms and sufficiently large keys.
