# Level 10 - Bandit
**Goal**: Find the password in `data.txt` in a human-readable string preceded by '=' characters.

##Concepts

**`strings`**: Extracts printable text characters from binary files. Helps to filter out non-human-readable data

**`grep`**: Used grep to find specific pattern in text extracted by `strings`.

`strings` clears the data -> `grep` filters what matters and what we are looking for. 

 

## Command used:
```bash
strings data.txt | grep "==="
