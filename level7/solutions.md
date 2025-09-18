# Level 7 - Bandit
**Goal**: Find a file owned by user `bandit7` and group `bandit6`, with a size of 33 bytes.

## Concepts

**Ownership in Linux**: Ownership determines which user and group have control over a file or directory. It is a fundamental security concept in Linux.

**User owner**: The individual user who owns the file

**Group owner**: A group of users who share access permission

To view ownership, use `-l` flag

##Command used 

```bash
find / -type f -size 33c -user bandit7 -group bandit6 2>/dev/null
```

/ next to find searches in all directories

`-user` flag to search determined user owner
`-group` flag to search determined group owners

## Why `2>/dev/null`?
When searching from the root directory (`/`), `find` attempts to access restricted folders (e.g., `/root`, `/sys`), causing "Permission denied" errors.  
- `2>` redirects error messages (stderr).  
- `/dev/null` discards them.  
Result: Only valid results are displayed.

