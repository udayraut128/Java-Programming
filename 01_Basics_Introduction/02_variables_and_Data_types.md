# **2. Java Basics**

## ➤ **Data Types in Java**

Java is a **strongly typed** language. This means that every variable must be declared with a **data type** before use. Java provides two categories of data types:

### **A. Primitive Data Types**

These are the most basic data types and are not objects.

| Data Type | Size    | Example                | Description                          |
| --------- | ------- | ---------------------- | ------------------------------------ |
| `byte`    | 1 byte  | `byte a = 100;`        | Whole numbers from -128 to 127       |
| `short`   | 2 bytes | `short s = 10000;`     | Whole numbers from -32,768 to 32,767 |
| `int`     | 4 bytes | `int i = 123456;`      | Common integer type                  |
| `long`    | 8 bytes | `long l = 123456789L;` | Very large whole numbers             |
| `float`   | 4 bytes | `float f = 10.5f;`     | Decimal numbers (single precision)   |
| `double`  | 8 bytes | `double d = 20.99;`    | Decimal numbers (double precision)   |
| `char`    | 2 bytes | `char c = 'A';`        | A single character (Unicode)         |
| `boolean` | 1 bit   | `boolean flag = true;` | Only `true` or `false`               |

---

### **B. Non-Primitive (Reference) Data Types**

* **String** – A sequence of characters (e.g., `"Hello"`).
* **Arrays** – A collection of values of the same type.
* **Classes, Interfaces, Enums** – User-defined or built-in complex types.

---

### **Examples of Data Types:**

```java
public class DataTypesExample {
    public static void main(String[] args) {
        int age = 25;
        float height = 5.9f;
        char grade = 'A';
        boolean passed = true;
        String name = "Bablu";

        System.out.println("Name: " + name);
        System.out.println("Age: " + age);
        System.out.println("Height: " + height);
        System.out.println("Grade: " + grade);
        System.out.println("Passed: " + passed);
    }
}
```

**Output:**

```
Name: Bablu
Age: 25
Height: 5.9
Grade: A
Passed: true
```

---

## ➤ **Variables in Java**

A **variable** is a name given to a memory location. In Java, variables are **containers** that hold data during program execution.

### **Types of Variables:**

| Type                                 | Description                                                                                   |
| ------------------------------------ | --------------------------------------------------------------------------------------------- |
| **Local Variable**                   | Declared inside a method or block. Only accessible within that scope.                         |
| **Instance Variable**                | Non-static variable, declared inside a class but outside any method. Associated with objects. |
| **Static Variable (Class Variable)** | Declared with `static`. Shared among all instances of the class.                              |

---

### **Variable Declaration Syntax:**

```java
data_type variable_name = value;
```

### **Examples:**

```java
public class VariableExample {
    // instance variable
    int instanceVar = 10;

    // static variable
    static String course = "Java";

    public void display() {
        // local variable
        String name = "Bablu";
        System.out.println("Name: " + name);
        System.out.println("InstanceVar: " + instanceVar);
        System.out.println("Course: " + course);
    }

    public static void main(String[] args) {
        VariableExample obj = new VariableExample();
        obj.display();
    }
}
```

**Output:**

```
Name: Bablu
InstanceVar: 10
Course: Java
```

---

