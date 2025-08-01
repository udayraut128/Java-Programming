## ✅  **Encapsulation in Java**

### 🔷 What is Encapsulation?

**Encapsulation** is one of the four fundamental **OOP concepts** in Java. It is the process of **wrapping data (variables)** and **code acting on the data (methods)** together as a single unit. In Java, this is done using:

* **Private variables**
* **Public getter and setter methods**

Encapsulation helps in **data hiding**, **security**, and **maintainability**.

---

### 🔐 Key Points:

* All instance variables are marked **private**.
* Access to these variables is provided via **public getter and setter** methods.
* It protects the internal state of an object from direct modification by external code.
* It enables **loose coupling** in code.

---

### ✅ Example 1: Simple Encapsulation

```java
class Student {
    // Private data members
    private String name;
    private int age;

    // Public getter method
    public String getName() {
        return name;
    }

    // Public setter method
    public void setName(String newName) {
        name = newName;
    }

    public int getAge() {
        return age;
    }

    public void setAge(int newAge) {
        if (newAge > 0) {
            age = newAge;
        }
    }
}

public class Main {
    public static void main(String[] args) {
        Student s = new Student();
        s.setName("Alice");
        s.setAge(21);

        System.out.println("Name: " + s.getName());
        System.out.println("Age: " + s.getAge());
    }
}
```

### 🔍 Output:

```
Name: Alice
Age: 21
```

---

### ✅ Example 2: Preventing Invalid Input

Encapsulation allows logic to be added inside setters to control how the data is set.

```java
class BankAccount {
    private double balance;

    public double getBalance() {
        return balance;
    }

    public void deposit(double amount) {
        if (amount > 0)
            balance += amount;
    }

    public void withdraw(double amount) {
        if (amount > 0 && amount <= balance)
            balance -= amount;
    }
}

public class Test {
    public static void main(String[] args) {
        BankAccount b = new BankAccount();
        b.deposit(1000);
        b.withdraw(500);
        System.out.println("Remaining Balance: " + b.getBalance());
    }
}
```

---

### 🎯 Advantages of Encapsulation:

| Feature               | Benefit                                                                |
| --------------------- | ---------------------------------------------------------------------- |
| **Data Hiding**       | Prevents direct access to sensitive data                               |
| **Improved Security** | Restricts invalid data using setters                                   |
| **Reusability**       | Code is modular and reusable                                           |
| **Flexibility**       | You can change internal implementation without affecting external code |
| **Readability**       | Clear separation of data and behavior                                  |

---

### 🧠 Summary:

* Use **private** variables to hide data.
* Use **public getter/setter** methods to access data.
* Encapsulation helps achieve **data hiding**, better **security**, and **clean design**.

---
 
