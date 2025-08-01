# ✅ 7. Java Packages

A **package** in Java is a namespace that organizes a set of related classes and interfaces. Think of it like a folder on your computer.

---

## 🔸 Why Use Packages?

* Avoid **name conflicts**
* Easier to **manage and maintain** code
* Provides **access control**
* Can reuse classes from built-in and custom libraries

---

## 🔹 Types of Packages

### 1. **Built-in Packages**

Java provides many built-in packages such as:

| Package     | Description                                                     |
| ----------- | --------------------------------------------------------------- |
| `java.lang` | Core classes (String, Math, Object, etc.) – imported by default |
| `java.util` | Utility classes (ArrayList, Date, HashMap, etc.)                |
| `java.io`   | Input/output classes (File, BufferedReader, etc.)               |
| `java.net`  | Networking classes                                              |
| `java.sql`  | JDBC and database interaction                                   |

### ✅ Example: Using `java.util.ArrayList`

```java
import java.util.ArrayList;

public class BuiltInExample {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<>();
        list.add("Java");
        list.add("Python");
        System.out.println(list);
    }
}
```

---

### 2. **User-defined Packages**

You can create your own package by using the `package` keyword.

### ✅ Steps to create a user-defined package:

#### a) Create the Package File

```java
// File: mypack/Message.java
package mypack;

public class Message {
    public void greet() {
        System.out.println("Hello from mypack!");
    }
}
```

#### b) Compile it from outside the `mypack` directory:

```bash
javac mypack/Message.java
```

#### c) Use the package in another class:

```java
// File: TestMessage.java
import mypack.Message;

public class TestMessage {
    public static void main(String[] args) {
        Message m = new Message();
        m.greet();
    }
}
```

#### d) Compile and run:

```bash
javac TestMessage.java
java TestMessage
```

---

## 🔹 Importing Packages

| Syntax                      | Description                      |
| --------------------------- | -------------------------------- |
| `import package.ClassName;` | Imports a specific class         |
| `import package.*;`         | Imports all classes in a package |

### ✅ Example:

```java
import java.util.Scanner;

public class ImportExample {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter your name: ");
        String name = sc.nextLine();
        System.out.println("Hello " + name);
    }
}
```

---

## 🔹 Accessing Classes from Packages

* Classes from other packages need to be `public`.
* You must use the fully qualified name if you don’t import.

### ✅ Without `import`:

```java
public class Test {
    public static void main(String[] args) {
        java.util.Date date = new java.util.Date();
        System.out.println(date);
    }
}
```

---

## ✅ Summary

| Concept                   | Description                                        |
| ------------------------- | -------------------------------------------------- |
| **Built-in Packages**     | Provided by Java (e.g., `java.util`, `java.io`)    |
| **User-defined Packages** | Created using `package` keyword                    |
| **Importing**             | `import` keyword used to bring packages into scope |
| **Accessing Classes**     | Use either `import` or fully qualified class name  |

---
 
