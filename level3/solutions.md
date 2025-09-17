# Level 3  - Bandit
**Goal**: Open file named --spaces in this filename-- 

## Concepts

**--**: In command arguments signals "end of options" (e.g., `cat -- --filename`)

If you write `cat "--spaces in this filename--"`, it will read `--spaces` as a flag, not a route

## Example commands 

```bash

cat -- "--spaces in this filename--"

cat ./"--spaces in this filename--"
```

