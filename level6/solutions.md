# Level 6  - Bandit
**Goal**: Find the password in a file store somewhere in a directory with this properties:

1033 bytes in size
Human readable
Non executable 

## Concepts

**`find`**: Command used to find in directory and all their subdirectories

Filters that can be used in find command:


**`-type`**: Argument to search determined type files (e.g., `-type -f`). 

**`-size`**: Argument to search by file size (e.g., `-size 1033c` c = byte).

**`-executable`**: Argument to search executable files, ! to negate (e.g., `! -executable`).

**`-exec`**: Allows executing a command for each file found

**{}**: Placeholder replaced by the file path

**`\;`**: Terminates command

**`grep`**: Searches for patterns (text or regex) in files or output streams

**Essential flags for `grep`**: - `-i`: Case insensitive search
				- `-r`: Recursive search in directories
				- `v`: Invert match (exclude lines containing the pattern)
				- `-n`: Show line number of matches
				- `-l`: Only show filename that contains the pattern


**Examples**: 

`grep "hello" file.txt` -> Search for word hello in single file

`grep -i "failed" auth.log` -> Case insensitive search

`grep -r "192.168.1" /etc/` -> Recursive search in a directory

`grep -v "success" log.txt` -> Exclude pattern (Invert match)

**Piping with grep**:

| -> Connects the output of a command to the input of another

**Examples**: 

`ps aux | grep "firefox"` -> Filter processes

`cat access.log | grep "404"` -> Search in compressed files

`find /var/log -name "*.log" | xargs grep "ERROR"` -> Combine with find, we are searching for the word error in all the files inside the directory with the name 


## Command used

```bash
find -type f -size 1033c ! -executable -exec file {}\; | grep text
```

 

