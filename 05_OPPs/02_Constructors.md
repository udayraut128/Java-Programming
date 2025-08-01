# ✅ 4. Constructors in Java

A **constructor** in Java is a special method used to **initialize objects**. It is called **automatically** when an object is created.

---

## 🔹 Characteristics of Constructors:

| Feature                  | Description                                |
| ------------------------ | ------------------------------------------ |
| Name                     | Same as the class name                     |
| Return type              | No return type (not even `void`)           |
| Called using             | `new` keyword during object creation       |
| Can be overloaded        | Yes                                        |
| Default provided by Java | Yes, if no constructor is defined manually |

---

## 🔸 Types of Constructors:

1. **Default Constructor**
2. **Parameterized Constructor**
3. **Copy Constructor**

---

## ✅ 1. Default Constructor

A constructor **without any parameters**. Java automatically provides one if you don’t define any constructor.

### 🔹 Example:

```java
class Animal {
    Animal() {  // Default constructor
        System.out.println("Animal is created");
    }
}

public class Main {
    public static void main(String[] args) {
        Animal a1 = new Animal(); // Constructor is called
    }
}
```

### 💡 Output:

```
Animal is created
```

---

## ✅ 2. Parameterized Constructor

A constructor that **accepts arguments** to initialize fields.

### 🔹 Example:

```java
class Student {
    int id;
    String name;

    // Parameterized constructor
    Student(int i, String n) {
        id = i;
        name = n;
    }

    void display() {
        System.out.println("ID: " + id + ", Name: " + name);
    }
}

public class Main {
    public static void main(String[] args) {
        Student s1 = new Student(101, "Bablu");
        Student s2 = new Student(102, "Rahul");

        s1.display();
        s2.display();
    }
}
```

### 💡 Output:

```
ID: 101, Name: Bablu
ID: 102, Name: Rahul
```

---

## ✅ 3. Copy Constructor

A constructor that creates a **new object by copying another object's data**. Java doesn’t provide this by default, you write it manually.

### 🔹 Example:

```java
class Book {
    String title;
    int pages;

    // Parameterized constructor
    Book(String t, int p) {
        title = t;
        pages = p;
    }

    // Copy constructor
    Book(Book b) {
        title = b.title;
        pages = b.pages;
    }

    void display() {
        System.out.println("Title: " + title + ", Pages: " + pages);
    }
}

public class Main {
    public static void main(String[] args) {
        Book b1 = new Book("Java Guide", 300);
        Book b2 = new Book(b1); // using copy constructor

        b1.display();
        b2.display();
    }
}
```

### 💡 Output:

```
Title: Java Guide, Pages: 300
Title: Java Guide, Pages: 300
```

---

## 🔸 Constructor Overloading

You can have **multiple constructors** in one class with different parameters. This is called **constructor overloading**.

---

## 🔸 Summary Table:

| Type          | Description                       |
| ------------- | --------------------------------- |
| Default       | No parameters                     |
| Parameterized | Accepts parameters                |
| Copy          | Copies values from another object |

---
 