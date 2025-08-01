# ✅03 **Control Statements in Java**

Control statements are **used to control the flow of execution** of a program. They decide which block of code should be executed under what condition.

---

## 🔹 1. `if` and `if-else` Statement

### ➤ `if` Statement

Executes a block of code only **if the condition is true**.

### **Syntax:**

```java
if (condition) {
    // code to execute if condition is true
}
```

### 💡 Example 1:

```java
int age = 20;
if (age >= 18) {
    System.out.println("Eligible to vote");
}
```

### 💡 Example 2:

```java
int number = 10;
if (number % 2 == 0) {
    System.out.println("Even number");
}
```

---

### ➤ `if-else` Statement

Executes **one block** if the condition is true, **another block** if it’s false.

### **Syntax:**

```java
if (condition) {
    // true block
} else {
    // false block
}
```

### 💡 Example 1:

```java
int marks = 45;
if (marks >= 50) {
    System.out.println("Pass");
} else {
    System.out.println("Fail");
}
```

### 💡 Example 2:

```java
int x = 5, y = 10;
if (x > y) {
    System.out.println("x is greater");
} else {
    System.out.println("y is greater");
}
```

---

## 🔹 2. `switch-case` Statement

Used when you have multiple options to choose from. It's an alternative to long `if-else-if` chains.

### **Syntax:**

```java
switch(expression) {
    case value1:
        // code
        break;
    case value2:
        // code
        break;
    default:
        // default code
}
```

### 💡 Example 1:

```java
int day = 3;
switch(day) {
    case 1: System.out.println("Sunday"); break;
    case 2: System.out.println("Monday"); break;
    case 3: System.out.println("Tuesday"); break;
    default: System.out.println("Invalid Day");
}
```

### 💡 Example 2:

```java
char grade = 'B';
switch(grade) {
    case 'A': System.out.println("Excellent"); break;
    case 'B': System.out.println("Good"); break;
    case 'C': System.out.println("Average"); break;
    default: System.out.println("Fail");
}
```

---

## 🔹 3. **Loops**

Loops are used to **execute a block of code repeatedly**.

---

### ➤ `for` Loop

Best when the **number of iterations is known**.

### **Syntax:**

```java
for (initialization; condition; update) {
    // loop body
}
```

### 💡 Example 1: Print 1 to 5

```java
for (int i = 1; i <= 5; i++) {
    System.out.println(i);
}
```

### 💡 Example 2: Sum of 1 to 10

```java
int sum = 0;
for (int i = 1; i <= 10; i++) {
    sum += i;
}
System.out.println("Sum: " + sum);
```

---

### ➤ `while` Loop

Used when the **condition is checked before loop execution**.

### **Syntax:**

```java
while (condition) {
    // code
}
```

### 💡 Example 1: Print numbers 1 to 5

```java
int i = 1;
while (i <= 5) {
    System.out.println(i);
    i++;
}
```

### 💡 Example 2: Print even numbers ≤ 10

```java
int n = 2;
while (n <= 10) {
    System.out.println(n);
    n += 2;
}
```

---

### ➤ `do-while` Loop

Loop **executes at least once**, then checks condition.

### **Syntax:**

```java
do {
    // code
} while (condition);
```

### 💡 Example 1:

```java
int i = 1;
do {
    System.out.println(i);
    i++;
} while (i <= 3);
```

### 💡 Example 2: Input until user enters 0

```java
import java.util.Scanner;
Scanner sc = new Scanner(System.in);
int num;
do {
    System.out.print("Enter a number (0 to exit): ");
    num = sc.nextInt();
} while (num != 0);
```

---

## 🔹 4. `break` and `continue`

### ➤ `break`: **Exits the loop** immediately.

### 💡 Example 1:

```java
for (int i = 1; i <= 10; i++) {
    if (i == 5)
        break;
    System.out.println(i);
}
// Output: 1 2 3 4
```

### 💡 Example 2:

```java
int i = 1;
while (true) {
    System.out.println(i);
    if (i == 3)
        break;
    i++;
}
```

---

### ➤ `continue`: **Skips the current iteration**, goes to next.

### 💡 Example 1:

```java
for (int i = 1; i <= 5; i++) {
    if (i == 3)
        continue;
    System.out.println(i);
}
// Output: 1 2 4 5
```

### 💡 Example 2:

```java
int i = 0;
while (i < 5) {
    i++;
    if (i == 2)
        continue;
    System.out.println(i);
}
```

---

## ✅ Summary

| Statement        | Use                                    |
| ---------------- | -------------------------------------- |
| `if` / `if-else` | Conditional code execution             |
| `switch-case`    | Multiple branch decision               |
| `for` loop       | Count-controlled looping               |
| `while` loop     | Condition-checked before execution     |
| `do-while`       | Executes first, checks condition later |
| `break`          | Exit loop or switch                    |
| `continue`       | Skip current iteration and go to next  |

---

