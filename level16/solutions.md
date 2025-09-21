# Level  - Bandit
**Goal**: Submit the current level's password to port 30001 on localhost using SSL/TLS encryption.

 
## Concepts

**SSL/TLS**: What is SSL/TLS?

SSL (Secure Sockets Layer) and TLS (Transport Layer Security) are encryption protocols that create a secure tunnel between two devices over a network.

Like putting your data in a locked safe before sending it through the internet.

Used everywhere: HTTPS websites, secure emails, banking apps, etc.

**How it works**: 

- Server sends a public lock (SSL certificate) to the client

- Client locks the data with this public lock (encryption)

- Only the server has the private key to unlock the data (decryption)

- Secure tunnel established - no one can spy or modify the data

**`openssl s_client`**: 

Tool to test SSL/TLS connections

- `connect`: Specify server and port

- `quiet`: Reduce verbose output

- `ign_eof`: Keep connection open until server closes it

## Command Used

```bash

echo "password" | openssl s_client -connect localhost:30001 -quiet
```

