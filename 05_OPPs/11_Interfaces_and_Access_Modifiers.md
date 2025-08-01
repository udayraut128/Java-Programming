## ✅ **1. Interfaces in Java**

### 🔷 What is an Interface?

An **interface** in Java is a **blueprint** of a class that contains **only abstract methods** (until Java 7), and can also have **default/static methods** (from Java 8) and **private methods** (from Java 9).

You cannot create objects of an interface. A class **implements** an interface to define its behavior.

---

### 🔑 Key Points:

* Declared using `interface` keyword.
* Methods are **implicitly abstract** and **public** (in Java 7).
* Variables in interfaces are **public static final** (constants).
* Supports **multiple inheritance** (a class can implement multiple interfaces).
* Interfaces provide **100% abstraction**.

---

### 🔸 Syntax:

```java
interface Vehicle {
    void start();  // public & abstract by default
}
```

```java
class Car implements Vehicle {
    public void start() {
        System.out.println("Car started");
    }
}
```

---

### ✅ Example 1: Basic Interface Implementation

```java
interface Animal {
    void makeSound();  // abstract method
}

class Cat implements Animal {
    public void makeSound() {
        System.out.println("Meow");
    }
}

public class Main {
    public static void main(String[] args) {
        Cat c = new Cat();
        c.makeSound();  // Output: Meow
    }
}
```

---

### ✅ Example 2: Interface with Multiple Inheritance

```java
interface A {
    void show();
}

interface B {
    void display();
}

class Test implements A, B {
    public void show() {
        System.out.println("Show from A");
    }

    public void display() {
        System.out.println("Display from B");
    }
}

public class Main {
    public static void main(String[] args) {
        Test t = new Test();
        t.show();      // Show from A
        t.display();   // Display from B
    }
}
```

---

### ✅ Example 3: Default Method (Java 8+)

```java
interface Greet {
    default void sayHello() {
        System.out.println("Hello!");
    }
}

class User implements Greet {}

public class Main {
    public static void main(String[] args) {
        User u = new User();
        u.sayHello();  // Output: Hello!
    }
}
```

---

### 🆚 Interface vs Abstract Class

| Feature      | Interface                                                     | Abstract Class         |
| ------------ | ------------------------------------------------------------- | ---------------------- |
| Inheritance  | Multiple (via `implements`)                                   | Single (via `extends`) |
| Methods      | Only abstract (till Java 7), default/static/private (Java 8+) | Can have both          |
| Variables    | `public static final` only                                    | Any type               |
| Constructors | ❌ No                                                          | ✅ Yes                  |
| When to Use  | Full abstraction                                              | Partial abstraction    |

---

## ✅ **2. Access Modifiers in Java**

### 🔷 What are Access Modifiers?

Access modifiers in Java **control the visibility** (access level) of **classes, methods, variables, and constructors**.

---

### 🔑 Four Types of Access Modifiers:

| Modifier    | Same Class | Same Package | Subclass | Other Packages |
| ----------- | ---------- | ------------ | -------- | -------------- |
| `private`   | ✅          | ❌            | ❌        | ❌              |
| `default`   | ✅          | ✅            | ❌        | ❌              |
| `protected` | ✅          | ✅            | ✅        | ❌              |
| `public`    | ✅          | ✅            | ✅        | ✅              |

---

### ✅ Example:

```java
public class Example {
    public int a = 1;         // accessible everywhere
    protected int b = 2;      // accessible in subclass or same package
    int c = 3;                // default (package-private)
    private int d = 4;        // only inside this class

    void display() {
        System.out.println(a);  // 1
        System.out.println(b);  // 2
        System.out.println(c);  // 3
        System.out.println(d);  // 4
    }
}
```

---

### 🔸 Access Outside the Class:

```java
public class Test {
    public static void main(String[] args) {
        Example obj = new Example();
        System.out.println(obj.a);  // ✅
        System.out.println(obj.b);  // ⚠️ If same package
        System.out.println(obj.c);  // ⚠️ If same package
        // System.out.println(obj.d);  // ❌ Error (private)
    }
}
```

---

