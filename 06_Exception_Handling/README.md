# 💥 5. **Exception Handling in Java**

Exception handling allows a program to deal with **runtime errors** gracefully **without crashing**.

---

## 🔹 What is an Exception?

An **exception** is an **abnormal condition** or **error** that disrupts the normal flow of execution.

---

## ✅ **Types of Exceptions**

Java exceptions fall into two main categories:

| Type                     | Description                 | Examples                                      |
| ------------------------ | --------------------------- | --------------------------------------------- |
| **Checked Exceptions**   | Checked at **compile time** | `IOException`, `SQLException`                 |
| **Unchecked Exceptions** | Checked at **runtime**      | `NullPointerException`, `ArithmeticException` |

---

## 🔹 **Try, Catch, Finally**

### ✅ Syntax:

```java
try {
    // risky code
} catch (ExceptionType e) {
    // handle exception
} finally {
    // cleanup code (always runs)
}
```

### ✅ Example:

```java
public class TryCatchExample {
    public static void main(String[] args) {
        try {
            int a = 10 / 0;  // ArithmeticException
        } catch (ArithmeticException e) {
            System.out.println("Error: " + e.getMessage());
        } finally {
            System.out.println("This block always executes.");
        }
    }
}
```

---

## 🔹 **Throw vs Throws**

### ✅ `throw`: Used to **manually throw** an exception.

```java
throw new ArithmeticException("Divide by zero");
```

### ✅ `throws`: Declares exceptions that a method **might throw**.

```java
void readFile() throws IOException {
    // code that might throw IOException
}
```

### ✅ Example:

```java
public class ThrowThrowsExample {
    static void checkAge(int age) throws Exception {
        if (age < 18) {
            throw new Exception("Age must be 18+");
        }
        System.out.println("You are allowed.");
    }

    public static void main(String[] args) {
        try {
            checkAge(16);
        } catch (Exception e) {
            System.out.println(e.getMessage());
        }
    }
}
```

---

## 🔹 **Multiple Catch Blocks**

Handle different exceptions **separately**.

```java
public class MultipleCatch {
    public static void main(String[] args) {
        try {
            int a = 5 / 0;
            int[] arr = new int[3];
            arr[5] = 10;
        } catch (ArithmeticException e) {
            System.out.println("Arithmetic error: " + e);
        } catch (ArrayIndexOutOfBoundsException e) {
            System.out.println("Array error: " + e);
        }
    }
}
```

---

## 🔹 **Nested Try**

A `try` block inside another `try`.

```java
public class NestedTry {
    public static void main(String[] args) {
        try {
            try {
                int a = 10 / 0;
            } catch (ArithmeticException e) {
                System.out.println("Inner catch: " + e);
            }

            String str = null;
            System.out.println(str.length());
        } catch (NullPointerException e) {
            System.out.println("Outer catch: " + e);
        }
    }
}
```

---

## 🔹 **Custom Exceptions**

You can create your **own exception class** by extending `Exception`.

### ✅ Example:

```java
class MyException extends Exception {
    public MyException(String msg) {
        super(msg);
    }
}

public class CustomExceptionExample {
    static void validate(int marks) throws MyException {
        if (marks < 40) {
            throw new MyException("Failing Marks!");
        }
    }

    public static void main(String[] args) {
        try {
            validate(35);
        } catch (MyException e) {
            System.out.println("Caught: " + e.getMessage());
        }
    }
}
```

---

## 🔹 **Checked vs Unchecked Exceptions**

| Feature                   | Checked Exception             | Unchecked Exception                                      |
| ------------------------- | ----------------------------- | -------------------------------------------------------- |
| Checked at compile time   | ✅ Yes                         | ❌ No                                                     |
| Needs try-catch or throws | ✅ Yes                         | ❌ Optional                                               |
| Examples                  | `IOException`, `SQLException` | `NullPointerException`, `ArrayIndexOutOfBoundsException` |

---

## ✅ Summary

* **`try-catch-finally`**: Core structure to handle exceptions
* **`throw` vs `throws`**: Throw exception vs declare possible exception
* **Custom exceptions**: User-defined error handling
* **Checked**: Compile-time; **Unchecked**: Runtime

---

