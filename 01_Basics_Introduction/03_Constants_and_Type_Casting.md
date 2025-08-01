## 🔹 **Constants and Literals in Java**

### ✅ **Constants**

Constants are variables whose value cannot be changed once assigned.

In Java, we declare a constant using the `final` keyword.

### **Syntax:**

```java
final data_type CONSTANT_NAME = value;
```

### **Example:**

```java
public class ConstantExample {
    public static void main(String[] args) {
        final double PI = 3.14159;
        // PI = 3.14; // ❌ Error: Cannot assign a value to final variable
        System.out.println("Value of PI: " + PI);
    }
}
```

---

### ✅ **Literals**

**Literals** are the actual values assigned to variables or constants in the code.

#### 📌 Types of Literals:

| Literal Type  | Example              | Description                          |
| ------------- | -------------------- | ------------------------------------ |
| **Integer**   | `10`, `-50`, `0x1F`  | Decimal or hexadecimal values        |
| **Floating**  | `3.14`, `1.0e-3`     | Double or float values               |
| **Character** | `'A'`, `'9'`, `'\n'` | Single character or escape sequences |
| **String**    | `"Java"`, `"123"`    | Sequence of characters               |
| **Boolean**   | `true`, `false`      | Logical values                       |

---

## 🔹 **Type Conversion vs. Type Casting**

Java supports **type conversion** between different data types. These conversions are categorized into **automatic** and **explicit** conversions.

---

### ✅ **Type Conversion (Widening Conversion)**

Also called **implicit casting**.

🔹 When a smaller data type is converted to a larger data type **automatically**.

### **Examples:**

* `int` to `long`
* `float` to `double`

### **Code Example:**

```java
public class TypeConversionExample {
    public static void main(String[] args) {
        int a = 10;
        long b = a; // automatic widening
        float c = b; // long to float

        System.out.println("Long: " + b);
        System.out.println("Float: " + c);
    }
}
```

---

### ✅ **Type Casting (Narrowing Conversion)**

Also called **explicit casting**.

🔹 When a larger data type is manually converted to a smaller type using a **cast operator**.

### **Syntax:**

```java
data_type variable = (target_type) value;
```

### **Code Example:**

```java
public class TypeCastingExample {
    public static void main(String[] args) {
        double x = 10.5;
        int y = (int) x;  // manual narrowing

        System.out.println("Original: " + x);
        System.out.println("After casting: " + y);
    }
}
```

### ⚠️ Possible Data Loss:

```java
int a = 130;
byte b = (byte) a;  // value becomes -126 due to overflow
```

---

### 🔄 **Comparison: Type Conversion vs. Type Casting**

| Aspect              | Type Conversion          | Type Casting          |
| ------------------- | ------------------------ | --------------------- |
| Performed By        | Java Compiler (Implicit) | Programmer (Explicit) |
| Data Type Direction | Lower → Higher           | Higher → Lower        |
| Risk of Data Loss   | No                       | Yes                   |
| Example             | `int → long`             | `double → int`        |

---

 