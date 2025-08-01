# ✅ **Operators in Java**

Operators in Java are **symbols** that perform operations on **variables and values**. Java provides a rich set of operators to manipulate data.

---

## 🔹 **1. Arithmetic Operators**

Used for performing **basic mathematical operations**.

| Operator | Description         | Example |
| -------- | ------------------- | ------- |
| `+`      | Addition            | `a + b` |
| `-`      | Subtraction         | `a - b` |
| `*`      | Multiplication      | `a * b` |
| `/`      | Division            | `a / b` |
| `%`      | Modulus (Remainder) | `a % b` |

### 💡 Example:

```java
public class ArithmeticExample {
    public static void main(String[] args) {
        int a = 10, b = 3;
        System.out.println("Addition: " + (a + b));
        System.out.println("Modulus: " + (a % b));
    }
}
```

---

## 🔹 **2. Relational (Comparison) Operators**

Used to compare two values.

| Operator | Description           | Example  |
| -------- | --------------------- | -------- |
| `==`     | Equal to              | `a == b` |
| `!=`     | Not equal to          | `a != b` |
| `>`      | Greater than          | `a > b`  |
| `<`      | Less than             | `a < b`  |
| `>=`     | Greater than or equal | `a >= b` |
| `<=`     | Less than or equal    | `a <= b` |

### 💡 Example:

```java
public class RelationalExample {
    public static void main(String[] args) {
        int x = 10, y = 20;
        System.out.println("Is x equal to y? " + (x == y));
    }
}
```

---

## 🔹 **3. Logical Operators**

Used to combine two or more conditions.

| Operator | Description | Example            |            |          |   |          |
| -------- | ----------- | ------------------ | ---------- | -------- | - | -------- |
| `&&`     | Logical AND | `(a > 0 && b > 0)` |            |          |   |          |
| \`       |             | \`                 | Logical OR | \`(a > 0 |   | b > 0)\` |
| `!`      | Logical NOT | `!(a > 0)`         |            |          |   |          |

### 💡 Example:

```java
public class LogicalExample {
    public static void main(String[] args) {
        int a = 5, b = 10;
        System.out.println((a < b) && (b > 0)); // true
    }
}
```

---

## 🔹 **4. Assignment Operators**

Used to assign values to variables.

| Operator | Example  | Equivalent To |
| -------- | -------- | ------------- |
| `=`      | `a = b`  | -             |
| `+=`     | `a += b` | `a = a + b`   |
| `-=`     | `a -= b` | `a = a - b`   |
| `*=`     | `a *= b` | `a = a * b`   |
| `/=`     | `a /= b` | `a = a / b`   |
| `%=`     | `a %= b` | `a = a % b`   |

### 💡 Example:

```java
public class AssignmentExample {
    public static void main(String[] args) {
        int a = 10;
        a += 5;  // a = a + 5
        System.out.println("a = " + a);
    }
}
```

---

## 🔹 **5. Unary Operators**

Operate on a **single operand**.

| Operator | Description          | Example      |
| -------- | -------------------- | ------------ |
| `+`      | Unary plus           | `+a`         |
| `-`      | Unary minus          | `-a`         |
| `++`     | Increment (pre/post) | `++a`, `a++` |
| `--`     | Decrement (pre/post) | `--a`, `a--` |
| `!`      | Logical complement   | `!true`      |

### 💡 Example:

```java
public class UnaryExample {
    public static void main(String[] args) {
        int x = 5;
        System.out.println(++x); // Pre-increment
        System.out.println(x--); // Post-decrement
    }
}
```

---

## 🔹 **6. Bitwise Operators**

Work at the **bit level**.

| Operator | Description        | Example    |     |     |
| -------- | ------------------ | ---------- | --- | --- |
| `&`      | Bitwise AND        | `a & b`    |     |     |
| \`       | \`                 | Bitwise OR | \`a | b\` |
| `^`      | Bitwise XOR        | `a ^ b`    |     |     |
| `~`      | Bitwise Complement | `~a`       |     |     |
| `<<`     | Left shift         | `a << 2`   |     |     |
| `>>`     | Right shift        | `a >> 2`   |     |     |

### 💡 Example:

```java
public class BitwiseExample {
    public static void main(String[] args) {
        int a = 5, b = 3;
        System.out.println("a & b = " + (a & b)); // 1
        System.out.println("a << 1 = " + (a << 1)); // 10
    }
}
```

---

## 🔹 **7. Ternary Operator**

A shorthand for `if-else` statements.

### **Syntax:**

```java
condition ? expression1 : expression2
```

### 💡 Example:

```java
public class TernaryExample {
    public static void main(String[] args) {
        int a = 10, b = 20;
        int max = (a > b) ? a : b;
        System.out.println("Max: " + max);
    }
}
```

---

## 🔹 **8. instanceof Operator**

Used to test whether an object is an instance of a specific class or subclass.

### 💡 Example:

```java
public class InstanceofExample {
    public static void main(String[] args) {
        String s = "Hello";
        System.out.println(s instanceof String); // true
    }
}
```

---

## 🔹 **9. Type Cast Operator**

Used to explicitly convert one data type to another.

### 💡 Example:

```java
public class CastingOperator {
    public static void main(String[] args) {
        double d = 10.5;
        int i = (int) d;  // Explicit casting
        System.out.println("i = " + i);
    }
}
```

---

## Summary Table:

| Category   | Operators                         |                           |         |
| ---------- | --------------------------------- | ------------------------- | ------- |
| Arithmetic | `+`, `-`, `*`, `/`, `%`           |                           |         |
| Relational | `==`, `!=`, `>`, `<`, `>=`, `<=`  |                           |         |
| Logical    | `&&`, \`                          |                           | `, `!\` |
| Assignment | `=`, `+=`, `-=`, `*=`, `/=`, `%=` |                           |         |
| Unary      | `+`, `-`, `++`, `--`, `!`         |                           |         |
| Bitwise    | `&`, \`                           | `, `^`, `\~`, `<<`, `>>\` |         |
| Ternary    | `? :`                             |                           |         |
| instanceof | `object instanceof ClassName`     |                           |         |
| Type Cast  | `(dataType) variable`             |                           |         |

---

Let me know if you'd like a quiz, summary chart, or continue with the next topic:
**4. Control Structures in Java (if, switch, loops, etc.)** ✅
