# Arithmetic Operations Script
This Bash script takes two numbers as input from the user and performs basic arithmetic operations: addition, subtraction, multiplication, and division. It also handles division by zero.

## Features
   Accepts two numeric inputs from the user.
   Performs the following operations:
  Addition
   Subtraction
   Multiplication
  Division (supports floating-point calculations).
  Handles division by zero with a clear error message.

  ## Script Breakdown
## 1. Shebang
```bash
#!/bin/bash
```

Tells the system to use the Bash shell to execute the script.

## 2. Prompting User Input

```bash
echo "Enter the first number:"
read num1

echo "Enter the second number:"
read num2
```

echo: Displays messages prompting the user to enter two numbers.
read: Captures user input and stores it in variables (num1 and num2).

## 3. Performing Arithmetic Operations
 ```bash
addition=$((num1 + num2))
subtraction=$((num1 - num2))
multiplication=$((num1 * num2))
```

Uses (( )) for integer arithmetic:

$((num1 + num2)): Adds num1 and num2.
$((num1 - num2)): Subtracts num2 from num1.
$((num1 * num2)): Multiplies num1 and num2.

## 4. Handling Division

```bash
if [ $num2 -ne 0 ]; then
  division=$(echo "scale=2; $num1 / $num2" | bc)
else
  division="Undefined (division by zero)"
fi
```

if [ $num2 -ne 0 ]: Checks if the second number is not equal to zero.

If true: Calculates division using bc (basic calculator) for floating-point precision.
scale=2: Ensures results are displayed with two decimal places.

If false: Outputs an error message for division by zero.

## 5. Displaying Results

```bash
echo "Addition: $addition"
echo "Subtraction: $subtraction"
echo "Multiplication: $multiplication"
echo "Division: $division"
```

Prints the results of the calculations using echo.

## How to Run the Script

1. Save the script to a file, e.g., arithmetic.sh.
2. Make the script executable

```bash
chmod +x arithmetic.sh
```
3. Run the script:

```bash
./ arithmetic.sh
```
4. Enter two numbers when prompted, and the results will be displayed.

5. ## Example Output

```plaintext
Enter the first number:
5
Enter the second number:
2
Addition: 7
Subtraction: 3
Multiplication: 10
Division: 2.50
```

## plaintext
If the second number is zero, the output will be:

```bash
Division: Undefined (division by zero)
```

## What is 'bc' in the script?

The script requires the bc command for floating-point calculations. This utility is commonly pre-installed on most Linux distributions

## Takeaways 📚:
User Input in Bash 🖊️: This script demonstrates how to take user input in Bash using the read command. Prompting users and storing their responses in variables is a fundamental skill for creating interactive scripts.

Arithmetic Operations in Bash ➗: Through this script, you've explored both integer arithmetic using $(( )) and floating-point calculations with bc. Understanding when and how to use these tools is crucial for accurate computations in scripts.

Error Handling in Bash ⚠️: The script highlights the importance of handling potential errors, such as division by zero. By using conditional statements (if), you can make scripts more robust and user-friendly.

Formatted Output 🖥️: Displaying results with echo ensures clarity and improves the user experience. Clear and concise output is key to making scripts accessible to others.

By completing this script, you have learned how to create interactive Bash scripts, perform arithmetic operations, handle edge cases gracefully, and present results effectively. 🚀













