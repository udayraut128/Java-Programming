# ✅ 3. Object-Oriented Programming (OOP)

### Core OOP concepts:

* **Classes** and **Objects**
* (We’ll cover other OOP principles—like inheritance, polymorphism, abstraction, encapsulation—in upcoming topics.)

---

## 🔹 **Classes and Objects in Java**

---

### 🔸 What is a Class?

A **class** is a **blueprint** or **template** for creating objects. It defines:

* **Properties** (variables/data members)
* **Behaviors** (methods/functions)

#### ➤ Syntax:

```java
class ClassName {
    // data members (variables)
    // methods (functions)
}
```

---

### 🔸 What is an Object?

An **object** is an **instance** of a class. When you create an object, memory is allocated for it.

#### ➤ Syntax:

```java
ClassName obj = new ClassName(); // object creation
```

---

## ✅ Example 1: Basic Class and Object

```java
class Student {
    // data members
    int id;
    String name;

    // method
    void display() {
        System.out.println("ID: " + id);
        System.out.println("Name: " + name);
    }
}

public class Main {
    public static void main(String[] args) {
        Student s1 = new Student();  // object 1
        s1.id = 101;
        s1.name = "Bablu";
        s1.display();

        Student s2 = new Student();  // object 2
        s2.id = 102;
        s2.name = "Rahul";
        s2.display();
    }
}
```

### 💡 Output:

```
ID: 101
Name: Bablu
ID: 102
Name: Rahul
```

---

## ✅ Example 2: Class with Method performing Action

```java
class Calculator {
    // method to add two numbers
    void add(int a, int b) {
        int result = a + b;
        System.out.println("Sum: " + result);
    }
}

public class Main {
    public static void main(String[] args) {
        Calculator calc = new Calculator();
        calc.add(10, 20);   // Sum: 30
        calc.add(5, 15);    // Sum: 20
    }
}
```

---

## ✅ Example 3: Constructor Usage in Class

```java
class Car {
    String model;
    int year;

    // Constructor
    Car(String m, int y) {
        model = m;
        year = y;
    }

    void showDetails() {
        System.out.println("Model: " + model + ", Year: " + year);
    }
}

public class Main {
    public static void main(String[] args) {
        Car c1 = new Car("Honda City", 2020);
        Car c2 = new Car("Tata Nexon", 2022);

        c1.showDetails();
        c2.showDetails();
    }
}
```

### 💡 Output:

```
Model: Honda City, Year: 2020
Model: Tata Nexon, Year: 2022
```

---

## ✅ Key Points Summary:

| Term        | Meaning               |
| ----------- | --------------------- |
| `class`     | Blueprint or template |
| `object`    | Instance of a class   |
| Constructor | Initializes object    |
| Method      | Function inside class |

---

 