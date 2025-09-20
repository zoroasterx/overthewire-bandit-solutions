# Level 12 - Bandit
**Goal**: Decode the ROT13 encoded password from data.txt

## Concepts

**ROT13**: Caesar cipher with shift of 13 positions

	-  Self reversible

	- Only affects letters

**`tr`**: `tr` command (translate), replaces or deletes characters in text

Syntax -> `tr "SET1" "SET2"`

**Input redirection (`<`)**: Sends a file's content as input to a command

Syntax -> `comand < file.txt`

Advantage over piping -> More efficient than `cat file | command` avoids extra process. 


##Command used

```bash
# Method 1: Input redirection (recommended)
tr 'A-Za-z' 'N-ZA-Mn-za-m' < data.txt

# Method 2: Using pipe
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```


