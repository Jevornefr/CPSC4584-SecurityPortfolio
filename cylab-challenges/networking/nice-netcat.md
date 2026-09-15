# Nice Netcat

## Challenge Overview

Nice Netcat is a networking challenge that demonstrates how Netcat can be used to connect to a remote service and receive data.

## Investigation

I used the hostname and port supplied by the challenge to establish a connection with the remote service using Netcat.

The server returned a series of numerical values. I analyzed the values and converted them into readable characters to recover the hidden message.

## Tools Used

- CyLab Security Academy WebShell
- Linux command line
- Netcat (`nc`)
- Character encoding conversion

## What I Learned

I learned how Netcat can retrieve information from a remote network service and how numerical character values can represent readable text.

## Security Takeaway

Security analysts should understand network connections and data representation because information transmitted across a network may require additional analysis before it becomes readable.
