# Linux_Commands
A collection of Linux command practice, terminal navigation examples, and basic Bash scripting exercises as part of my learning in cloud and IT systems.


<img width="836" height="619" alt="image" src="https://github.com/user-attachments/assets/eec6098c-90dd-49c9-a0c1-2faf9fa80bec" />

## Navigation Commands

### pwd - Print Working Directory
Running `pwd` returned `/root`, confirming that the current 
working directory is the root user's home directory.

### ls - List Files
Running `ls` displayed all visible files in the current directory:
`bench.py`, `hello.c`, `hello.js`, `readme.txt`, `rv128test.bin`

### ls -al - List All Files with Details
Running `ls -al` displayed all files including hidden files 
(files starting with `.`) along with:
- **File permissions** (e.g. `drwxr-xr-x`)
- **Owner** (root)
- **File size** in bytes
- **Last modified date**

Hidden files found: `.Xauthority`, `.dillo`, `.fltk`, 
`.fluxbox`, `.serverauth.46`, `.xsession`

<img width="843" height="660" alt="image" src="https://github.com/user-attachments/assets/9ded6ed8-49a8-4ed9-a66c-eb07f7a18196" />

## File Operations - cp, mv, mkdir, touch

### Commands Practiced

**Created a new file**
touch sharath777.txt

**Created a new folder**
mkdir Sharathfiles

**Copied a file into a folder**
cp sharath777.txt Sharathfiles

**Verified the copy worked**
cd Sharathfiles
ls
# Output: sharath777.txt ✅

**Moved a file into a folder**
mv sharath777.txt Sharathfiles/

### Error Encountered & Fixed
Got error: `cp: can't stat 'sharath777.txt': No such file or directory`
This happened because I was inside `Sharathfiles` folder 
instead of `Directory_1`. Fixed it by going back using `cd` 
and running the command from the correct directory.

### What I Learned
- Always check which directory you are in using `pwd`
- `cp` and `mv` need to be run from the correct location
- Linux commands are case sensitive — `Cd` is not same as `cd`

<img width="838" height="658" alt="image" src="https://github.com/user-attachments/assets/96c23656-f187-4693-922b-b1d155aca1dc" />

## File Operations - rm, rm -rf

### Commands Practiced

**Deleted a single file**
rm sharath777.txt

**Deleted a folder and all its contents**
rm -rf Sharathfiles

**Verified deletion**
ls
# Output: only rocky.txt remaining ✅

### Error Encountered & Fixed
Got error: `rm: can't remove 'Sharath777.txt': No such file or directory`
This happened because Linux is **case sensitive** —
`Sharath777.txt` and `sharath777.txt` are different files.
Fixed by using the exact correct filename.

### What I Learned
- `rm` deletes a single file
- `rm -rf` deletes a folder and everything inside it
- Linux is **case sensitive** — filenames must match exactly
- Always run `ls` after deleting to confirm it worked

<img width="844" height="664" alt="image" src="https://github.com/user-attachments/assets/374aeb9c-7caf-4170-9b0f-ba86c56b43fb" />

<img width="830" height="400" alt="image" src="https://github.com/user-attachments/assets/76fc318c-d757-4b71-a096-0b074e0c3e6d" />


## File Permissions - chmod, chown, whoami

### Commands Practiced

**Viewed file permissions**
ls -l
# Output: -rw-r--r-- (no execute permission)

**Added execute permission**
chmod +x rocky.txt
ls -l
# Output: -rwxr-xr-x ✅ (x added, file turned green!)

**Removed execute permission**
chmod -x rocky.txt
ls -l
# Output: -rw-r--r-- (x removed successfully)

**Set permissions using numbers**
chmod 755 rocky.txt
ls -l
# Output: -rwxr-xr-x ✅ (full owner, read+execute for others)

**Checked current user**
whoami
# Output: root

### Errors Encountered & What I Learned
- `cd whoami` → Error: whoami is a command not a directory
- `chown newuser` → Error: user does not exist on this system
- `chown user:group` → Error: group does not exist on this system

### Key Observations
- File turned **green** in terminal after chmod +x 
  — this means the file is now executable
- `chmod +x` and `chmod 755` both add execute permission
- `chmod -x` removes execute permission
- `chown` requires real existing users on the system


<img width="841" height="517" alt="image" src="https://github.com/user-attachments/assets/78cc58a7-6831-4248-83d9-424af6a2166a" />


## Search Commands - grep, find

### Commands Practiced

**Search for text inside a file**
grep "hi" rocky.txt
# Output: hi ✅ (found the word "hi" in the file)

**Search ignoring uppercase/lowercase**
grep -i "HI" rocky.txt
# Output: hi ✅ (found even though we searched in uppercase)

**Find a specific file by name**
find . -name "rocky.txt"
# Output: ./rocky.txt ✅

**Find all .txt files**
find . -name "*.txt"
# Output: ./rocky.txt ✅

**Find all .sh files**
find . -name "*.sh"
# Output: nothing (no .sh files exist here)

**Find all folders**
find . -type d
# Output: . (only current directory exists, no subfolders)

### Error Encountered & Fixed
grep "hi" rocky.txt failed first because I was in the 
wrong directory (~). Fixed by navigating to Directory_1 
using `cd Directory_1` first.

### What I Learned
- `grep` searches for text **inside** a file
- `grep -i` makes the search **case insensitive**
- `find . -name` searches for files **by name**
- `*` is a wildcard — `*.txt` means any file ending in .txt
- Always check your current directory before running commands

<img width="843" height="668" alt="image" src="https://github.com/user-attachments/assets/69df34b9-8396-498e-ae32-24254964c8d1" />
<img width="844" height="667" alt="image" src="https://github.com/user-attachments/assets/dd109be7-0f18-4891-a71a-5522d63ce5f2" />
<img width="852" height="271" alt="image" src="https://github.com/user-attachments/assets/4357259d-0d4b-46b8-b423-15f54aa46ff0" />

## Viewing Files - cat, head, tail

### File Used
First edited `rocky.txt` using `vi` editor and added 11 lines of text.

### Commands Practiced

**cat - Print entire file contents**
cat rocky.txt
# Output: showed all 11 lines from hi to line 10 end ✅

**head - Show first 10 lines**
head rocky.txt
# Output: showed first 9 lines (hi to line 9 focus) ✅

**tail - Show last 10 lines**
tail rocky.txt
# Output: showed last 10 lines (line 1 welcome to line 10 end) ✅

### Key Difference Between head and tail
| Command | Shows |
|---------|-------|
| `cat` | All lines in the file |
| `head` | First 10 lines only |
| `tail` | Last 10 lines only |

### What I Learned
- `vi` can be used to edit existing files, not just create them
- `cat` is best for small files to see all content at once
- `head` is useful to quickly check the beginning of a file
- `tail` is useful to check the most recent entries in log files
- Linux is case sensitive — `Cat` failed but `cat` worked


