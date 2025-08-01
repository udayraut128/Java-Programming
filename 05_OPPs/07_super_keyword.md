## ✅ What is `super` in Java?

The `super` keyword in Java is used to refer **immediately to the parent (superclass)** of the current object.

---

## 🔸 Uses of `super` Keyword:

1. **To call the superclass constructor**
2. **To access superclass fields (variables)**
3. **To call superclass methods**

---

### 1. **Calling Superclass Constructor**

You can use `super()` to invoke the **constructor of the parent class** from the subclass constructor.
This is always the **first statement** in the subclass constructor.

#### 🧪 Example:

```java
class Animal {
    Animal() {
        System.out.println("Animal constructor called");
    }
}

class Dog extends Animal {
    Dog() {
        super(); // calling parent class constructor
        System.out.println("Dog constructor called");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog d = new Dog();
    }
}
```

#### 🟩 Output:

```
Animal constructor called
Dog constructor called
```

---

### 2. **Accessing Superclass Fields**

If a subclass has a **field with the same name** as the superclass, `super` helps access the superclass field.

#### 🧪 Example:

```java
class Animal {
    String name = "Animal";
}

class Dog extends Animal {
    String name = "Dog";

    void printNames() {
        System.out.println("Subclass name: " + name);
        System.out.println("Superclass name: " + super.name);
    }
}

public class Main {
    public static void main(String[] args) {
        Dog d = new Dog();
        d.printNames();
    }
}
```

#### 🟩 Output:

```
Subclass name: Dog
Superclass name: Animal
```

---

### 3. **Calling Superclass Methods**

If a method is overridden in the subclass, `super.methodName()` is used to call the **parent class version** of the method.

#### 🧪 Example:

```java
class Animal {
    void display() {
        System.out.println("Animal display()");
    }
}

class Dog extends Animal {
    void display() {
        super.display(); // calls Animal's display
        System.out.println("Dog display()");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog d = new Dog();
        d.display();
    }
}
```

#### 🟩 Output:

```
Animal display()
Dog display()
```

---

## 🔐 Important Rules

* `super()` must be the first statement in the constructor.
* `super` cannot be used in a static context.
* You can’t access private members of the superclass using `super`.

---
 