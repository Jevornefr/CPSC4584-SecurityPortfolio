# Strings It

## Challenge Overview

Strings It is a General Skills challenge that demonstrates how readable text can be extracted from a file using Linux command-line tools.

## Investigation

I examined the provided file using the `strings` utility.

Instead of manually searching through all of the output, I used command-line filtering to locate the relevant readable information contained within the file.

## Tools Used

- CyLab Security Academy WebShell
- Linux command line
- strings
- grep

## What I Learned

I learned that binary files can still contain readable text even when opening the file normally does not produce useful information. I also learned how combining commands can make searching large amounts of output faster.

## Security Takeaway

The `strings` command can be useful during security investigations because it may reveal readable information, filenames, messages, URLs, or other artifacts embedded inside a file.
