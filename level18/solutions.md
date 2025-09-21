# Level 18  - Bandit
**Goal**: Find the password in passwords.new that was changed from passwords.old


## Concepts

**File Comparison with `diff`**: 

Purpose: Compare files line by line and show differences

Output format:

< : Line from first file (old)

> : Line from second file (new)

c : Changed line (also a for added, d for deleted)
---------------------------------
**Reading `diff` output**:

```bash
42c42
< old_password
---
> new_password
```

Line numbers: Show where changes occurred

Change type: c indicates changed content




