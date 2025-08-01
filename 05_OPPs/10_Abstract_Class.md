## 🔷 What is an Abstract Class in Java?

An **abstract class** in Java is a class that **cannot be instantiated** (i.e., you cannot create objects of it).
It is meant to be **inherited** by other classes and can include:

* **Abstract methods** (methods without a body)
* **Non-abstract methods** (regular methods with a body)
* **Constructors**
* **Instance variables and static variables**

---

## 🔑 Key Features:

| Feature                          | Description                         |
| -------------------------------- | ----------------------------------- |
| Declared with `abstract` keyword | `abstract class ClassName {}`       |
| May contain abstract methods     | `abstract void methodName();`       |
| May also contain normal methods  | With full definition                |
| Used for partial abstraction     | Unlike interface (100% abstraction) |
| Can have constructors and fields | Yes                                 |
| Can extend one abstract class    | Java supports single inheritance    |

---

## 🔸 Syntax:

```java
abstract class Animal {
    abstract void sound();  // abstract method

    void eat() {
        System.out.println("This animal eats food.");  // non-abstract method
    }
}
```

---

## ✅ Example 1: Abstract Class with Abstract and Non-Abstract Methods

```java
abstract class Animal {
    abstract void makeSound(); // abstract method

    void sleep() {             // regular method
        System.out.println("Sleeping...");
    }
}

class Dog extends Animal {
    void makeSound() {
        System.out.println("Bark");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog d = new Dog();
        d.makeSound();  // Output: Bark
        d.sleep();      // Output: Sleeping...
    }
}
```

🚫 You **cannot** do this:

```java
Animal a = new Animal(); // ❌ Error: Cannot instantiate abstract class
```

---

## ✅ Example 2: Abstract Class with Constructor and Fields

```java
abstract class Shape {
    String color;

    Shape(String color) {
        this.color = color;
    }

    abstract double area(); // abstract method

    void displayColor() {
        System.out.println("Color: " + color);
    }
}

class Circle extends Shape {
    double radius;

    Circle(String color, double radius) {
        super(color);
        this.radius = radius;
    }

    double area() {
        return 3.14 * radius * radius;
    }
}

public class Test {
    public static void main(String[] args) {
        Circle c = new Circle("Red", 5.0);
        c.displayColor();                     // Color: Red
        System.out.println(c.area());         // Area: 78.5
    }
}
```

---

## 🔄 Difference Between Abstract Class and Interface

| Feature              | Abstract Class                      | Interface                                        |
| -------------------- | ----------------------------------- | ------------------------------------------------ |
| Methods              | Can have both abstract and concrete | Only abstract (Java 7), default/static (Java 8+) |
| Variables            | Can have instance variables         | Only static final variables                      |
| Constructors         | Yes                                 | No                                               |
| Multiple inheritance | Not supported                       | Supported                                        |
| Access Modifiers     | Can be public, protected, private   | All methods are public by default                |
| When to use          | Shared code & partial abstraction   | Full abstraction, multiple sources               |

---

## 🧠 Use Case:

Abstract classes are used when:

* You want to **share common code** (methods/fields) across related classes.
* You want to provide **a base implementation** with some methods needing to be defined in child classes.

---

## ⛔ When *Not* to Use Abstract Class

* When you only need method declarations (use **interfaces** instead).
* When you need **multiple inheritance**.

---
 
