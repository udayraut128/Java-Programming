# ☕ 13. Networking in Java (Socket Programming)

Java provides robust networking capabilities through the **`java.net`** package, which enables communication between programs across different machines using sockets, IP, and URLs.

---

## 🔸 1. Introduction to Networking in Java

* **Networking** refers to communication between two or more devices using protocols (e.g., TCP/IP).
* Java supports networking using:

  * **Socket Programming (TCP/IP)**
  * **URL and HTTP Connections**

Java hides complex networking details using high-level classes like:

* `Socket`, `ServerSocket` (TCP communication)
* `InetAddress` (IP-related info)
* `URL`, `URLConnection` (web resources)

---

## 🔸 2. Socket and ServerSocket

* **`Socket`** – Represents the client side of the connection.
* **`ServerSocket`** – Waits for and accepts incoming client connections on the server side.

### ✅ TCP Client (Socket)

```java
import java.io.*;
import java.net.*;

public class SimpleClient {
    public static void main(String[] args) throws IOException {
        Socket socket = new Socket("localhost", 6666);
        DataOutputStream out = new DataOutputStream(socket.getOutputStream());
        out.writeUTF("Hello Server");
        out.close();
        socket.close();
    }
}
```

### ✅ TCP Server (ServerSocket)

```java
import java.io.*;
import java.net.*;

public class SimpleServer {
    public static void main(String[] args) throws IOException {
        ServerSocket server = new ServerSocket(6666);
        Socket socket = server.accept();
        DataInputStream in = new DataInputStream(socket.getInputStream());
        String str = in.readUTF();
        System.out.println("Client says: " + str);
        server.close();
    }
}
```

---

## 🔸 3. `InetAddress` Class

Used to get IP address and host name information.

### ✅ Example:

```java
import java.net.*;

public class InetAddressExample {
    public static void main(String[] args) throws UnknownHostException {
        InetAddress ip = InetAddress.getLocalHost();
        System.out.println("Host Name: " + ip.getHostName());
        System.out.println("IP Address: " + ip.getHostAddress());
    }
}
```

---

## 🔸 4. TCP/IP Client-Server Communication

**TCP (Transmission Control Protocol)** ensures reliable, ordered, and error-checked delivery of data.

* `ServerSocket` waits for client requests.
* `Socket` initiates the connection from the client.
* Communication is done using `InputStream` and `OutputStream`.

### ✅ Enhanced Example:

#### Server:

```java
import java.io.*;
import java.net.*;

public class TCPServer {
    public static void main(String[] args) throws IOException {
        ServerSocket ss = new ServerSocket(1234);
        System.out.println("Server started...");
        Socket s = ss.accept();
        System.out.println("Client connected.");

        BufferedReader reader = new BufferedReader(new InputStreamReader(s.getInputStream()));
        String msg = reader.readLine();
        System.out.println("Message from client: " + msg);
        ss.close();
    }
}
```

#### Client:

```java
import java.io.*;
import java.net.*;

public class TCPClient {
    public static void main(String[] args) throws IOException {
        Socket s = new Socket("localhost", 1234);
        PrintWriter out = new PrintWriter(s.getOutputStream(), true);
        out.println("Hello Server, from Client!");
        s.close();
    }
}
```

---

## 🔸 5. URL and URLConnection

* `URL` is used to **access data** on the Internet via HTTP, FTP, etc.
* `URLConnection` is used to **connect and interact** with that resource.

### ✅ Example: Reading from a URL

```java
import java.net.*;
import java.io.*;

public class URLReadExample {
    public static void main(String[] args) throws Exception {
        URL url = new URL("https://example.com");
        BufferedReader reader = new BufferedReader(new InputStreamReader(url.openStream()));

        String inputLine;
        while ((inputLine = reader.readLine()) != null) {
            System.out.println(inputLine);
        }
        reader.close();
    }
}
```

---

## ✅ Summary Table

| Component       | Purpose                        |
| --------------- | ------------------------------ |
| `Socket`        | Connects to a server (TCP)     |
| `ServerSocket`  | Listens for client connections |
| `InetAddress`   | Represents IP and host info    |
| `URL`           | Represents a web address       |
| `URLConnection` | Used to read/write to a URL    |

---

