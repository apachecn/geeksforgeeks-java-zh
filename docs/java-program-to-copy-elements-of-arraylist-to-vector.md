# 将数组列表的元素复制到向量的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到数组列表元素到向量的复制/](https://www.geeksforgeeks.org/java-program-to-copy-elements-of-arraylist-to-vector/)

Vector 实现了 List Interface，就像 [ArrayList](https://www.geeksforgeeks.org/arraylist-in-java/) 一样，它也保持插入顺序，但是它很少在非线程环境中使用，因为它是同步的，因此它在元素的添加、搜索、删除和更新方面表现不佳。若要将元素从一个集合复制到其他集合，请在初始化时将数组列表的对象传递给[向量](https://www.geeksforgeeks.org/java-util-vector-class-java/)的构造函数，或者使用迭代逐元素复制。

**方法 1:**

```java
Vector<Integer> vector = new Vector<>(arrayList);
```

1.  Create a Vector object, and pass the ArrayList object in the constructor at initialization.
2.  Print vectors.

下面是上述方法的实现:

## Java

T0T7**输出**

```java
[Rohan, Sangeeta, Ritik, Yogesh]
```