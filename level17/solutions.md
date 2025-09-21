# Level 17  - Bandit
**Goal**: Find the only open port between 31000-32000 that returns an SSH private key instead of echoing input.


## Concepts

**Port Scanning with `nmap`**: 
------------------------------
**Purpose**: Discover open ports and identify services running on them.

**Key flags**:

`-sV`: Detect service/version info (crucial for identifying SSL)

`-p`: Specify port range (31000-32000)

**Service identification**: ssl/ prefix indicates SSL/TLS encryption required
-------------------------------

**SSL/TLS Service Testing**:

`openssl s_client`: Connect to SSL services directly

`-quiet`: Suppress verbose output (focus on response)
--------------------------------

**RSA Private Key Format**:

Starts with: -----BEGIN RSA PRIVATE KEY-----

Ends with: -----END RSA PRIVATE KEY-----

Usage: Save to file and use with `ssh -i` for authentication
----------------------------------

## Commands used:

```bash
# Port scanning
nmap -sV -p 31000-32000 localhost

# SSL service testing
echo "kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx" | openssl s_client -connect localhost:31790 -quiet

# Key handling
chmod 600 bandit17.key
ssh -i bandit17.key bandit17@bandit.labs.overthewire.org -p 2220
```
