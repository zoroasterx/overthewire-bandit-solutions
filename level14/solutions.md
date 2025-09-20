# Level 14  - Bandit
**Goal**: Use a private SSH key to connect to bandit14 on localhost. 

## Concepts

**SSH Key Authentication**: 

Private Key: A cryptographic key that replaces password authentication.

Key-Based Auth: More secure than passwords and used for automated access.

Permissions: Private keys require strict file permissions (`chmod 600`).

**SSH Connection Details**:

localhost: Connecting to the same machine (127.0.0.1).

Port Specification: Must specify port 2220 even for local connections.

Identity File: `-i` flag specifies which private key to use.

## Command used:

```bash

ssh -i sshkey.private -p 2220 bandit14@localhost
```

