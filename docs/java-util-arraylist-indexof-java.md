# Java.util.Arraylist.indexOf()在 Java 中的应用

> 哎哎哎:# t0]https://www . geeksforgeeks . org/Java-util-array list-index of-Java/

[**数组列表**](https://www.geeksforgeeks.org/arraylist-in-java/) 的 **indexOf()** 方法返回该列表中指定元素的**第一次出现的**的索引，如果该列表不包含该元素，则返回 **-1** 。

**语法:**

```java
public int IndexOf(Object o)
obj : The element to search for.

```

```java
// Java code to demonstrate the working of
// indexOf in ArrayList

// for ArrayList functions
import java.util.ArrayList;

public class IndexOfEx {
  public static void main(String[] args) {

  // creating an Empty Integer ArrayList
  ArrayList<Integer> arr = new ArrayList<Integer>(5);

  // using add() to initialize values
  arr.add(1);
  arr.add(2);
  arr.add(3);
  arr.add(4);

  // printing initial value
  System.out.print("The initial values in ArrayList are : ");
  for (Integer value : arr) {
  System.out.print(value);
  System.out.print(" ");
  }  

  // using indexOf() to find index of 3
  int pos =arr.indexOf(3);

  // prints 2
  System.out.println("\nThe element 3 is at index : " + pos);
  }

}   
```

输出:

```java
The initial values in ArrayList are : 1 2 3 4 
The element 3 is at index : 2

```

**实际应用:**指数函数主要用于**确定事件的最后一次或第一次出现**，例如骰子掷中 6 的最后一次出现，或名称中任何字母的第一次出现等。

**再举一个例子:**

```java
// Java code to demonstrate the application of
// index functions in ArrayList

// for ArrayList functions
import java.util.ArrayList;

public class AppliIndex {
  public static void main(String[] args) {

  // creating an Empty Integer ArrayList
  ArrayList<Integer> arr = new ArrayList<Integer>(10);

  // using add() to initialize dice values
  arr.add(1);
  arr.add(2);
  arr.add(4);
  arr.add(6);
  arr.add(5);
  arr.add(2);
  arr.add(6);
  arr.add(1);
  arr.add(6);
  arr.add(4);

  // using IndexOf() to find first index of 6
  int pos1 =arr.indexOf(6);

  // using lastIndexOf() to find last index of 6
  int pos2 =arr.lastIndexOf(6);

  // to balance 0 based indexing
  pos1 = pos1+1;
  pos2 = pos2+1;

  // printing first index of 6
  System.out.println("The first occurrence of 6 is  : " + pos1);

  // printing last index of 6
  System.out.println("The last occurrence of 6 is  : " + pos2);

  }

}   
```

输出:

```java
The first occurrence of 6 is  : 4
The last occurrence of 6 is  : 9

```

本文由**香巴拉维·辛格**供稿。如果你喜欢极客博客并想投稿，你也可以用 contribute.geeksforgeeks.org 写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。