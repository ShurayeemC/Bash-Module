# File Permission Checker Script
This Bash script checks the existence and permissions of a specified file. It verifies if the file is readable, writable, and executable, providing appropriate messages for each condition.

## Features
- Checks if a specified file exists.
- Verifies the file's permissions:
  - Readable
  - Writable
  - Executable
- Provides clear output messages for each check.

---

## Script Breakdown

## 1. Shebang
```bash
#!/bin/bash
```
Specifies the Bash shell as the interpreter for executing the script.

## 2. Defining the File

```bash
FILE="steak"
```
The variable FILE stores the name or path of the file to check. You can replace "steak" with any file name or path.

## 3. Checking if the File Exists

```bash
if [[ -e "$FILE" ]]; then
    echo "The file '$FILE' exists."
```
The -e flag checks if the file exists. If true, a message confirms its existence and proceeds to permission checks.

## 4. Checking File Permissions

4.1 Readable

```bash
if [[ -r "$FILE" ]]; then
    echo "The file is readable."
else
    echo "The file is not readable."
fi
```
4.2 Writable

```bash
if [[ -w "$FILE" ]]; then
    echo "The file is writable."
else
    echo "The file is not writable."
fi
```
The -w flag checks if the file is writable.

4.3 Executable

```bash
if [[ -x "$FILE" ]]; then
    echo "The file is executable."
else
    echo "The file is not executable."
fi
```
## 5. Handling Non-Existence

```bash
else
    echo "The file '$FILE' does not exist."
fi
```
If the file does not exist, a message indicates its absence, and the script exits without performing permission checks.

## How to run the script

1. Save the script to a file, e.g., file_checker.sh.
2. Make the script executable:

```bash
chmod +x file_checker.sh
```

3. Run the script

```bash
chmod +x file_checker.sh
```
4. Modify the FILE variable to specify the file you want to check.
## Example Output
When the file exists:

```plaintext
The file 'steak' exists.
The file is readable.
The file is writable.
The file is not executable.
```
When the file does not exist:
```plaintext
The file 'steak' does not exist.
```
## Takeaways 📚:
File Existence Check 🔍: This script demonstrates how to check if a file exists using the -e flag.

Permission Checks 🛡️: It introduces the -r, -w, and -x flags to verify read, write, and execute permissions for files.

Conditional Statements in Bash 🤔: Uses if-else blocks to handle different scenarios based on file properties.

Customizable Inputs ✍️: By modifying the FILE variable, you can easily reuse this script for different files.

By completing this script, you’ve gained skills to create scripts that check file properties and permissions, a critical task in file management and automation. 🚀























