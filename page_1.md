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
