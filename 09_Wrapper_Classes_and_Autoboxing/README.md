# ✅ 09. Wrapper Classes and Autoboxing

---

## 🔹 What are Wrapper Classes?

In Java, **wrapper classes** are used to **wrap primitive data types** (like `int`, `char`, etc.) into objects. This is essential when objects are required, such as in collections (`ArrayList`, `HashMap`, etc.).

### ✅ List of Wrapper Classes

| Primitive Type | Wrapper Class |
| -------------- | ------------- |
| `byte`         | `Byte`        |
| `short`        | `Short`       |
| `int`          | `Integer`     |
| `long`         | `Long`        |
| `float`        | `Float`       |
| `double`       | `Double`      |
| `char`         | `Character`   |
| `boolean`      | `Boolean`     |

---

### ✅ Example: Creating Wrapper Objects

```java
public class WrapperExample {
    public static void main(String[] args) {
        int a = 10;
        Integer obj = Integer.valueOf(a);  // manual boxing
        System.out.println("Integer object: " + obj);
    }
}
```

---

## 🔹 What is Autoboxing?

**Autoboxing** is the automatic conversion of **primitive types into their wrapper class** objects.

```java
int x = 5;
Integer obj = x;  // autoboxing
```

## 🔹 What is Unboxing?

**Unboxing** is the automatic conversion of **wrapper class objects back to primitive types**.

```java
Integer obj = 10;
int x = obj;  // unboxing
```

---

### ✅ Autoboxing and Unboxing Example

```java
import java.util.ArrayList;

public class AutoBoxingUnboxing {
    public static void main(String[] args) {
        ArrayList<Integer> list = new ArrayList<>();

        // Autoboxing: int → Integer
        list.add(100);

        // Unboxing: Integer → int
        int num = list.get(0);

        System.out.println("Value: " + num);
    }
}
```

---

## 🔹 Use Cases of Wrapper Classes

1. **Collections Framework** (like `ArrayList`, `HashMap`) can only store **objects**, not primitives.

   ```java
   ArrayList<Integer> nums = new ArrayList<>();
   nums.add(10);  // Autoboxed
   ```
2. **Utility Methods** in wrapper classes (e.g., `Integer.parseInt()`, `Double.valueOf()`)

   ```java
   int a = Integer.parseInt("123");
   ```
3. **Serialization** – Only objects can be serialized.
4. **Synchronization** – Sometimes needed for threads.
5. **Reflection APIs** – Work with objects and classes.

---

## ✅ Summary

| Concept       | Description                                    |
| ------------- | ---------------------------------------------- |
| Wrapper Class | Converts primitives to objects                 |
| Autoboxing    | Primitive → Wrapper (automatic)                |
| Unboxing      | Wrapper → Primitive (automatic)                |
| Use Cases     | Collections, Utility methods, Reflection, etc. |

---
