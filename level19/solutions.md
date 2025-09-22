# Level 19  - Bandit
**Goal**: Retrieve the password from readme in the home directory, but `.bashrc` logs you out immediately on SSH login.

## Concepts

**Bash Shell Fundamentals**:

**Bash (Bourne Again SHell)**: Command interpreter that processes user commands and executes programs.

**Primary function**: Read → Execute → Display loop for terminal interactions.

Not just a programming language: While it supports scripting, its main role is interactive command execution.
--------------------------------------------
**Shell Types: Interactive vs Non-Interactive**:

**Interactive Shell**:
What: Continuous session where you type commands and see results.

Examples:

- Regular SSH login sessions

- Terminal windows in Kali/GUI

- Prompt: `bandit18@bandit:~$`

Behavior: Executes `.bashrc` automatically for environment customization.


**Non-Interactive Shell**:
What: Executes a specific command and terminates immediately.

Examples:

- `ssh user@host "command"`

- Shell scripts

- Automated tasks

Behavior: Does NOT execute `.bashrc.`
-------------------------------------------
**`.bashrc` file**:

**Purpose**: Configuration file that runs when an interactive Bash shell starts.

**Location**: `~/.bashrc`  (user's home directory).

Typical content:

- Aliases (shortcuts)

- Environment variables

- Prompt customization

- Function definitions
------------------------------------------

**The Bandit18 "Trap"**

Modified `.bashrc` contains an exit command that terminates the session immediately.

**Why it works**: Interactive SSH sessions execute `.bashrc` on login.

**Solution**: Use non-interactive SSH to bypass `.bashrc` execution.
------------------------------------------

## Command used:

```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220 "cat readme"
```

Non-interactive mode: SSH executes `cat readme` directly without starting an interactive shell.

`.bashrc` bypassed: Since no interactive shell is created, the malicious exit command never runs.

Command completes: `cat readme` executes successfully and returns the password before connection closes.
--------------------------------------------

##Key Takeaways:

Interactive shells execute `.bashrc`; non-interactive shells do not.

SSH command execution provides a way to bypass shell initialization files.

`.bashrc` is powerful but can be exploited for security challenges.

Understanding shell types is crucial for system administration and troubleshooting.
