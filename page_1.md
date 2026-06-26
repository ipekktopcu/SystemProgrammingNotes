System = It refers to the infrastructure your programs run on:
- Operating system (OS) -> Linux, Windows
- Hardware -> CPU, RAM, disk
- Kernel -> the core of the OS
- System calls(syscalls) -> how programs communicate with the OS

System = OS + Hardware + control mechanisms

System Programming = Not teach us how to write applications, but how to write software that talks to the system.

| Normal App | System Programming |
| :--- | :--- |
| JavaScript -> button -> UI | C -> read() -> kernel -> fetch data from disk |

So you remove abstraction layers and go closer to the system.

## UNIX File System ##
- In UNIX we can think of everything as a file.
- Unlike Windows there is no disk partitions like C, D or E. All resources can be accessed  from a single directory structure. This is called **mounting.**

- In UNIX, every user has their own directory. Example:
- `/Users/ipeks`
-
  When you connect to the terminal on UNIX, you authomatically start in your home directory
- `/Users/ipeks`
You can navigate to other users' directories using the `cd` command. Additionally, you can use the `~` symbol to refer to the home directory and move to a specific path.

`pwd` -> shows the current directory `/Users/ipeks/Github/lessons/systemprog`
`cd ..` -> moves one level up `/Users/ipeks/Github/lessons`
`cd .` -> stays in the current directory (no change)
`cd ~/example/pyhtonlesson` -> no matter where you are, this takes you to: `/Users/ipeks/example/pyhtonlesson`
## File paths in UNIX and Linux ##
`/bin` = contains executable files for users and system administrators.
`dev` = contains files required to access hardware devices
`etc` = contains system configuration files
`lib` = contains system libraries
`sbin` = contains executable files for system administrators. 
`/home` = directory for user accounts.
`/mnt` = mount points for external devices (USB, harici HDD/SSD, CD/DVD).
`/root` = home directory of the root (superuser).
`/tmp` = directory for temporary files.
`/usr` = contains shared files, programs, and documentation.
`/var` = contains logs, emails, and system/application messages.
`/proc` = virtual directory containing system information.

### History Notes
* **UNIX:** Developed at Bell Labs in the 1970s. It is a modular, multi-user, multi-tasking OS.
* **Linux:** Inspired by UNIX; it is an open-source, versatile, and widely adopted OS.

## Basic Linux Commands ##
`touch ipek.txt` -> Creates a text file named "ipek.txt". (Can be `.c`, `.py`, `.js` etc.)
`mv ipek.txt atlasipek.txt` -> Renames the file without changing its directory.
`mv ipek.txt /persons` -> Moves the file to the "Kisiler" directory.
`mv ipek.txt /persons/atlasipek.txt` -> Moves the file and renames it.
`cp sistem.txt systemprog.txt` -> Copies "system.txt" and names the copy "systemprog.txt".
`rm system.txt` -> Deletes the file named "system.txt".
`rm -rv /persons` -> Deletes the "persons" directory and all its contents recursively.
`mkdir persons` -> Creates a new directory named "persons" in the current location.

#### Shell Flavors
* **Business / Standard:** `sh`, `sysv sh`, `bash`, `ksh`
* **Academic / Oriented:** `BSD`, `csh`, `tcsh`
### Process Management & `fork()`
* `top` -> Displays processes currently running in the CPU.
* `fork()` -> Prepares and creates a new process.

#### How is a new process created?
1. **Parent process initiates:** The current process (parent) calls `fork()`.
2. **Kernel assigns new process ID (PID):** The Kernel gives the new process a unique PID.
3. **Memory copy:** The parent's memory space (code, data, stack) is copied to the child. (Modern systems use copy-on-write).
4. **Child process starts execution:** The new process (child) begins running from the point right after `fork()`.
5. **Parent and child run concurrently:** Both processes run independently, each with its own PID.
6. **Optional `exec()` call:** The child can replace itself with a different program using `exec()`.

