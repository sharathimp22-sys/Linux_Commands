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
