# ✅ `this` Keyword in Java

The `this` keyword is a reference variable in Java that refers to the **current object** of the class.

---

## 🔹 Purposes of `this` Keyword:

1. To refer **current class instance variable**
2. To invoke **current class method or constructor**
3. To pass the current object as a parameter
4. To return the current object from a method

---

## ✅ 1. Refer current class instance variable

When local variables (parameters) and instance variables have **same names**, `this` differentiates them.

### 🔹 Example:

```java
class Student {
    int id;
    String name;

    Student(int id, String name) {
        this.id = id;       // 'this.id' refers to instance variable
        this.name = name;   // 'name' is local parameter
    }

    void display() {
        System.out.println("ID: " + id + ", Name: " + name);
    }
}

public class Main {
    public static void main(String[] args) {
        Student s1 = new Student(101, "Bablu");
        s1.display();
    }
}
```

### 💡 Output:

```
ID: 101, Name: Bablu
```

---

## ✅ 2. Invoke current class method

You can call a **method from another method** using `this`.

```java
class Demo {
    void show() {
        System.out.println("Hello from show()");
    }

    void display() {
        this.show(); // same as just calling show()
        System.out.println("Inside display()");
    }
}

public class Main {
    public static void main(String[] args) {
        Demo d = new Demo();
        d.display();
    }
}
```

---

## ✅ 3. Invoke current class constructor (Constructor Chaining)

You can call one constructor from another using `this()`.

```java
class Employee {
    int id;
    String name;

    Employee() {
        this(100, "Default"); // Calls parameterized constructor
        System.out.println("Default constructor called");
    }

    Employee(int id, String name) {
        this.id = id;
        this.name = name;
        System.out.println("Parameterized constructor called");
    }

    void display() {
        System.out.println("ID: " + id + ", Name: " + name);
    }
}

public class Main {
    public static void main(String[] args) {
        Employee e = new Employee();
        e.display();
    }
}
```

### 💡 Output:

```
Parameterized constructor called
Default constructor called
ID: 100, Name: Default
```

---

## ✅ 4. Pass current object as method argument

```java
class A {
    void show(A obj) {
        System.out.println("Method called with current object");
    }

    void callShow() {
        show(this); // passing current object
    }
}

public class Main {
    public static void main(String[] args) {
        A a = new A();
        a.callShow();
    }
}
```

---

## ✅ 5. Return current object from method

```java
class Chain {
    Chain getObject() {
        return this;
    }

    void msg() {
        System.out.println("Returning this object");
    }
}

public class Main {
    public static void main(String[] args) {
        Chain c = new Chain();
        c.getObject().msg(); // chaining
    }
}
```

---

## 🔸 Summary Table

| Use Case          | Purpose                        |
| ----------------- | ------------------------------ |
| `this.var = var;` | Resolve name conflict          |
| `this.method()`   | Call current class method      |
| `this()`          | Call current class constructor |
| `show(this)`      | Pass current object            |
| `return this;`    | Return current object          |

---
 