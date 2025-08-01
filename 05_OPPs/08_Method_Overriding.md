## ✅ What is Method Overriding?

**Method Overriding** occurs when a **subclass provides a specific implementation** of a method that is already defined in its **superclass**.

> The overridden method in the subclass must have the **same name, return type, and parameters** as in the superclass.

---

## 🔸 Key Rules of Method Overriding:

| Rule                     | Description                                                         |
| ------------------------ | ------------------------------------------------------------------- |
| 🟦 Same Method Signature | Method name and parameter list must be the same.                    |
| 🟩 Inheritance Required  | There must be a **parent-child** relationship.                      |
| 🟨 Access Modifier       | The subclass method must have **same or more accessible** modifier. |
| 🟥 No Static Methods     | Static methods **cannot be overridden**, they are hidden.           |
| 🟧 No Private Methods    | Private methods **can’t be overridden** (they are not inherited).   |
| 🟫 Use of `@Override`    | Optional but recommended to indicate overriding.                    |

---

## 🧪 Example 1: Simple Method Overriding

```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Dog extends Animal {
    @Override
    void sound() {
        System.out.println("Dog barks");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal a = new Dog();  // Upcasting
        a.sound();             // Calls overridden method in Dog
    }
}
```

### ✅ Output:

```
Dog barks
```

---

## 🧪 Example 2: Without Overriding

```java
class Animal {
    void sound() {
        System.out.println("Animal makes a sound");
    }
}

class Cat extends Animal {
    // No overriding
}

public class Main {
    public static void main(String[] args) {
        Cat c = new Cat();
        c.sound();   // Calls Animal's method
    }
}
```

### ✅ Output:

```
Animal makes a sound
```

---

## 🧪 Example 3: Using `super` to call parent method

```java
class Vehicle {
    void start() {
        System.out.println("Vehicle is starting");
    }
}

class Car extends Vehicle {
    @Override
    void start() {
        super.start();  // Call parent method
        System.out.println("Car is starting");
    }
}

public class Main {
    public static void main(String[] args) {
        Car c = new Car();
        c.start();
    }
}
```

### ✅ Output:

```
Vehicle is starting
Car is starting
```

---

## ✅ When to Use Method Overriding?

Use method overriding when:

* You want **polymorphic behavior** (different behavior for the same method in different classes).
* You want to **customize or extend functionality** of an inherited method.
* You’re implementing **frameworks or templates** that expect certain methods to be overridden.

---

## 🧱 Difference Between Method Overloading vs Method Overriding:

| Feature            | Method Overloading    | Method Overriding                                  |
| ------------------ | --------------------- | -------------------------------------------------- |
| Class Relationship | Same class            | Requires Inheritance                               |
| Parameters         | Must be different     | Must be same                                       |
| Return Type        | Can be different      | Must be same or covariant                          |
| Polymorphism Type  | Compile-time (Static) | Runtime (Dynamic)                                  |
| Access             | No restriction        | Subclass method must be equally or more accessible |

---
 
