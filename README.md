### File-System-Project

## Introduction

This project implements a basic file system in C for Linux using contiguous allocation. It stores files and their sizes contiguously on a virtual disk and supports basic operations such as creating files (`cat`), listing files (`ls`), and displaying file content (`more`).

## Project Files

- **`simplefs.c`**: Contains the implementation of the file system.
- **`readme.txt`**: This documentation file.
- **`disk.img`**: The virtual disk file used to store data.

## Features

- **Create File (`cat`)**: Creates a new file with specified content.
- **List Files (`ls`)**: Lists all files stored in the file system.
- **Display File Content (`more`)**: Shows the content of a specified file.

## Compilation and Execution

### Requirements

- Ubuntu Linux
- GCC (GNU Compiler Collection)

### Compilation

1. Open a terminal.
2. Navigate to the project directory.
3. Compile the source code:
   ```bash
   gcc simplefs.c -o simplefs
   ```

### Execution

1. Run the program:
   ```bash
   ./simplefs
   ```

2. Follow the prompts to enter commands:
   - **Create File**:
     ```bash
     Enter command (cat, ls, more, exit): cat
     Enter filename: example.txt
     Enter content: This is an example file.
     ```
   - **List Files**:
     ```bash
     Enter command (cat, ls, more, exit): ls
     ```
   - **Show File Content**:
     ```bash
     Enter command (cat, ls, more, exit): more
     Enter filename: example.txt
     ```
   - **Exit Program**:
     ```bash
     Enter command (cat, ls, more, exit): exit
     ```

## Detailed Explanation

### Data Structures

1. **FileEntry**: Represents a file with attributes such as filename, size, and start position on the disk.
   ```c
   typedef struct {
       char filename[100];
       int size;
       int start;
   } FileEntry;
   ```

2. **FileSystem**: Manages an array of `FileEntry` structures, file count, and free space.
   ```c
   typedef struct {
       FileEntry files[100];
       int file_count;
       int free_space;
   } FileSystem;
   ```

### Functions

1. **Initialization (`init_fs`)**: Initializes the file system with default values.
   ```c
   void init_fs(FileSystem *fs) {
       // Initialize file count, free space, and file entries
   }
   ```

2. **Create File (`create_file`)**: Creates a new file with the specified name and content, writing it to the virtual disk.
   ```c
   int create_file(FileSystem *fs, const char *filename, const char *content) {
       // Check space and file limits, then write content to disk
   }
   ```

3. **List Files (`list_files`)**: Lists all files in the file system.
   ```c
   void list_files(FileSystem *fs) {
       // Print filenames of all stored files
   }
   ```

4. **Show File Content (`show_file`)**: Displays the content of a specified file.
   ```c
   void show_file(FileSystem *fs, const char *filename) {
       // Find file and print its content
   }
   ```

5. **Main Function (`main`)**: Provides an interactive menu for the user to enter commands.
   ```c
   int main() {
       // Initialize file system and handle user commands in a loop
   }
   ```

## Known Issues

- No support for file deletion or modification.
- Assumes provided file content does not exceed available disk space.
- Error handling can be improved.

## Conclusion

This project demonstrates a basic file system using contiguous allocation, covering essential operations. Future enhancements could include support for file deletion, modification, and improved error handling.
