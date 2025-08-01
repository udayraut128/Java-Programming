## 🔒 What is `final` in Java?

The `final` keyword in Java is a **non-access modifier** used to restrict the user:

| Use Case         | Restriction                                        |
| ---------------- | -------------------------------------------------- |
| `final` variable | Value cannot be changed (i.e., becomes a constant) |
| `final` method   | Method cannot be overridden in a subclass          |
| `final` class    | Class cannot be inherited (no subclass allowed)    |

---

## 🔹 1. `final` **Variable** – Constant

When a variable is declared `final`, its **value cannot be reassigned** after initialization.

### 🔸 Example:

```java
public class Example {
    public static void main(String[] args) {
        final int MAX = 100;
        System.out.println("MAX value: " + MAX);

        // MAX = 200;  // ❌ Compile-time error: cannot assign a value to final variable
    }
}
```

🔹 You **must** assign a value to a final variable during declaration or in the constructor (if it's an instance variable).

---

## 🔹 2. `final` **Method** – Cannot Be Overridden

A final method **cannot be overridden** by any subclass. It's useful when you want to **prevent modification of behavior**.

### 🔸 Example:

```java
class Animal {
    final void makeSound() {
        System.out.println("Animal sound");
    }
}

class Dog extends Animal {
    // void makeSound() {  // ❌ Error: Cannot override final method
    //     System.out.println("Dog barks");
    // }
}
```

📝 `final` method can still be **inherited**, but not overridden.

---

## 🔹 3. `final` **Class** – Cannot Be Extended

A final class **cannot have any subclasses**. This is used to **prevent inheritance**.

### 🔸 Example:

```java
final class Car {
    void start() {
        System.out.println("Car is starting");
    }
}

// class SportsCar extends Car {  // ❌ Error: Cannot inherit from final class
// }
```

📝 Commonly used with immutable classes like `String` in Java (`java.lang.String` is a final class).

---

## 🔎 Summary Table

| `final` Used With | Meaning                        |
| ----------------- | ------------------------------ |
| Variable          | Value cannot change (constant) |
| Method            | Cannot be overridden           |
| Class             | Cannot be inherited            |

---

## ✅ Use Cases of `final`:

* Define **constants** (`final static`).
* Prevent method overriding for **security or stability**.
* Make classes **immutable**.
* Ensure **consistent behavior** in inheritance.

---

## 📌 Example: Using all three `final` types

```java
final class Constants {
    final static double PI = 3.14159;

    final void display() {
        System.out.println("This is a final method.");
    }
}

public class Test {
    public static void main(String[] args) {
        Constants obj = new Constants();
        obj.display();
        System.out.println("PI: " + Constants.PI);
    }
}
```

---
 
