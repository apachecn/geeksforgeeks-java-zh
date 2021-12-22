# Java 中参数是如何传递的？

> 原文:[https://www.geeksforgeeks.org/g-fact-45/](https://www.geeksforgeeks.org/g-fact-45/)

**详见[本](https://www.geeksforgeeks.org/g-fact-31-java-is-strictly-pass-by-value/)。**

在 Java 中，参数总是按值传递的。例如，以下程序打印 i = 10，j = 20。

```java
//  Test.java
class Test {
   // swap() doesn't swap i and j
   public static void swap(Integer i, Integer j) {
      Integer temp = new Integer(i);
      i = j;
      j = temp;
   }
   public static void main(String[] args) {
      Integer i = new Integer(10);
      Integer j = new Integer(20);
      swap(i, j);
      System.out.println("i = " + i + ", j = " + j);
   }
}
```

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。