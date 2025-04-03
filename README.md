# **📘 Day-15: Java Collections – LinkedList**  
Welcome to **Day-15** of our Java learning journey! Today, we explore the powerful and flexible **`LinkedList`**, a key player in the **Java Collections Framework**.

---

## **📌 Lesson Structure**

### **1️⃣ Recap: Collections Framework**
- The JCF gives us **dynamic data structures** like `List`, `Set`, `Map`.
- Yesterday we worked with `ArrayList` – great for fast reads.

### **2️⃣ What is a LinkedList?**
- A `LinkedList` is a **doubly-linked list**: each node points to the next and previous elements.
- Implements both `List` and `Deque` interfaces.
- Good for **frequent insertions/removals**, especially at the beginning or middle.

---

## **🧠 Key Features of LinkedList**

| Feature                  | Description                             |
|--------------------------|-----------------------------------------|
| 🔗 Structure             | Doubly-linked nodes                     |
| ➕ Insertion/Removal     | Fast at start/middle – O(1)              |
| ❌ Random Access         | Slower – O(n)                            |
| 🔁 Allows Duplicates     | Yes                                      |
| 📈 Memory Overhead       | Higher (node object + two references)    |
| 💡 Implements            | `List`, `Deque`, `Queue`                 |

---

## **🏗️ When to Use LinkedList**

Use `LinkedList` when:
- You need to **frequently insert or remove** elements.
- You're implementing a **queue**, **stack**, or **recent history** list.
- You don’t need **fast access by index**.

---

## **🧪 Live Coding Demo: Recent Files App**

> 🧠 *Let’s build a simple app that tracks your recently opened files, like an IDE or browser history. New files appear at the top, and you can remove the oldest file if needed.*

```java
import java.util.LinkedList;
import java.util.Scanner;

public class RecentFilesApp {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        LinkedList<String> recentFiles = new LinkedList<>();
        boolean running = true;

        System.out.println("📂 Welcome to the Recent Files Tracker!");

        while (running) {
            System.out.println("\nChoose an option:");
            System.out.println("1. Open a file");
            System.out.println("2. View recent files");
            System.out.println("3. Remove the oldest file");
            System.out.println("4. Exit");
            System.out.print("👉 Your choice: ");
            int choice = scanner.nextInt();
            scanner.nextLine();

            switch (choice) {
                case 1:
                    System.out.print("Enter filename: ");
                    String file = scanner.nextLine();
                    recentFiles.addFirst(file);
                    System.out.println(file + " opened.");
                    break;
                case 2:
                    if (recentFiles.isEmpty()) {
                        System.out.println("No files opened yet.");
                    } else {
                        System.out.println("🗂️ Recently Opened Files:");
                        for (String f : recentFiles) {
                            System.out.println("- " + f);
                        }
                    }
                    break;
                case 3:
                    if (!recentFiles.isEmpty()) {
                        String removed = recentFiles.removeLast();
                        System.out.println("Removed: " + removed);
                    } else {
                        System.out.println("Nothing to remove.");
                    }
                    break;
                case 4:
                    running = false;
                    System.out.println("👋 Exiting the app.");
                    break;
                default:
                    System.out.println("❌ Invalid choice.");
            }
        }

        scanner.close();
    }
}
```

---

## 🎯 Hands-on Assignment

👨‍💻 **Assignment: Customer Queue Manager (using LinkedList)**  
You will simulate a simple **bank queue** system using `LinkedList`.

### ✅ Features to implement:
- Add a customer to the end of the queue.
- Serve (remove) the customer at the front.
- View the current queue.
- Show total people waiting.

👉 [Assignment Link on GitHub Classroom](_to be added_)

---

## 🧠 Student Discussion Questions

1. What are the performance benefits of `LinkedList` over `ArrayList`?
2. When should you **not** use `LinkedList`?
3. How does adding at the front differ between `LinkedList` and `ArrayList`?
4. What is the time complexity of `get(index)` in a `LinkedList`?

---

## 📚 Additional Resources

- [LinkedList – Oracle Docs](https://docs.oracle.com/javase/8/docs/api/java/util/LinkedList.html)
- [Java Collections Overview](https://docs.oracle.com/javase/tutorial/collections/intro/index.html)
- [ArrayList vs LinkedList – GeeksForGeeks](https://www.geeksforgeeks.org/arraylist-vs-linkedlist-java/)
- [Video Recording](_to be added_)
- [Lesson Live Coding: LinkedList Deep Dive](_to be added_)

---

🚀 **Well done today! With both ArrayList and LinkedList under your belt, you’re ready to choose the right tool for the job — like a real backend engineer!**  
Tomorrow, we’ll start comparing Lists vs Sets and explore the world of `HashSet`. 🔥

