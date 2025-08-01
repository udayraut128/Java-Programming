## ✅ What is Inheritance?

**Inheritance** is the process by which one class (**child/subclass**) acquires the **properties (fields)** and **behaviors (methods)** of another class (**parent/superclass**).

---

### 🔹 Why use Inheritance?

* Code reusability
* Method overriding (runtime polymorphism)
* Maintainability and modularity

---

## ✅ Syntax of Inheritance

```java
class Parent {
    // properties and methods
}

class Child extends Parent {
    // additional properties and methods
}
```

---

## 📘 Types of Inheritance in Java

### 1. **Single Inheritance**

One subclass inherits from one superclass.

```
      A
      │
      B
```

### 🔸 Example:

```java
class Animal {
    void eat() {
        System.out.println("This animal eats food");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog d = new Dog();
        d.eat();   // inherited
        d.bark();  // own method
    }
}
```

---

### 2. **Multilevel Inheritance**

A class is derived from another derived class.

```
      A
      │
      B
      │
      C
```

### 🔸 Example:

```java
class Animal {
    void eat() {
        System.out.println("Eats food");
    }
}

class Mammal extends Animal {
    void walk() {
        System.out.println("Walks on legs");
    }
}

class Dog extends Mammal {
    void bark() {
        System.out.println("Barks");
    }
}

public class Main {
    public static void main(String[] args) {
        Dog d = new Dog();
        d.eat();   // from Animal
        d.walk();  // from Mammal
        d.bark();  // from Dog
    }
}
```

---

### 3. **Hierarchical Inheritance**

Multiple classes inherit from the same parent class.

```
       A
      / \
     B   C
```

### 🔸 Example:

```java
class Animal {
    void sound() {
        System.out.println("Animal makes sound");
    }
}

class Cat extends Animal {
    void meow() {
        System.out.println("Cat meows");
    }
}

class Dog extends Animal {
    void bark() {
        System.out.println("Dog barks");
    }
}

public class Main {
    public static void main(String[] args) {
        Cat c = new Cat();
        Dog d = new Dog();

        c.sound();
        c.meow();

        d.sound();
        d.bark();
    }
}
```

---

## ❌ Note:

Java **does not support multiple inheritance using classes** (i.e., one class can't extend two classes) to avoid **ambiguity** (Diamond problem). This can be achieved using **interfaces**.

---
 