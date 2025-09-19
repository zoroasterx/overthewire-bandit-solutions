# Level 11  - Bandit
**Goal**: The password for the next level is stored in the file data.txt, which contains base64 encoded data


## Concepts

**Base64 Enconding**: Base64 is an enconding system (not encryption). Converts binary data to ASCII text. 

Safely transmits binary daya through text-based protocols (HTTP, email...)

**Recognize Base64**: 

Character set -> Only contains `A-Z`, `a-z`, `0-9`, `+`, `/`, `=`.

Padding -> Typically ends with `=` or `==`

Lenght -> Always multiple of 4 characters.

No special characters -> `!`, `@`, `#` etc...

## Base64 command

```bash

# Encode text or files
echo "text" | base64
base64 input_file.txt

# Decode Base64
echo "encoded_text" | base64 -d
base64 -d encoded_file.txt

# Flags:
# -d, --decode: Decode data instead of encoding
```

## Common uses

**Data Exfiltration**: Attackers use Base64 to hide malicious payloads

**Forensics Analysis**: Decode artifacts in logs, files, or network traffic

**Protocol Analysis**: HTTP Basic Auth, email attachments, API responses

**Obfuscation**: Simple way to hide plaintext data from casual inspection
