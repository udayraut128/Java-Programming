## 🔷 3. Object-Oriented Programming: **Polymorphism in Java**

### ✅ What is Polymorphism?

The word **"Polymorphism"** means **"many forms."**
In Java, polymorphism allows one **interface** or method to behave **differently based on the context.**

There are two types of polymorphism in Java:

| Type                          | Achieved Through                |
| ----------------------------- | ------------------------------- |
| **Compile-time Polymorphism** | Method Overloading              |
| **Runtime Polymorphism**      | Method Overriding (Inheritance) |

---

## 🔹 1. Compile-time Polymorphism (Method Overloading)

### 📌 Definition:

When **multiple methods** in the **same class** have the **same name but different parameters**, it is called **method overloading**.

### ✅ Example:

```java
class MathOperations {
    // Method with 1 parameter
    int add(int a) {
        return a + 10;
    }

    // Method with 2 parameters
    int add(int a, int b) {
        return a + b;
    }

    // Method with 3 parameters
    int add(int a, int b, int c) {
        return a + b + c;
    }
}

public class Main {
    public static void main(String[] args) {
        MathOperations op = new MathOperations();
        System.out.println(op.add(5));           // Output: 15
        System.out.println(op.add(5, 10));       // Output: 15
        System.out.println(op.add(5, 10, 15));   // Output: 30
    }
}
```

### 🔍 Key Notes:

* The method name is the same: `add()`
* Number or type of parameters differ.
* Decision is made **at compile time** → hence **compile-time polymorphism**

---

## 🔹 2. Runtime Polymorphism (Method Overriding)

### 📌 Definition:

When a **subclass** provides a **specific implementation** of a method that is already defined in its **parent class**, it’s called **method overriding**.

### ✅ Example:

```java
class Animal {
    void sound() {
        System.out.println("Animal makes sound");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Dog barks");
    }
}

class Cat extends Animal {
    @Override
    void sound() {
        System.out.println("Cat meows");
    }
}

public class Test {
    public static void main(String[] args) {
        Animal a1 = new Dog();  // Parent reference → Dog object
        Animal a2 = new Cat();  // Parent reference → Cat object

        a1.sound();  // Output: Dog barks
        a2.sound();  // Output: Cat meows
    }
}
```

### 🔍 Key Notes:

* Method name and parameters are the **same**
* Method is **overridden** in subclass
* Decision is made **at runtime** → hence **runtime polymorphism**

---

## 🎯 Why Use Polymorphism?

| Benefit              | Description                                      |
| -------------------- | ------------------------------------------------ |
| **Code Reusability** | Same method name can handle different data types |
| **Maintainability**  | Easier to manage and scale code                  |
| **Flexibility**      | One interface, multiple implementations          |
| **Extensibility**    | Easier to add new behavior using inheritance     |

---

### ✅ Example 3: Polymorphism via Interfaces

```java
interface Shape {
    void draw();
}

class Circle implements Shape {
    public void draw() {
        System.out.println("Drawing Circle");
    }
}

class Square implements Shape {
    public void draw() {
        System.out.println("Drawing Square");
    }
}

public class Demo {
    public static void main(String[] args) {
        Shape s;

        s = new Circle();  // Interface reference to Circle object
        s.draw();          // Output: Drawing Circle

        s = new Square();  // Interface reference to Square object
        s.draw();          // Output: Drawing Square
    }
}
```

---

## 🧠 Summary

| Type         | Method Used        | Resolved At  | Example                                |
| ------------ | ------------------ | ------------ | -------------------------------------- |
| Compile-time | Method Overloading | Compile-time | `add(int)`, `add(int, int)`            |
| Runtime      | Method Overriding  | Runtime      | Subclass overriding superclass methods |

---
 
