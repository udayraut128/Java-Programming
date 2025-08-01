# ✅ 16. Java Tools and Compilation

Java provides a set of **command-line tools** that allow you to compile, run, document, analyze, and package Java programs. These tools are part of the **JDK (Java Development Kit)**.

---

## 🔹 1. `javac` — Java Compiler

### ✅ Purpose:

Compiles `.java` source files into `.class` bytecode files.

### ✅ Syntax:

```bash
javac MyProgram.java
```

### ✅ Example:

```java
// File: Hello.java
public class Hello {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

```bash
javac Hello.java  // Compiles into Hello.class
```

---

## 🔹 2. `java` — Java Launcher

### ✅ Purpose:

Launches the Java application using the compiled `.class` file.

### ✅ Syntax:

```bash
java ClassName
```

### ✅ Example:

```bash
java Hello  // Runs Hello.class and prints "Hello, World!"
```

> ⚠️ Do not include the `.class` extension while running the program.

---

## 🔹 3. `jar` — Java Archive Tool

### ✅ Purpose:

Packages multiple `.class` files and resources into a single **.jar (Java Archive)** file.

### ✅ Syntax:

```bash
jar cf MyApp.jar *.class
```

* `c`: create archive
* `f`: specify archive file name

### ✅ Example:

```bash
jar cf HelloApp.jar Hello.class
```

### ✅ Running a `.jar`:

```bash
java -jar HelloApp.jar
```

> You need a `MANIFEST.MF` with `Main-Class: Hello` to run it this way.

---

## 🔹 4. `javadoc` — Java Documentation Generator

### ✅ Purpose:

Generates HTML documentation from Java source code using comments.

### ✅ JavaDoc Comment Syntax:

```java
/**
 * This class demonstrates Hello World.
 * @author Bablu
 */
public class Hello {
    /**
     * This method prints a message.
     */
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

### ✅ Command:

```bash
javadoc Hello.java
```

> This creates HTML files with documentation.

---

## 🔹 5. `javap` — Java Class Disassembler

### ✅ Purpose:

Shows the **bytecode structure** of a `.class` file (methods, variables, etc.).

### ✅ Example:

```bash
javap Hello
```

### ✅ Output:

```
Compiled from "Hello.java"
public class Hello {
  public Hello();
  public static void main(java.lang.String[]);
}
```

---

## 🔹 6. Setting `CLASSPATH`

### ✅ What is it?

`CLASSPATH` tells Java where to find `.class` or `.jar` files during compilation and execution.

### ✅ Temporarily:

```bash
javac -classpath /path/to/library.jar MyApp.java
```

```bash
java -classpath .:/path/to/library.jar MyApp
```

### ✅ Permanently:

Set in environment variables:

* Windows:

  ```cmd
  set CLASSPATH=.;C:\libs\myLib.jar
  ```
* Linux/macOS:

  ```bash
  export CLASSPATH=.:/home/user/libs/myLib.jar
  ```

> `.` refers to the current directory.

---

## 🔹 7. Command-Line Arguments

### ✅ What are they?

Arguments passed to the `main()` method from the command line.

### ✅ Syntax:

```bash
java Hello arg1 arg2
```

### ✅ Code Example:

```java
public class CommandLineArgs {
    public static void main(String[] args) {
        for (int i = 0; i < args.length; i++) {
            System.out.println("Arg " + i + ": " + args[i]);
        }
    }
}
```

### ✅ Output:

```bash
java CommandLineArgs Java GPT Chat
```

```
Arg 0: Java
Arg 1: GPT
Arg 2: Chat
```

---

## ✅ Summary Table

| Tool        | Use                                |
| ----------- | ---------------------------------- |
| `javac`     | Compile `.java` to `.class` files  |
| `java`      | Run Java bytecode                  |
| `jar`       | Package files into `.jar` archives |
| `javadoc`   | Generate documentation             |
| `javap`     | Disassemble `.class` files         |
| `CLASSPATH` | Set location for classes and jars  |

---

