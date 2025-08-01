# 🧵 07. Multithreading in Java

Java supports **multithreading**, allowing multiple threads to execute concurrently for better CPU utilization.

---

## 🔸 What is a Thread?

A **thread** is a lightweight sub-process. It’s a **smallest unit of execution** that can run concurrently with other threads.

---

## 🔹 Creating Threads in Java

### ✅ 1. **By extending `Thread` class**

```java
class MyThread extends Thread {
    public void run() {
        System.out.println("Thread is running...");
    }
}

public class ThreadExample1 {
    public static void main(String[] args) {
        MyThread t = new MyThread();
        t.start();  // starts the thread
    }
}
```

---

### ✅ 2. **By implementing `Runnable` interface**

```java
class MyRunnable implements Runnable {
    public void run() {
        System.out.println("Runnable thread running...");
    }
}

public class ThreadExample2 {
    public static void main(String[] args) {
        Thread t = new Thread(new MyRunnable());
        t.start();
    }
}
```

---

## 🔹 Thread Life Cycle

A thread goes through these **states**:

```
NEW → RUNNABLE → RUNNING → BLOCKED/WAITING → TERMINATED
```

### ✅ Diagram (Text Format):

```
NEW
 ↓ start()
RUNNABLE
 ↓ (picked by scheduler)
RUNNING
 ↓ (sleep/wait)
WAITING/BLOCKED
 ↓ (completed)
TERMINATED
```

---

## 🔹 Thread Methods

| Method      | Description                                      |
| ----------- | ------------------------------------------------ |
| `start()`   | Starts a new thread. Calls `run()` internally.   |
| `run()`     | Defines the code that a thread executes.         |
| `sleep(ms)` | Puts the thread to sleep for given milliseconds. |
| `join()`    | Waits for a thread to finish.                    |
| `isAlive()` | Checks if a thread is still running.             |

### ✅ Example with `sleep()`, `join()`, `isAlive()`:

```java
class MyThread extends Thread {
    public void run() {
        try {
            Thread.sleep(1000);
            System.out.println("Thread running...");
        } catch (InterruptedException e) {
            System.out.println(e);
        }
    }
}

public class ThreadMethodsExample {
    public static void main(String[] args) throws InterruptedException {
        MyThread t1 = new MyThread();
        t1.start();
        System.out.println("Is thread alive? " + t1.isAlive());

        t1.join();  // wait for t1 to finish
        System.out.println("Thread has finished.");
    }
}
```

---

## 🔹 Synchronization

Multiple threads accessing shared data can lead to inconsistency (race condition). **Synchronization** prevents that.

### ✅ Example:

```java
class Counter {
    int count = 0;

    synchronized void increment() {
        count++;
    }
}

public class SyncExample {
    public static void main(String[] args) throws InterruptedException {
        Counter counter = new Counter();

        Thread t1 = new Thread(() -> {
            for (int i = 0; i < 1000; i++) counter.increment();
        });

        Thread t2 = new Thread(() -> {
            for (int i = 0; i < 1000; i++) counter.increment();
        });

        t1.start(); t2.start();
        t1.join(); t2.join();

        System.out.println("Final count: " + counter.count); // Should be 2000
    }
}
```

---

## 🔹 Inter-thread Communication

Used when threads need to communicate — typically in **producer-consumer** problems.

### ✅ Key Methods:

| Method        | Description                            |
| ------------- | -------------------------------------- |
| `wait()`      | Causes thread to wait and release lock |
| `notify()`    | Wakes up a single waiting thread       |
| `notifyAll()` | Wakes up all waiting threads           |

### ✅ Example:

```java
class Shared {
    boolean ready = false;

    synchronized void produce() {
        System.out.println("Producing...");
        ready = true;
        notify(); // signal consumer
    }

    synchronized void consume() {
        if (!ready) {
            try {
                wait();  // wait for producer
            } catch (InterruptedException e) {}
        }
        System.out.println("Consuming...");
    }
}

public class InterThreadCommunication {
    public static void main(String[] args) {
        Shared s = new Shared();

        Thread producer = new Thread(() -> s.produce());
        Thread consumer = new Thread(() -> s.consume());

        consumer.start();
        producer.start();
    }
}
```

---

## ✅ Summary

| Topic                 | Key Point                          |
| --------------------- | ---------------------------------- |
| `Thread` / `Runnable` | Two ways to create threads         |
| `start()` vs `run()`  | `start()` runs thread concurrently |
| `sleep()` / `join()`  | Pause or wait for threads          |
| `isAlive()`           | Check if thread is running         |
| `synchronized`        | Avoids data inconsistency          |
| `wait()` / `notify()` | Enables thread communication       |

---

