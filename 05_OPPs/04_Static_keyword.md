# ✅ `static` Keyword in Java

The `static` keyword in Java is used for memory management. It can be applied to:

* Variables
* Methods
* Blocks
* Nested Classes

It belongs to the **class** rather than instances (objects), so memory is allocated **only once**.

---

## 🔹 1. Static Variable

A **static variable** is shared among all instances of a class.

### ✅ Example:

```java
class Student {
    int id;
    String name;
    static String college = "ABC College"; // shared by all objects

    Student(int id, String name) {
        this.id = id;
        this.name = name;
    }

    void display() {
        System.out.println(id + " " + name + " " + college);
    }
}

public class Main {
    public static void main(String[] args) {
        Student s1 = new Student(1, "Bablu");
        Student s2 = new Student(2, "Amit");

        s1.display();
        s2.display();
    }
}
```

### 💡 Output:

```
1 Bablu ABC College  
2 Amit ABC College
```

✅ **Note**: Only one copy of `college` is created and shared among all objects.

---

## 🔹 2. Static Method

A **static method** belongs to the class, not an object. It can be called **without creating an object**.

### ✅ Rules:

* Can access **only static data**.
* Can call **only other static methods**.
* Cannot use `this` or `super`.

### ✅ Example:

```java
class Utility {
    static int square(int x) {
        return x * x;
    }
}

public class Main {
    public static void main(String[] args) {
        int result = Utility.square(5); // no object needed
        System.out.println("Square: " + result);
    }
}
```

### 💡 Output:

```
Square: 25
```

---

## 🔹 3. Static Block

A **static block** is used to initialize static variables. It runs **once** when the class is loaded.

### ✅ Example:

```java
class Test {
    static int x;

    static {
        x = 10;
        System.out.println("Static block initialized");
    }

    static void show() {
        System.out.println("x = " + x);
    }
}

public class Main {
    public static void main(String[] args) {
        Test.show(); // static block runs before this
    }
}
```

### 💡 Output:

```
Static block initialized  
x = 10
```

---

## ✅ Summary Table

| Feature           | Description                        |
| ----------------- | ---------------------------------- |
| `static variable` | Shared across all objects          |
| `static method`   | Can be called without object       |
| `static block`    | Executes once when class is loaded |

---

## 🔸 Real-life Analogy

Think of a **classroom**:

* `static variable`: the **whiteboard** shared by all students.
* `static method`: the **teacher's instructions** (common for all).
* `static block`: the **preparation** done before students enter.

---
 