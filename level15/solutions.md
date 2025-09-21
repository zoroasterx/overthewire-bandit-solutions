# Level 15  - Bandit
**Goal**: Submit the current level's password to port 30000 on localhost to receive the next password.


## Concepts

**Network Services and Ports**: 

Port: A numbered endpoint (0-65535) where network services listen for connections.

Localhost: The current machine itself (IP: 127.0.0.1).

Service Interaction: Some services accept input and return output via specific ports.

**`netcat` (`nc`)**:

Purpose: Tool for reading/writing data across network connections (TCP/UDP).

Basic syntax:` nc [host] [port]`

With pipes:` echo "text" | nc [host] [port]` sends text directly to the service.

**Password Submission Protocol**:

Concept: Some services validate credentials by receiving passwords on specific ports.

No SSH involved: Raw TCP communication, not encrypted SSH.

##Command used:

```bash

echo "current_password" | nc localhost 30000
```

