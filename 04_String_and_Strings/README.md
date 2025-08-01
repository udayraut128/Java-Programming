# 🧩 04. Arrays and Strings in Java

---

## 🔹 1. **One-Dimensional Arrays**

A one-dimensional array stores a **linear collection** of elements of the same type.

### ✅ Declaration & Initialization

```java
int[] numbers = new int[5];            // Declaration with size
int[] marks = {90, 80, 70, 85, 95};    // Declaration with values
```

### ✅ Access & Modify

```java
System.out.println(marks[2]);  // Output: 70
marks[2] = 75;                 // Modify value
```

### ✅ Example: Sum of elements

```java
public class OneDArrayExample {
    public static void main(String[] args) {
        int[] nums = {2, 4, 6, 8, 10};
        int sum = 0;

        for (int i = 0; i < nums.length; i++) {
            sum += nums[i];
        }

        System.out.println("Sum = " + sum);  // Output: Sum = 30
    }
}
```

---

## 🔹 2. **Two-Dimensional Arrays**

Used to store data in a table or matrix form (rows and columns).

### ✅ Declaration & Initialization

```java
int[][] matrix = {
    {1, 2, 3},
    {4, 5, 6}
};
```

### ✅ Access

```java
System.out.println(matrix[1][2]);  // Output: 6
```

### ✅ Example: Printing a 2D Array

```java
public class TwoDArrayExample {
    public static void main(String[] args) {
        int[][] arr = {
            {1, 2},
            {3, 4}
        };

        for (int i = 0; i < arr.length; i++) {
            for (int j = 0; j < arr[i].length; j++) {
                System.out.print(arr[i][j] + " ");
            }
            System.out.println();
        }
    }
}
```

---

## 🔹 3. **Array Operations: Sorting & Searching**

### ✅ Sorting

```java
import java.util.Arrays;

public class SortArray {
    public static void main(String[] args) {
        int[] data = {5, 2, 9, 1};
        Arrays.sort(data);
        System.out.println(Arrays.toString(data)); // Output: [1, 2, 5, 9]
    }
}
```

### ✅ Searching (Linear Search)

```java
public class SearchArray {
    public static void main(String[] args) {
        int[] arr = {10, 20, 30, 40};
        int key = 30;
        boolean found = false;

        for (int num : arr) {
            if (num == key) {
                found = true;
                break;
            }
        }

        System.out.println("Found? " + found); // Output: Found? true
    }
}
```

---

## 🔹 4. **String Class and Common Methods**

### ✅ Declaration

```java
String s1 = "Hello";
String s2 = new String("World");
```

### ✅ Common Methods

| Method               | Description                     |
| -------------------- | ------------------------------- |
| `charAt(i)`          | Returns character at index `i`  |
| `length()`           | Returns length of string        |
| `substring(x, y)`    | Returns substring               |
| `equals()`           | Compares two strings (value)    |
| `equalsIgnoreCase()` | Ignores case while comparing    |
| `toLowerCase()`      | Converts string to lower case   |
| `toUpperCase()`      | Converts string to upper case   |
| `indexOf()`          | Finds index of first occurrence |
| `replace()`          | Replaces characters             |

### ✅ Example

```java
public class StringExample {
    public static void main(String[] args) {
        String str = "Java Programming";
        System.out.println(str.charAt(5));               // Output: P
        System.out.println(str.substring(5, 11));        // Output: Progra
        System.out.println(str.toUpperCase());           // Output: JAVA PROGRAMMING
    }
}
```

---

## 🔹 5. **StringBuffer and StringBuilder**

Used for **mutable** strings.

| Feature         | StringBuffer       | StringBuilder         |
| --------------- | ------------------ | --------------------- |
| **Thread-Safe** | Yes (synchronized) | No (not synchronized) |
| **Performance** | Slower             | Faster                |

### ✅ Example: StringBuffer

```java
public class BufferExample {
    public static void main(String[] args) {
        StringBuffer sb = new StringBuffer("Hello");
        sb.append(" Java");
        System.out.println(sb); // Output: Hello Java
    }
}
```

### ✅ Example: StringBuilder

```java
public class BuilderExample {
    public static void main(String[] args) {
        StringBuilder sb = new StringBuilder("Data");
        sb.insert(4, "base");
        System.out.println(sb); // Output: Database
    }
}
```

---

## 🔹 6. **String vs StringBuffer**

| Feature     | `String` (Immutable)         | `StringBuffer` (Mutable)      |
| ----------- | ---------------------------- | ----------------------------- |
| Modifiable  | No                           | Yes                           |
| Thread-Safe | No                           | Yes                           |
| Performance | Faster for less manipulation | Slower due to synchronization |

---

## 🔹 7. **Immutable Strings**

Java `String` objects are **immutable**, meaning **once created, they cannot be changed**.

### ✅ Example:

```java
String s = "Java";
s.concat(" Programming");  // New string created
System.out.println(s);     // Output: Java (original remains unchanged)
```

To modify strings, use `StringBuilder` or `StringBuffer`.

---

## 🔹 8. **Common String Operations**

```java
public class CommonStringOps {
    public static void main(String[] args) {
        String s = "HelloWorld";

        System.out.println(s.charAt(4));             // Output: o
        System.out.println(s.equals("helloworld"));  // Output: false
        System.out.println(s.substring(0, 5));       // Output: Hello
        System.out.println(s.indexOf("World"));      // Output: 5
        System.out.println(s.replace("Hello", "Hi"));// Output: HiWorld
    }
}
```

---

## ✅ Summary

* ✅ **Arrays** = Fixed-size collections of same-type elements.
* ✅ **Strings** = Immutable sequences of characters.
* ✅ **StringBuffer/StringBuilder** = Mutable strings for efficient manipulation.
* ✅ Learn `charAt()`, `substring()`, `equals()`, `replace()`, etc. for powerful string handling.

---

