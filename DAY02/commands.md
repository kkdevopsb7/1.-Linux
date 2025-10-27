
# Linux Commands – Complete Guide with Real-Time Use Cases

## What is a Command?

A **command** in Linux is an instruction given to the system to perform a specific task — like creating files, checking status, or managing users.

Think of it as telling the operating system:

> “Do this specific job for me.”

---

## What is a Program?

A **program** is a collection of instructions (commands + logic) designed to perform a broader function.
Examples: `ls`, `cat`, `top`, and `grep`.

---

## 1. `clear` – Clear Terminal Screen

### Description

Used to clear the terminal screen and remove previous outputs.

### Syntax

```bash
clear
```

### Alternate Shortcut

```
Ctrl + L
```

### Use Cases

* When the terminal becomes cluttered.
* Before taking screenshots or sharing your screen.
* To improve visibility during training or troubleshooting.

---

## 2. `uname` – Display System Information

### Description

Shows details about your operating system, kernel, and architecture.

### Syntax & Examples

```bash
uname          # Show kernel name
uname -a       # Show all system details
uname -r       # Show kernel version
uname -m       # Show machine hardware
uname -s       # Show kernel name
uname -n       # Show hostname
```

### Use Cases

* Check OS before software installation.
* Identify kernel version during debugging.
* Confirm server type (RHEL, Ubuntu, Amazon Linux).

---

## 3. `man` – Manual Pages

### Description

Displays documentation for Linux commands with syntax, options, and examples.

### Syntax & Examples

```bash
man ls             # Show manual for ls
man mkdir          # Manual for mkdir
man 5 passwd       # View section 5 of passwd file
man -k user        # Search for 'user' related commands
```

### Use Cases

* Learn command usage in detail.
* Explore hidden options for `grep`, `awk`, `sed`.
* Quick help when no internet access is available.

---

## 4. `whoami` – Show Current User

### Description

Displays the username of the person currently logged into the system.

### Syntax

```bash
whoami
```

### Use Cases

* Verify user before running `sudo` commands.
* Identify which user executed a deployment.
* Helpful in automation logs.

---

## 5. `pwd` – Print Working Directory

### Description

Displays the full path of the current working directory.

### Syntax

```bash
pwd
```

### Example

```bash
/home/ec2-user/projects
```

### Use Cases

* Confirm your working directory.
* Use inside scripts to log paths.
* Check location before running `rm` or `cp`.

---

## 6. `history` – Show Command History

### Description

Displays all previously executed commands.

### Syntax & Examples

```bash
history              # Show full history
history | grep yum   # Filter results
!!                   # Repeat last command
!45                  # Run command number 45
!sudo                # Run last command starting with sudo
history -c           # Clear all history
history -d 100       # Delete command at line 100
```

### Use Cases

* Quickly repeat past commands.
* Troubleshoot what steps were executed before failure.
* Audit activity on shared Linux systems.

---

## 7. `sudo su -` – Switch to Root User

### Description

Grants administrative privileges for performing system-level tasks.

### Syntax

```bash
sudo su -       # Switch to root user
exit             # Return to normal user
```

### Use Cases

* Install or update packages (`sudo yum install httpd -y`)
* Edit configuration files (`/etc/hosts`, `/etc/fstab`)
* Restart services (`systemctl restart nginx`)

### Note

Root user has full control. Be careful when deleting or modifying system files.

---

## 8. `who` – Show Logged-in Users

### Description

Displays all users currently logged into the system with login details.

### Syntax

```bash
who
who -uH    # Show idle time and process IDs
```

### Use Cases

* Check active users on multi-user servers.
* Identify remote logins or session count.
* Audit login activity.

---

## 9. `mkdir` – Create Directories

### Description

Used to create new directories (folders).

### Syntax & Examples

```bash
mkdir test              # Create a single directory
mkdir one two three     # Create multiple directories
mkdir -p a/b/c          # Create nested directories
mkdir -v project        # Verbose mode
mkdir "kk funda"        # Directory with spaces
mkdir -m 755 scripts    # Create directory with permissions
```

### Use Cases

* Create directory structures for projects:

  ```bash
  mkdir -p /opt/app/{frontend,backend,logs}
  ```
* Prepare folders before deploying code.

---

## 10. `cd` – Change Directory

### Description

Used to move between directories in the Linux filesystem.

### Syntax & Examples

```bash
cd /etc                 # Go to configuration directory
cd /var/log             # Access log files
cd ~/Downloads          # Go to user's download folder
cd ..                   # Move one level up
cd ../..                # Move two levels up
cd -                    # Switch back to previous directory
cd                      # Go to home directory
```

### Use Cases

* Move between application folders.
* Use inside shell scripts for navigation before commands.
* Quick access to log or config directories.

---

## 11. `rmdir` – Remove Empty Directory

### Description

Deletes an empty directory.

### Syntax

```bash
rmdir logs
rmdir -p one/two/three  # Remove nested empty directories
```

### Use Cases

* Clean up build directories.
* Delete temp folders after file operations.

---

## 12. `rm` – Remove Files and Directories

### Description

Deletes files or directories (including non-empty ones).

### Syntax & Examples

```bash
rm file.txt              # Remove file
rm -i file.txt           # Ask for confirmation
rm -rf temp/             # Force delete directory
rm -v file.txt           # Verbose output
```

### Use Cases

* Remove old logs (`rm -rf /var/log/httpd/*`)
* Clean build artifacts (`rm -rf target/`)
* Important: Always double-check before running `rm -rf` in production.

---

## 13. `touch` – Create Empty Files or Update Timestamp

### Description

Creates an empty file or updates the timestamp of existing files.

### Syntax & Examples

```bash
touch demo.txt                 # Create file
touch file1 file2 file3        # Multiple files
touch -t 202510261030 file1    # Set custom timestamp
```

### Use Cases

* Create placeholder files during automation.
* Update modification time of files.
* Create configuration placeholders:

  ```bash
  touch /var/www/html/health.html
  ```

---

## 14. `ls` – List Directory Contents

### Description

Lists files and directories with optional details like permissions, size, and modification date.

### Syntax & Examples

```bash
ls              # Basic listing
ls -l           # Long format
ls -a           # Show hidden files
ls -lh          # Human readable
ls -lrt         # Sort by modification time
ls /etc | grep ssh  # Filter using grep
```

### Use Cases

* Check permissions and ownership.
* Validate files after deployment.
* Identify recently modified files.

---

## 15. `cat` – View File Content

### Description

Displays file contents directly in the terminal.

### Syntax & Examples

```bash
cat file.txt
cat -n file.txt       # Show line numbers
cat file1 file2 > merged.txt
```

### Use Cases

* View configuration files (`cat /etc/hosts`)
* Display log output (`cat /var/log/messages`)
* Merge multiple files into one.

---

## 16. `echo` – Display Text or Variables

### Description

Used to print text or variable values to the terminal.

### Syntax & Examples

```bash
echo "Hello KK FUNDA"
echo $USER
echo "Current path: $(pwd)"
```

### Use Cases

* Print debug information in shell scripts.
* Display environment variable values.
* Write text into files:

  ```bash
  echo "DevOps" > notes.txt
  ```

---

## Summary Table

| Command     | Description             | Example Use Case           |
| ----------- | ----------------------- | -------------------------- |
| `clear`     | Clear terminal screen   | Clean console before demo  |
| `uname`     | Show system info        | Verify OS & kernel version |
| `man`       | View manual pages       | Learn command syntax       |
| `whoami`    | Show current user       | Verify current login user  |
| `pwd`       | Print working directory | Confirm current path       |
| `history`   | List previous commands  | Rerun previous steps       |
| `sudo su -` | Switch to root user     | Perform admin tasks        |
| `who`       | Show logged-in users    | Identify active sessions   |
| `mkdir`     | Create directories      | Setup project structure    |
| `cd`        | Change directory        | Navigate through paths     |
| `rmdir`     | Remove empty folders    | Clean temporary dirs       |
| `rm`        | Delete files & folders  | Remove artifacts/logs      |
| `touch`     | Create empty files      | Create placeholders        |
| `ls`        | List files              | Check file details         |
| `cat`       | View file content       | Read configuration or logs |
| `echo`      | Print text              | Debug or output values     |

---

Would you like me to continue this document with the **next 10 essential commands** (`cp`, `mv`, `head`, `tail`, `grep`, `find`, `chmod`, `chown`, `df`, `du`) in the same clean `.md` format?
