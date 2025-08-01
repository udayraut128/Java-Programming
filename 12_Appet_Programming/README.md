# ☕ 12. Applet Programming in Java

Java **Applets** are small programs that run in a web browser or applet viewer. They are part of Java's AWT (Abstract Window Toolkit) and primarily used for creating **graphical Java programs** embedded in web pages.

> Applets are mostly obsolete today due to browser restrictions, but understanding them is still valuable for legacy systems and exams.

---

## 🔸 1. Introduction to Applets

* Applets extend the `java.applet.Applet` or `javax.swing.JApplet` class.
* They are embedded in HTML pages using `<applet>` or `<object>` tags.
* Do **not** have a `main()` method.

```java
import java.applet.Applet;
import java.awt.Graphics;

public class HelloApplet extends Applet {
    public void paint(Graphics g) {
        g.drawString("Hello Applet!", 50, 50);
    }
}
```

### ✅ HTML to Run Applet:

```html
<applet code="HelloApplet.class" width="300" height="100"></applet>
```

> Note: Applets must be compiled and run using **appletviewer** (not modern browsers).

---

## 🔸 2. Applet Life Cycle

Each Applet goes through a defined set of **lifecycle methods**:

| Method              | Description                                                        |
| ------------------- | ------------------------------------------------------------------ |
| `init()`            | Called once when applet is first loaded                            |
| `start()`           | Called every time applet becomes active (after init or after stop) |
| `paint(Graphics g)` | Called to redraw the content (e.g., when applet is resized)        |
| `stop()`            | Called when applet is no longer active                             |
| `destroy()`         | Called when applet is about to be destroyed                        |

### ✅ Example Showing All Lifecycle Methods:

```java
import java.applet.Applet;
import java.awt.Graphics;

public class LifeCycleApplet extends Applet {

    public void init() {
        System.out.println("Applet Initialized");
    }

    public void start() {
        System.out.println("Applet Started");
    }

    public void paint(Graphics g) {
        g.drawString("Applet Life Cycle Demo", 20, 20);
    }

    public void stop() {
        System.out.println("Applet Stopped");
    }

    public void destroy() {
        System.out.println("Applet Destroyed");
    }
}
```

---

## 🔸 3. Difference Between Applet and Application

| Feature          | Java Applet                   | Java Application             |
| ---------------- | ----------------------------- | ---------------------------- |
| Execution        | Runs in browser/appletviewer  | Runs using JVM (main method) |
| Entry Point      | `init()`                      | `main()`                     |
| GUI Support      | Uses AWT                      | Can use AWT/Swing/JavaFX     |
| Access to System | Limited (sandboxed)           | Full system access           |
| Use Case         | Embedded content in web pages | Standalone software          |
| Security         | Restricted (sandbox)          | No sandbox                   |

---

## 🔸 4. Passing Parameters to Applets

You can pass parameters from the HTML file to an applet using `<param>` tags.

### ✅ HTML:

```html
<applet code="ParamApplet.class" width="300" height="100">
  <param name="username" value="Bablu">
</applet>
```

### ✅ Java Applet:

```java
import java.applet.Applet;
import java.awt.Graphics;

public class ParamApplet extends Applet {
    String user;

    public void init() {
        user = getParameter("username");
        if (user == null) user = "Guest";
    }

    public void paint(Graphics g) {
        g.drawString("Welcome " + user, 50, 50);
    }
}
```

---

## ✅ Summary

| Concept           | Description                                              |
| ----------------- | -------------------------------------------------------- |
| Applet            | GUI program that runs in a browser/appletviewer          |
| Lifecycle Methods | `init()`, `start()`, `paint()`, `stop()`, `destroy()`    |
| No main()         | Applet does not use `main()` for execution               |
| Parameters        | Passed via `<param>` in HTML                             |
| Obsolete          | No longer used in modern browsers (for security reasons) |

---
