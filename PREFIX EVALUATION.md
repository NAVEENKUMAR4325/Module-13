# Exp.No:34  
## PREFIX EVALUATION

---

### AIM  
To write a Python program to evaluate a user-given Prefix expression using a stack. The expression must contain operators such as Multiplication, Addition, and Subtraction.

---

### ALGORITHM

1. **Start the program.**
2. Define a set of valid operators: `*, -, +, %, /, **`.
3. Initialize an empty stack.
4. Traverse the prefix expression from **right to left**:
   - If the character is a **digit**, convert it to an integer and push it onto the stack.
   - If the character is an **operator**, pop two elements from the stack.
     - Apply the operator on the two popped operands.
     - Push the result back onto the stack.
   - If an invalid character is encountered, raise an error.
5. After traversal, the stack should contain only **one element**.
6. Return the **single element** as the evaluation result.
7. **End the program.**

---

### PROGRAM

```
OPERATORS = set(['*', '-', '+'])

def evaluate(expression):
    stack = []
    
   
    for ch in reversed(expression):
        if ch.isdigit():
            stack.append(int(ch))
        elif ch in OPERATORS:
            op1 = stack.pop()
            op2 = stack.pop()

            if ch == '+':
                stack.append(op1 + op2)
            elif ch == '-':
                stack.append(op1 - op2)
            elif ch == '*':
                stack.append(op1 * op2)
    
    return stack.pop()


test_expression = input().strip()


print("Prefix Expression :", test_expression)
print("Evaluation result :", evaluate(test_expression))


```


### OUTPUT
![image](https://github.com/user-attachments/assets/94fbcee2-b4ec-4a38-947a-97dcd8c3aa7c)



### RESULT
Thus, the evaluation of a prefix expression using stack operations and operator precedence was successfully implemented and executed.
