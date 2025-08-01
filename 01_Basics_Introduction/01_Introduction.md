# **1. Introduction to Java**

## **➤ History of Java**

Java was developed by **James Gosling** and his team at **Sun Microsystems** in **1995**. Initially called **Oak**, it was renamed to Java (inspired by Java coffee). It was designed to be **platform-independent**, secure, and easy to use for internet-based applications.

* In 2009, Sun Microsystems was acquired by Oracle Corporation.
* Java is now one of the most widely used programming languages for mobile, desktop, and web applications.

---

## **➤ Features of Java**

Here are the main features of Java with brief explanations:

| Feature                  | Description                                                                                             |
| ------------------------ | ------------------------------------------------------------------------------------------------------- |
| **Platform Independent** | Java code is compiled into bytecode, which can run on any system with a JVM (Write Once, Run Anywhere). |
| **Object-Oriented**      | Everything in Java is treated as an object (class-based design).                                        |
| **Simple**               | Syntax is clean and easy to understand (similar to C/C++).                                              |
| **Secure**               | Java does not support pointers and provides a secure runtime environment.                               |
| **Robust**               | Strong memory management and exception handling make Java reliable.                                     |
| **Multithreaded**        | Supports multithreading (running multiple threads simultaneously).                                      |
| **Portable**             | Java bytecode can be transferred and executed on any platform.                                          |
| **High Performance**     | Uses Just-In-Time (JIT) compiler for high performance.                                                  |
| **Dynamic**              | Supports runtime polymorphism, dynamic loading of classes, etc.                                         |
| **Distributed**          | Built-in support for distributed computing with packages like `java.net` and RMI.                       |

---

## **➤ JDK, JRE, and JVM**

| Component                          | Description                                                                                               |
| ---------------------------------- | --------------------------------------------------------------------------------------------------------- |
| **JVM (Java Virtual Machine)**     | Executes Java bytecode (.class files). It makes Java platform-independent.                                |
| **JRE (Java Runtime Environment)** | Provides the libraries + JVM to run Java programs.                                                        |
| **JDK (Java Development Kit)**     | Includes JRE + compiler (`javac`), debugger, and development tools. It’s needed to develop Java programs. |

**Diagram:**

```
        [ Your Java Code ] 
                ↓
           javac (Compiler)
                ↓
        [ Bytecode (.class) ]
                ↓
           JVM executes it
                ↓
       Program runs on any OS
```

---

## **➤ Java Program Structure**

A typical Java program structure looks like this:

```java
// Filename: HelloWorld.java

public class HelloWorld {   // Class Declaration
    public static void main(String[] args) {  // Main Method
        System.out.println("Hello, Java!");   // Statement
    }
}
```

### Structure Breakdown:

* `class HelloWorld` – Everything must be in a class.
* `public static void main(String[] args)` – Entry point for the program.
* `System.out.println(...)` – Prints output to the console.

---

## **➤ First Java Program: Hello World**

### Step 1: Write the code

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, Java!");
    }
}
```

### Step 2: Compile

Open terminal/command prompt and run:

```
javac HelloWorld.java
```

### Step 3: Run

```
java HelloWorld
```

**Output:**

```
Hello, Java!
```

---
 