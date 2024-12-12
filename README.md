
---

# Xv6 Custom System Calls and Unix Utilities

## Overview
This project enhances the xv6 operating system by implementing new system calls and developing a series of simplified UNIX-like utilities. The modifications include new functionalities for process creation, inter-process communication (IPC), signals, and more.

---

## File Structure
1. **Project - 1**: Contains the code files and documentation for system call modifications.
2. **Project - 2**: Contains the code files and documentation for UNIX-like utilities.

---

## Project - 1: Implementing New System Calls
Using the xv6 operating system, this project involves:
1. Analyzing the existing implementation of system calls.
2. Writing new system calls for:
   - Fork tree
   - Signals
   - Waitpid
   - Exit
   - Priority pipes
3. Demonstrating their usage by adding user programs in xv6 that incorporate these system calls.

### System Call Details
1. **Fork Tree (`fork(n)`)**
   - **Functionality**: Creates a tree structure of `n` child processes.
   - **Usage**:
     ```c
     int n = 5; // Number of children
     fork_tree(n);
     ```

2. **Waitpid (`wait_pid()`)**
   - **Functionality**: Waits for a specific child process to terminate.
   - **Usage**:
     ```c
     int status;
     int pid = wait_pid(child_pid, &status, 0);
     ```

3. **Exit (`exit()`)**
   - **Functionality**: The parent process exits only after all child processes have terminated.
   - **Usage**:
     ```c
     exit(0);
     ```

4. **Priority Pipes (`pr_pipe()`)**
   - **Functionality**: Manages inter-process communication with prioritized messages.
   - **Usage**:
     ```c
     char message[] = "Important message";
     pr_pipe(1, message, sizeof(message));
     ```

5. **Signal Handling (`sigint`)**
   - **Functionality**: Handles `CTRL+C` signal to pause and resume the process.
   - **Usage**:
     ```c
     void my_handler(int signum) {
       // Handle signal
     }
     signal(SIGINT, my_handler);
     ```


---

## Project - 2: Simplified Unix-Like Utilities
This project includes the development of simplified versions of common UNIX commands, build from scratch:

1. **ls** - List directory contents
   - `ls -l`: Displays detailed information about each file
   - `ls -a`: Lists all files including hidden files
   - `ls -s`: Displays the size of each file
   - Example:
     ```sh
     ls -l
     ls -a
     ls -s
     ```

2. **cat** - Concatenate and display file content
   - `cat -u`: Display file content in uppercase
   - `cat -l`: Display file content with line numbers
   - Example:
     ```sh
     cat -u filename.txt
     cat -l filename.txt
     ```

3. **grep** - Search for patterns in files
   - `grep -i`: Case insensitive search
   - `grep -v`: Invert match; select non-matching lines
   - Example:
     ```sh
     grep -i "pattern" filename.txt
     grep -v "pattern" filename.txt
     ```

4. **wc** - Word, line, and character count
   - Example:
     ```sh
     wc filename.txt
     ```

5. **cp** - Copy files
   - `cp -r`: Recursively copy directories
   - Example:
     ```sh
     cp source.txt destination.txt
     cp -r source_directory/ destination_directory/
     ```

6. **mv** - Move or rename files
   - `mv -r`: Recursively move directories
   - Example:
     ```sh
     mv oldname.txt newname.txt
     mv -r source_directory/ destination_directory/
     ```

7. **rm** - Remove files or directories
   - `rm -r`: Recursively remove directories
   - Example:
     ```sh
     rm filename.txt
     rm -r directory_name/
     ```

---

## Documentation
- **Project Details**: A thorough analysis and explanation of the new system calls.
- **User Programs**: Example programs showing the implementation and usage.

## Acknowledgements
- Special thanks to the original xv6 developers for providing the base operating system to work on.

---

