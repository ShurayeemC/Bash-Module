# Directory Backup Script
This Bash script copies all .txt files from a specified source directory to a backup directory. If the backup directory does not exist, the script creates it.

## Features
Accepts source and backup directories as command-line arguments.
Checks if the provided source directory exists.
Creates the backup directory if it doesn't already exist.
Copies all .txt files from the source to the backup directory.
Handles missing directories and provides informative error messages.

## Script Breakdown
## 1. Shebang

```bash
#!/bin/bash
```
Specifies the Bash shell as the interpreter for executing the script.

## 2. Accepting Arguments

```bash
SOURCE_DIR=$1  
BACKUP_DIR=$2  
```
$1 and $2: Accept the source and backup directory paths as command-line arguments.

## 3. Argument Validation
Check if both arguments are provided:

```bash
if [[ -z "$SOURCE_DIR" || -z "$BACKUP_DIR" ]]; then  
    echo "Usage: $0 <source_directory> <backup_directory>"  
    exit 1  
fi  
```
Validates that both arguments are passed when running the script.

Check if the source directory exists:

```bash
if [[ ! -d "$SOURCE_DIR" ]]; then  
    echo "Error: Source directory '$SOURCE_DIR' does not exist."  
    exit 1  
fi  
```
Ensures the source directory exists, else exits with an error.

## 4. Creating the Backup Directory

```bash
if [[ ! -d "$BACKUP_DIR" ]]; then  
    echo "Backup directory '$BACKUP_DIR' does not exist. Creating it..."  
    mkdir -p "$BACKUP_DIR"  
    if [[ $? -ne 0 ]]; then  
        echo "Error: Failed to create backup directory."  
        exit 1  
    fi  
fi  
```
Checks if the backup directory exists. If not, creates it using mkdir -p.
Exits with an error if directory creation fails.

## Copying .txt Files

```bash
cp "$SOURCE_DIR"/*.txt "$BACKUP_DIR" 2>/dev/null  

```
Copies all .txt files from the source directory to the backup directory.

Redirects error messages to /dev/null to suppress "no such file" warnings

## Success or Error Messages

```bash
if [[ $? -eq 0 ]]; then  
    echo "All .txt files have been successfully copied."  
else  
    echo "No .txt files found in the source directory or an error occurred."  
fi  
```

Provides feedback on whether the files were copied successfully or not.

## How to Run the Script
1. Save the script to a file, e.g., backup_txt_files.sh.
2. Make the script executable:

```bash
chmod +x backup_txt_files.sh  

```
```bash
./backup_txt_files.sh /path/to/source /path/to/backup  

```
## Example Output
```bash
Backup directory '/path/to/backup' does not exist. Creating it...  
Copying .txt files from '/path/to/source' to '/path/to/backup'...  
All .txt files have been successfully copied.  

```
No .txt Files Found or Error:
```bash
Copying .txt files from '/path/to/source' to '/path/to/backup'...  
No .txt files found in the source directory or an error occurred.  
```

## Takeaways 📚:
Argument Handling in Bash ⚙️: This script demonstrates how to use positional arguments $1 and $2 for user inputs.

Directory Management 📂: Introduces mkdir -p for creating directories and validation checks with -d.

File Operations 🗂️: Explores how to copy specific file types using cp and manage potential errors.

Error Handling ⚠️: Validates inputs and directories, providing user-friendly error messages for missing arguments or directories.

By completing this script, you’ve gained practical skills in file and directory management, automation, and error handling in Bash. 🚀
