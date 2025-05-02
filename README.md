# **📘 Day-15: Java Collections – LinkedList vs ArrayList**

Welcome to **Day-15** of our Java backend journey! Today, we dove into the **world of Java Collections**, focusing on the **differences between `ArrayList` and `LinkedList`** – two of the most widely used list implementations in the Java ecosystem. Grasping their internal data structures helps you write more **performance-aware** code.

---

## **📌 Lesson Structure**

### **1️⃣ Introduction to Java Lists**

* `ArrayList` and `LinkedList` both implement the **List interface**.
* But under the hood, their **data structures** are very different.

---

## **📂 Data Structure Visualizations**

### **🔷 ArrayList**

Internally uses a **resizable array** (like `String[]`).

#### 📊 Visualization:

```
Index:     0     1     2     3     4
          [A]   [B]   [C]   [D]   [E]

Operation Cost:
- get(3) → Fast (O(1))
- add/remove at end → Fast
- add/remove at start → Slow (O(n))
```

### **🔷 LinkedList**

Built as a **doubly linked list** with nodes.

#### 🔗 Visualization:

```
NULL ← [A] ⇄ [B] ⇄ [C] ⇄ [D] ⇄ [E] → NULL

Each Node:
- value
- pointer to previous
- pointer to next

Operation Cost:
- get(3) → Slower (O(n))
- add/remove at start → Fast (O(1))
- add/remove in middle → Moderate (O(n))
```

---

## **🔍 Key Differences**

| Feature              | ArrayList             | LinkedList          |
| -------------------- | --------------------- | ------------------- |
| **Data Structure**   | Dynamic Array         | Doubly Linked List  |
| **Access (get/set)** | O(1) – Fast           | O(n) – Slower       |
| **Insert at Start**  | O(n) – Slow (shift)   | O(1) – Fast         |
| **Insert at End**    | O(1)\* – Usually Fast | O(1) – Fast         |
| **Memory Usage**     | Less (no pointers)    | More (pointers)     |
| **Iteration**        | Better cache usage    | Slower due to nodes |

> \* Note: When the array is full, `ArrayList` resizes itself (new array = old size × 1.5)

---

## **🧪 Code Demonstration**

### **📌 ArrayList Example**

```java
List<String> arrayList = new ArrayList<>();
arrayList.add("Java");
arrayList.add("Python");
arrayList.add("C++");

System.out.println(arrayList.get(1)); // Python
```

### **📌 LinkedList Example**

```java
List<String> linkedList = new LinkedList<>();
linkedList.add("Java");
linkedList.add("Python");
linkedList.add("C++");

System.out.println(linkedList.get(1)); // Python
```

---

## **🧠 When to Use What?**

### ✅ Use `ArrayList` when:

* Frequent **access (get/set)** operations
* Memory optimization matters
* You rarely add/remove in the middle

### ✅ Use `LinkedList` when:

* Frequent **insertions/deletions**, especially at the start/middle
* Don’t need fast random access

---

## **🎯 Practice Challenges**

✅ Create an `ArrayList` and a `LinkedList`, perform the same operations, and compare performance.
✅ Implement a queue using `LinkedList`.
✅ Try reversing both lists manually.
✅ Measure time taken for `get(i)` for 1 million items.

---

## **📚 Additional Resources**

* [Baeldung: LinkedList vs ArrayList](https://www.baeldung.com/java-arraylist-vs-linkedlist)
* [GeeksForGeeks: Java Collections](https://www.geeksforgeeks.org/collections-in-java-2/)
* [Oracle Docs: List Interface](https://docs.oracle.com/javase/8/docs/api/java/util/List.html)

---

## **🎥 Video Lesson Recording**

📺 [*Video Lesson Recording*](https://us06web.zoom.us/rec/share/luRZaAabElxI8T5WoKT4HRSLo3T8B9ycvQyvGbzNJQ0Ihft_nP8YDPdtay3aP29W.OF-dFZdaTvvyTTTE?startTime=1743756552000)



---

🚀 **Excellent work today! Understanding data structures like these makes you a true Java warrior. See you in the next session for more backend wizardry! (No, Java does *not* count as wizardry 😄)**


