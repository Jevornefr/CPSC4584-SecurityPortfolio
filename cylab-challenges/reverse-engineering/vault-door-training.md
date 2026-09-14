# VaultDoorTraining

## Challenge Overview

VaultDoorTraining is an introductory Reverse Engineering challenge involving analysis of Java source code.

## Investigation

I examined the provided Java program and identified the section responsible for validating the user's input.

By following the program's logic, I determined how the application performed its password comparison and used that information to complete the challenge.

## Tools Used

- CyLab Security Academy WebShell
- Java source code
- Linux command line
- Source code analysis

## What I Learned

I learned that source code can reveal how a program processes and validates user input. I also gained experience reading basic Java code from a security-analysis perspective.

## Security Takeaway

Sensitive credentials should not be stored directly in source code because anyone with access to the code may be able to recover them.
