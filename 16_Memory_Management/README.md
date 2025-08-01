# ✅ 16. Memory Management in Java

Java uses **automatic memory management**, meaning developers don’t need to explicitly free memory. The **Java Virtual Machine (JVM)** handles memory through **Garbage Collection (GC)**.

---

## 🔹 1. Garbage Collection

### ✅ What is it?

Garbage Collection in Java is the process by which the **JVM automatically removes unused objects** from memory to free up space and avoid memory leaks.

### ✅ How it works:

* The JVM tracks objects in memory.
* When no part of the program references an object, the **Garbage Collector** removes it.

### ✅ Example:

```java
public class GarbageExample {
    public static void main(String[] args) {
        GarbageExample obj = new GarbageExample();
        obj = null;  // Eligible for garbage collection

        System.gc(); // Suggests JVM to run garbage collector
    }

    @Override
    protected void finalize() {
        System.out.println("Object is garbage collected");
    }
}
```

📝 `System.gc()` is only a **request** — the JVM **may or may not** run the GC immediately.

---

## 🔹 2. finalize() Method (Deprecated in Java 9+)

### ✅ What is it?

The `finalize()` method is called by the Garbage Collector **before** reclaiming the object memory. You can override it to perform cleanup, like closing files or releasing resources.

> ⚠️ **Note**: `finalize()` is **deprecated** because it's unpredictable and not reliable for managing resources.

### ✅ Example:

```java
class MyClass {
    @Override
    protected void finalize() {
        System.out.println("Finalize method called");
    }
}

public class FinalizeDemo {
    public static void main(String[] args) {
        MyClass obj = new MyClass();
        obj = null;

        System.gc(); // Request GC
    }
}
```

---

## 🔹 3. Reference Types

Java provides several types of object references in `java.lang.ref` package to give programmers more control over memory management.

---

### ✅ a) Strong Reference (Default)

* Most common.
* If an object has a strong reference, **it will never be garbage collected**.

```java
String str = new String("Java"); // strong reference
```

---

### ✅ b) Weak Reference

* The object **can be GC'd** even if it has a weak reference.
* Useful in caching where we don’t want to prevent GC.

```java
import java.lang.ref.WeakReference;

public class WeakRefExample {
    public static void main(String[] args) {
        String s = new String("Hello");
        WeakReference<String> weakRef = new WeakReference<>(s);

        s = null; // remove strong reference
        System.gc();

        System.out.println("After GC: " + weakRef.get()); // May return null
    }
}
```

---

### ✅ c) Soft Reference

* Slightly stronger than weak references.
* GC reclaims them **only when memory is low**.
* Good for memory-sensitive caches.

```java
import java.lang.ref.SoftReference;

public class SoftRefExample {
    public static void main(String[] args) {
        String data = new String("Important Data");
        SoftReference<String> softRef = new SoftReference<>(data);

        data = null; // clear strong ref
        System.gc();

        System.out.println("Soft Ref: " + softRef.get()); // Usually still accessible
    }
}
```

---

### ✅ d) Phantom Reference

* The weakest reference.
* You cannot get the object using `get()`.
* Used to **track object finalization**.

```java
import java.lang.ref.PhantomReference;
import java.lang.ref.ReferenceQueue;

public class PhantomRefExample {
    public static void main(String[] args) {
        ReferenceQueue<Object> queue = new ReferenceQueue<>();
        Object obj = new Object();
        PhantomReference<Object> phantom = new PhantomReference<>(obj, queue);

        obj = null;
        System.gc();

        System.out.println("Phantom Ref: " + phantom.get()); // Always null
    }
}
```

---

## 🔚 Summary Table

| Reference Type    | Collected by GC   | `get()` returns object?  | Use Case                  |
| ----------------- | ----------------- | ------------------------ | ------------------------- |
| Strong Reference  | ❌ No              | ✅ Yes                    | Normal program flow       |
| Soft Reference    | ✅ If memory low   | ✅ Yes (usually)          | Caching                   |
| Weak Reference    | ✅ Always eligible | ✅ Yes (if not collected) | Memory-sensitive caching  |
| Phantom Reference | ✅ Yes             | ❌ No                     | Post-cleanup/Finalization |

---

