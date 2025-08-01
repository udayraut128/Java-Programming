# 🖼️ 11. GUI Programming in Java (AWT & Swing)

Java provides two main libraries for building GUIs:

* **AWT (Abstract Window Toolkit)** – Older, platform-dependent.
* **Swing** – Newer, platform-independent, more powerful.

---

## 🔸 1. Introduction to AWT and Swing

| Feature     | AWT                          | Swing                              |
| ----------- | ---------------------------- | ---------------------------------- |
| Package     | `java.awt.*`                 | `javax.swing.*`                    |
| Platform    | Depends on native OS widgets | Pure Java (lightweight components) |
| Look & Feel | OS-dependent                 | Customizable                       |
| Speed       | Faster (uses OS components)  | Slightly slower                    |

---

## 🔸 2. Common GUI Components

| Component | AWT Class       | Swing Class    |
| --------- | --------------- | -------------- |
| Label     | `Label`         | `JLabel`       |
| Button    | `Button`        | `JButton`      |
| TextField | `TextField`     | `JTextField`   |
| TextArea  | `TextArea`      | `JTextArea`    |
| Checkbox  | `Checkbox`      | `JCheckBox`    |
| Radio     | `CheckboxGroup` | `JRadioButton` |
| ComboBox  | `Choice`        | `JComboBox`    |
| List      | `List`          | `JList`        |

---

### ✅ Example (Swing): Simple Button + Label

```java
import javax.swing.*;

public class SwingExample {
    public static void main(String[] args) {
        JFrame frame = new JFrame("Swing Example");
        JButton button = new JButton("Click Me");
        JLabel label = new JLabel("Hello, Java!");

        frame.setSize(300, 200);
        frame.setLayout(null);  // absolute positioning
        label.setBounds(100, 50, 120, 30);
        button.setBounds(100, 100, 100, 30);

        frame.add(label);
        frame.add(button);

        frame.setVisible(true);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    }
}
```

---

## 🔸 3. Containers

Containers are GUI components that hold and organize other components.

| Container | Description                                      |
| --------- | ------------------------------------------------ |
| `Frame`   | Top-level window (AWT)                           |
| `JFrame`  | Swing version of Frame                           |
| `Panel`   | Generic container to hold components             |
| `JPanel`  | Swing’s container version                        |
| `Applet`  | Used to embed Java applications in a web browser |

---

## 🔸 4. Layout Managers

Java provides layout managers to control component placement.

### ✅ Common Layout Managers:

| Layout Manager  | Description                                    |
| --------------- | ---------------------------------------------- |
| `FlowLayout`    | Left to right, wrap to next line               |
| `BorderLayout`  | Five regions: North, South, East, West, Center |
| `GridLayout`    | Grid-like arrangement (rows × columns)         |
| `BoxLayout`     | Arrange in one direction (X or Y axis)         |
| `CardLayout`    | Stack components like cards                    |
| `GridBagLayout` | Advanced grid with constraints                 |

---

### ✅ Example: Using FlowLayout

```java
import javax.swing.*;
import java.awt.*;

public class FlowLayoutExample {
    public static void main(String[] args) {
        JFrame frame = new JFrame("FlowLayout Example");
        frame.setLayout(new FlowLayout());

        frame.add(new JButton("Button 1"));
        frame.add(new JButton("Button 2"));
        frame.add(new JButton("Button 3"));

        frame.setSize(300, 150);
        frame.setVisible(true);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    }
}
```

---

## 🔸 5. Event Handling

GUI applications respond to user actions via **events** like button clicks, key presses, etc.

Java uses the **Event Delegation Model**, where events are handled by **listener interfaces**.

---

### ✅ Event Delegation Model

* **Event Source** – The component (e.g., Button)
* **Event Listener** – Interface that handles event (e.g., `ActionListener`)
* **Event Object** – Contains event details (e.g., `ActionEvent`)

---

### ✅ Event Listener Interfaces

| Interface        | Used For                  |
| ---------------- | ------------------------- |
| `ActionListener` | Button, Menu, etc.        |
| `MouseListener`  | Mouse clicks, enter, exit |
| `KeyListener`    | Keyboard events           |
| `ItemListener`   | Checkbox, RadioButton     |
| `WindowListener` | Frame closing, opening    |

---

### ✅ Example: Handling Button Click

```java
import javax.swing.*;
import java.awt.event.*;

public class ButtonEventExample {
    public static void main(String[] args) {
        JFrame frame = new JFrame("Button Click");
        JButton button = new JButton("Click Me");

        button.setBounds(100, 100, 100, 40);
        frame.add(button);

        button.addActionListener(new ActionListener() {
            public void actionPerformed(ActionEvent e) {
                JOptionPane.showMessageDialog(frame, "Button Clicked!");
            }
        });

        frame.setSize(300, 250);
        frame.setLayout(null);
        frame.setVisible(true);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    }
}
```

---

## 🔸 6. Adapter Classes

When you only want to override **some methods** of a listener interface (which has many), use **adapter classes**.

| Interface        | Adapter Class   |
| ---------------- | --------------- |
| `MouseListener`  | `MouseAdapter`  |
| `KeyListener`    | `KeyAdapter`    |
| `WindowListener` | `WindowAdapter` |

---

### ✅ Example: WindowAdapter

```java
import javax.swing.*;
import java.awt.event.*;

public class WindowAdapterExample {
    public static void main(String[] args) {
        JFrame frame = new JFrame("Window Adapter");

        frame.addWindowListener(new WindowAdapter() {
            public void windowClosing(WindowEvent e) {
                System.out.println("Window is closing");
                System.exit(0);
            }
        });

        frame.setSize(300, 200);
        frame.setVisible(true);
    }
}
```

---

## ✅ Summary

| Topic           | Key Points                        |
| --------------- | --------------------------------- |
| AWT & Swing     | GUI libraries in Java             |
| Components      | Buttons, Labels, TextFields, etc. |
| Containers      | JFrame, JPanel, Applet            |
| Layout Managers | FlowLayout, BorderLayout, etc.    |
| Event Handling  | Listeners handle user actions     |
| Adapter Classes | Simplify listener implementation  |

---

