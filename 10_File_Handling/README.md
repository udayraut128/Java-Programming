# 📁 10. File Handling (I/O in Java)

Java provides several classes in the `java.io` and `java.util` packages to perform **input and output (I/O)** operations on files.

---

## 🔹 1. `File` Class

The `File` class is used to represent file and directory pathnames in an abstract manner.

### 📌 Common Methods:

| Method              | Description             |
| ------------------- | ----------------------- |
| `exists()`          | Checks if file exists   |
| `createNewFile()`   | Creates a new file      |
| `mkdir()`           | Creates a new directory |
| `getName()`         | Returns file name       |
| `getAbsolutePath()` | Returns full path       |
| `length()`          | Returns size in bytes   |
| `delete()`          | Deletes the file        |

### ✅ Example: Using File class

```java
import java.io.File;
import java.io.IOException;

public class FileExample {
    public static void main(String[] args) {
        try {
            File file = new File("example.txt");

            if (file.createNewFile()) {
                System.out.println("File created: " + file.getName());
            } else {
                System.out.println("File already exists.");
            }

            System.out.println("Absolute Path: " + file.getAbsolutePath());
        } catch (IOException e) {
            System.out.println("An error occurred.");
        }
    }
}
```

---

## 🔹 2. Reading/Writing Using `FileReader` / `FileWriter`

Used for reading and writing character-based data.

### ✅ Example: Writing to a file using `FileWriter`

```java
import java.io.FileWriter;
import java.io.IOException;

public class WriteFile {
    public static void main(String[] args) {
        try {
            FileWriter writer = new FileWriter("sample.txt");
            writer.write("Hello Java!\nWelcome to file writing.");
            writer.close();
            System.out.println("File written successfully.");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

### ✅ Example: Reading from a file using `FileReader`

```java
import java.io.FileReader;
import java.io.IOException;

public class ReadFile {
    public static void main(String[] args) {
        try {
            FileReader reader = new FileReader("sample.txt");
            int ch;
            while ((ch = reader.read()) != -1) {
                System.out.print((char) ch);
            }
            reader.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

---

## 🔹 3. Using `BufferedReader` / `BufferedWriter`

BufferedReader/Writer offer better performance and support line-by-line operations.

### ✅ Example: Reading using `BufferedReader`

```java
import java.io.*;

public class BufferedRead {
    public static void main(String[] args) {
        try {
            BufferedReader br = new BufferedReader(new FileReader("sample.txt"));
            String line;
            while ((line = br.readLine()) != null) {
                System.out.println(line);
            }
            br.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

### ✅ Example: Writing using `BufferedWriter`

```java
import java.io.*;

public class BufferedWrite {
    public static void main(String[] args) {
        try {
            BufferedWriter bw = new BufferedWriter(new FileWriter("output.txt"));
            bw.write("This is written using BufferedWriter.");
            bw.newLine();
            bw.write("Line 2.");
            bw.close();
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

---

## 🔹 4. Using `Scanner` for File Reading

`Scanner` class (from `java.util`) can be used to read file content with token-based parsing.

### ✅ Example: Reading file using `Scanner`

```java
import java.io.File;
import java.io.FileNotFoundException;
import java.util.Scanner;

public class ScannerRead {
    public static void main(String[] args) {
        try {
            File file = new File("sample.txt");
            Scanner sc = new Scanner(file);
            while (sc.hasNextLine()) {
                String data = sc.nextLine();
                System.out.println(data);
            }
            sc.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        }
    }
}
```

---

## 🔹 5. Using `ObjectInputStream` / `ObjectOutputStream`

Used for **serialization and deserialization** of objects.

### ✅ Example: Serializing an object

```java
import java.io.*;

class Student implements Serializable {
    int id;
    String name;

    Student(int i, String n) {
        id = i;
        name = n;
    }
}

public class ObjectWrite {
    public static void main(String[] args) {
        try {
            Student s = new Student(101, "Alice");

            ObjectOutputStream out = new ObjectOutputStream(new FileOutputStream("student.ser"));
            out.writeObject(s);
            out.close();
            System.out.println("Object serialized successfully.");
        } catch (IOException e) {
            e.printStackTrace();
        }
    }
}
```

### ✅ Example: Deserializing an object

```java
import java.io.*;

public class ObjectRead {
    public static void main(String[] args) {
        try {
            ObjectInputStream in = new ObjectInputStream(new FileInputStream("student.ser"));
            Student s = (Student) in.readObject();
            in.close();
            System.out.println("ID: " + s.id + ", Name: " + s.name);
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

---

## ✅ Summary Table

| Tool                        | Purpose                                  |
| --------------------------- | ---------------------------------------- |
| `File`                      | File creation, info, existence check     |
| `FileReader` / `FileWriter` | Reading/writing text (char-based)        |
| `BufferedReader` / `Writer` | Fast, line-by-line file I/O              |
| `Scanner`                   | Easy parsing of file input (token-based) |
| `ObjectStream`              | Serialize/deserialize Java objects       |

---
 