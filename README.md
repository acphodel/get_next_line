# get_next_line

## Project Overview

**get_next_line** is a custom implementation of a function designed to read and return a line from a file descriptor. This project emphasizes memory management, performance, and compliance with specific constraints, making it a foundational exercise in C programming and file I/O operations.

---

## Features

- Reads one line at a time from a file descriptor.
- Handles any valid file descriptor, including files, standard input, and redirections.
- Returns:
  - `1` when a line is successfully read.
  - `0` when the end of the file is reached.
  - `-1` when an error occurs.
- Works with customizable buffer sizes (`BUFF_SIZE` macro).
- Properly manages memory to avoid leaks.
- Supports the following scenarios:
  - Reading multiple lines from a file descriptor.
  - Switching between multiple file descriptors (bonus).
- Does not use global variables; static variables are allowed.

---

## Mandatory Part

### Function Prototype
```c
int get_next_line(const int fd, char **line);
```

### Parameters
- `fd` (int): The file descriptor to read from.
- `line` (char **): A pointer to a string where the function will store the line read.

### Behavior
- Returns a line without the trailing newline character (`\n`).
- Reads until `EOF` or an error occurs.
- Handles edge cases like:
  - Large or small files.
  - Buffer size variations.
  - Invalid or closed file descriptors.

---

## Bonus Part

- **Single Static Variable:** Implemented with only one static variable for efficiency and simplicity.
- **Multiple File Descriptors:** Maintains the reading state for multiple file descriptors simultaneously, allowing seamless switching.

---

## Compilation

To use this function, compile your program along with the `get_next_line.c` and include the `get_next_line.h` header file.

### Example Compilation Command
```bash
gcc -Wall -Wextra -Werror -D BUFF_SIZE=32 -o test_program test_program.c get_next_line.c
```
