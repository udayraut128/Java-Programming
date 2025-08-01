# ☕ 14. JDBC (Java Database Connectivity)

## 🔸 What is JDBC?

**JDBC** is an API in Java that allows Java applications to interact with relational databases (e.g., MySQL, Oracle, PostgreSQL, SQLite).

---

## 🔸 JDBC Architecture

JDBC works using **4 layers**:

```
Java Application
      ↓
JDBC API (Interfaces)
      ↓
JDBC Driver Manager
      ↓
JDBC Driver (Specific to DB)
      ↓
Database (MySQL, Oracle, etc.)
```

---

## 🔸 JDBC API Interfaces:

| Interface           | Description                                     |
| ------------------- | ----------------------------------------------- |
| `DriverManager`     | Manages a list of database drivers              |
| `Connection`        | Establishes a connection to DB                  |
| `Statement`         | Executes SQL queries (static)                   |
| `PreparedStatement` | Executes precompiled SQL queries (dynamic/safe) |
| `ResultSet`         | Holds the result of a query                     |

---

## 🔸 Steps to Connect to a Database

### ✅ Steps:

1. **Import the JDBC package**
2. **Load the JDBC Driver**
3. **Establish a Connection**
4. **Create Statement or PreparedStatement**
5. **Execute Query**
6. **Process ResultSet**
7. **Close Connection**

---

## ✅ Example: JDBC with MySQL

Assuming:

* Database: `testdb`
* Table: `students(id INT, name VARCHAR)`

### 🔧 Prerequisites:

* Add MySQL JDBC driver (`mysql-connector-java.jar`) to your project.
* Use IDE or CLI with classpath configured.

---

## 🔹 1. SELECT (Fetch data)

```java
import java.sql.*;

public class JDBCSelectExample {
    public static void main(String[] args) {
        try {
            // 1. Load driver
            Class.forName("com.mysql.cj.jdbc.Driver");

            // 2. Establish connection
            Connection con = DriverManager.getConnection(
                    "jdbc:mysql://localhost:3306/testdb", "root", "password");

            // 3. Create statement
            Statement stmt = con.createStatement();

            // 4. Execute query
            ResultSet rs = stmt.executeQuery("SELECT * FROM students");

            // 5. Process result
            while (rs.next()) {
                System.out.println(rs.getInt(1) + " " + rs.getString(2));
            }

            con.close();
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

---

## 🔹 2. INSERT (Using `PreparedStatement`)

```java
import java.sql.*;

public class JDBCInsertExample {
    public static void main(String[] args) {
        try {
            Class.forName("com.mysql.cj.jdbc.Driver");

            Connection con = DriverManager.getConnection(
                    "jdbc:mysql://localhost:3306/testdb", "root", "password");

            String sql = "INSERT INTO students VALUES (?, ?)";
            PreparedStatement ps = con.prepareStatement(sql);

            ps.setInt(1, 101);
            ps.setString(2, "Alice");

            int status = ps.executeUpdate();
            System.out.println(status + " row inserted.");

            con.close();
        } catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

---

## 🔹 3. UPDATE

```java
String sql = "UPDATE students SET name=? WHERE id=?";
PreparedStatement ps = con.prepareStatement(sql);
ps.setString(1, "Bob");
ps.setInt(2, 101);
int result = ps.executeUpdate();
```

---

## 🔹 4. DELETE

```java
String sql = "DELETE FROM students WHERE id=?";
PreparedStatement ps = con.prepareStatement(sql);
ps.setInt(1, 101);
int result = ps.executeUpdate();
```

---

## 🔸 Exception Handling in JDBC

JDBC operations often throw **`SQLException`**, which should be caught and logged.

```java
catch (SQLException e) {
    System.out.println("SQL Error: " + e.getMessage());
    e.printStackTrace();
}
```

You should always:

* Close **Connection**, **Statement**, and **ResultSet** in a `finally` block.
* Use `try-with-resources` for auto-closing.

---

## 🔸 Summary Table

| Component           | Purpose                 |
| ------------------- | ----------------------- |
| `DriverManager`     | Loads DB drivers        |
| `Connection`        | Connects to database    |
| `Statement`         | Runs static SQL         |
| `PreparedStatement` | Dynamic/precompiled SQL |
| `ResultSet`         | Result of SELECT query  |

---
