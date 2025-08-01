## ✅ 1. Method Overloading in Java

### 🔹 Definition:

**Method Overloading** means defining multiple methods with the **same name** in a class but with **different parameters** (number, type, or order of parameters).

### 🔸 Key Points:

* Happens **within the same class**
* Return type can be different but **not enough** to overload a method
* Compile-time polymorphism (also called **static polymorphism**)

---

### ✅ Example 1: Varying number of parameters

```java
class Calculator {
    int add(int a, int b) {
        return a + b;
    }

    int add(int a, int b, int c) {
        return a + b + c;
    }
}

public class Main {
    public static void main(String[] args) {
        Calculator calc = new Calculator();
        System.out.println("Sum = " + calc.add(10, 20));      // Output: 30
        System.out.println("Sum = " + calc.add(10, 20, 30));  // Output: 60
    }
}
```

---

### ✅ Example 2: Varying data types

```java
class Display {
    void show(String msg) {
        System.out.println("Message: " + msg);
    }

    void show(int number) {
        System.out.println("Number: " + number);
    }
}

public class Main {
    public static void main(String[] args) {
        Display d = new Display();
        d.show("Bablu");
        d.show(100);
    }
}
```

---

## ✅ 2. Constructor Overloading in Java

### 🔹 Definition:

**Constructor Overloading** means having **more than one constructor** in a class with **different parameter lists**.

---

### 🔸 Why use it?

* To create objects with **different initializations**
* Helps improve **code flexibility and readability**

---

### ✅ Example:

```java
class Student {
    String name;
    int age;

    // Default constructor
    Student() {
        name = "Unknown";
        age = 0;
    }

    // Parameterized constructor
    Student(String n, int a) {
        name = n;
        age = a;
    }

    void display() {
        System.out.println("Name: " + name + ", Age: " + age);
    }
}

public class Main {
    public static void main(String[] args) {
        Student s1 = new Student();             // default constructor
        Student s2 = new Student("Amit", 21);   // parameterized constructor

        s1.display();  // Output: Name: Unknown, Age: 0
        s2.display();  // Output: Name: Amit, Age: 21
    }
}
```

---

## ✅ Differences between Method Overloading and Constructor Overloading

| Feature       | Method Overloading                     | Constructor Overloading                 |
| ------------- | -------------------------------------- | --------------------------------------- |
| Purpose       | Perform different tasks with same name | Initialize objects differently          |
| Return Type   | Can be same or different               | No return type (constructors have none) |
| Explicit call | Called explicitly by method name       | Called automatically on object creation |
| Example use   | `add(int a, int b)`, `add(double a)`   | `Student()`, `Student(String name)`     |

---
  