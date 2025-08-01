# 🔹 15. Java Advanced Topics

---

## ✅ 1. Lambda Expressions (Java 8)

**Lambda** expressions enable you to treat functionality as a method argument or to create anonymous functions.

### ✅ Syntax:

```java
(parameters) -> expression

// Or

(parameters) -> { statements }
```

### ✅ Example:

```java
interface Greet {
    void sayHello(String name);
}

public class LambdaExample {
    public static void main(String[] args) {
        Greet greet = (name) -> System.out.println("Hello, " + name);
        greet.sayHello("Bablu");
    }
}
```

---

## ✅ 2. Functional Interfaces

An interface with exactly **one abstract method** is called a **Functional Interface**. Annotated with `@FunctionalInterface`.

### ✅ Example:

```java
@FunctionalInterface
interface Addable {
    int add(int a, int b);
}

public class FunctionalInterfaceExample {
    public static void main(String[] args) {
        Addable add = (a, b) -> a + b;
        System.out.println("Sum = " + add.add(5, 3));
    }
}
```

---

## ✅ 3. Stream API

Introduced in Java 8, it processes collections of objects in a **functional style** (filter, map, collect, etc.)

### ✅ Example:

```java
import java.util.*;
import java.util.stream.*;

public class StreamExample {
    public static void main(String[] args) {
        List<String> names = Arrays.asList("Anil", "Bablu", "Arun");

        names.stream()
             .filter(n -> n.startsWith("A"))
             .map(String::toUpperCase)
             .forEach(System.out::println);
    }
}
```

---

## ✅ 4. Collections Framework

A unified architecture for storing and manipulating data.

---

### 📘 i) Interfaces:

* `List`: Ordered, allows duplicates
* `Set`: Unordered, no duplicates
* `Map`: Key-value pairs
* `Queue`: FIFO structure

---

### 📘 ii) Common Classes with Examples:

#### 📍 ArrayList

```java
List<String> list = new ArrayList<>();
list.add("Java");
list.add("Python");
System.out.println(list.get(0));
```

#### 📍 LinkedList

```java
LinkedList<Integer> ll = new LinkedList<>();
ll.add(10);
ll.addFirst(5);
System.out.println(ll);
```

#### 📍 HashSet

```java
Set<String> set = new HashSet<>();
set.add("A");
set.add("B");
set.add("A"); // Ignored
System.out.println(set);
```

#### 📍 TreeSet (Sorted Set)

```java
Set<Integer> treeSet = new TreeSet<>();
treeSet.add(50);
treeSet.add(10);
treeSet.add(30);
System.out.println(treeSet); // Sorted output
```

#### 📍 HashMap

```java
Map<Integer, String> map = new HashMap<>();
map.put(1, "Apple");
map.put(2, "Banana");
System.out.println(map.get(1));
```

---

## ✅ 5. Generics

Generics enable types (classes and methods) to operate on objects of various types while providing compile-time type safety.

### ✅ Example:

```java
class Box<T> {
    T value;

    void set(T value) {
        this.value = value;
    }

    T get() {
        return value;
    }
}

public class GenericsExample {
    public static void main(String[] args) {
        Box<String> b = new Box<>();
        b.set("Hello");
        System.out.println(b.get());
    }
}
```

---

## ✅ 6. Annotations

Annotations provide metadata about your program to the compiler or runtime.

### ✅ Common Annotations:

| Annotation             | Purpose                           |
| ---------------------- | --------------------------------- |
| `@Override`            | Checks if method overrides parent |
| `@Deprecated`          | Marks method as outdated          |
| `@FunctionalInterface` | Functional interface              |

### ✅ Example:

```java
class Parent {
    void show() {
        System.out.println("Parent");
    }
}

class Child extends Parent {
    @Override
    void show() {
        System.out.println("Child");
    }
}
```

---

## ✅ 7. Enum

An `enum` is a special class that represents a group of constants.

### ✅ Example:

```java
enum Day { MONDAY, TUESDAY, FRIDAY }

public class EnumExample {
    public static void main(String[] args) {
        Day d = Day.MONDAY;
        System.out.println(d);

        for (Day day : Day.values()) {
            System.out.println(day);
        }
    }
}
```

---

## 📝 Summary Table

| Topic                | Example                             |
| -------------------- | ----------------------------------- |
| Lambda               | `(a, b) -> a + b`                   |
| Functional Interface | `@FunctionalInterface`              |
| Stream API           | `stream().filter().map().collect()` |
| Collections          | `List`, `Set`, `Map`, `Queue`       |
| Generics             | `Box<T>`                            |
| Annotations          | `@Override`, `@Deprecated`          |
| Enum                 | `enum Day { MON, TUE }`             |

---

