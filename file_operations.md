# File Operations Script
This Bash script demonstrates basic file operations such as creating a directory, navigating into it, creating a file, writing text to the file, and displaying its contents.

## Features
Creates a new directory named File-Operation.
Navigates into the newly created directory.
Creates an empty file named CoderCo inside the directory.
Writes a custom message into the file.
Displays the contents of the file in the terminal.
  ## Script Breakdown
## 1. Shebang
```bash
#!/bin/bash
```

Tells the system to use the Bash shell to execute the script.

## 2. Creating a Directory

```bash
mkdir File-Operation  
```
The mkdir command creates a directory named File-Operation in the current working directory.

## 3. Navigating into the Directory
 ```bash
cd File-Operation  
```
The cd command changes the current directory to File-Operation, making it the active working directory.

## 4. Creating a File

```bash
touch CoderCo  
```
The touch command creates an empty file named CoderCo within the File-Operation directory.

## 5. Writing Text to the File

```bash
echo "Watch me land a DevOps role in 6 months." > CoderCo  
```
echo outputs the provided text.
The > operator redirects the text into the file CoderCo, overwriting any existing content.

## 6. Displaying File Contents

```bash
cat CoderCo  
 ```

## How to Run the Script

1. Save the script to a file, e.g., file_operations.sh
2. Make the script executable

```bash
chmod +x file_operations.sh
```
3. Run the script:

```bash
./file_operations.sh
```
4. Check the directory and file created, and view the displayed message in the terminal

5. ## Example Output

```plaintext
$ ./file_operations.sh  
Watch me land a DevOps role in 6 months.  
```



## Takeaways 📚:
File and Directory Management in Bash 📁: This script introduces how to create directories, navigate into them, and create files using Bash commands like mkdir, cd, and touch.

Writing to Files ✍️: The use of echo with redirection (>) demonstrates how to write content into files programmatically.

Displaying File Contents 📜: The cat command helps in viewing file contents directly from the terminal, making it easy to verify results.

Automation Workflow 🛠️: Following a structured sequence of commands ensures clarity and efficiency in scripting tasks.

By completing this script, you have learned essential skills for automating file operations, managing directories, and presenting outputs effectively in Bash. 🚀
