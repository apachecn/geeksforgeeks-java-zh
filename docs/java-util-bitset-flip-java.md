# Java 中的 Java.util.BitSet.flip()

> 原文:[https://www.geeksforgeeks.org/java-util-bitset-flip-java/](https://www.geeksforgeeks.org/java-util-bitset-flip-java/)

flip()方法有两个**变体。本文对所有这些进行了如下描述:**

****1。flip(int 值):**此方法移除参数中指定的值。**

```java
**public void flip(int value)**

**Parameters :** 
**value : ** the value to flip.
**Return Value**This method does not return a value. 
```

```java
// Java code to demonstrate the
// working of flip(int value) in Bitset

import java.util.*;

public class Flip1 {
  public static void main(String[] args) {

  // declaring bitset
  BitSet bset = new BitSet(6);

  // assigning values to bset
  bset.set(0);
  bset.set(1);
  bset.set(2);
  bset.set(3);

  // printing the original set
  System.out.println("The original bitset is : " + bset);

  // using flip() to remove 2
  bset.flip(2);

  //  printing final bitset
  // 2 is removed
  System.out.println("The flipped bitset is : " + bset);
  }
}
```

**输出:**

```java
The original bitset is : {0, 1, 2, 3}
The flipped bitset is : {0, 1, 3} 
```

****2。flip(int fromnum，int tonum) :** 此方法将从指定 fromnum(包括)到指定 tonum(不包括)的每个位设置为其当前值的补码，即**移除 fromnum 到 tonum-1 的值**。**

```java
**public void flip(int fromnum,int tonum)**
**Parameters :** 
**fromnum : ** start number to begin flipping.
**tonum : ** last-1 number to end flipping.
**Return Value :** 
This method does not return a value. 
```

```java
// Java code to demonstrate the
// working of flip(int fromnum, int tonum) in Bitset

import java.util.*;

public class Flip2 {
  public static void main(String[] args) {

  // declaring bitset
  BitSet bset = new BitSet(6);

  // assigning values to bset
  bset.set(0);
  bset.set(1);
  bset.set(2);
  bset.set(3);

  // printing the original set
  System.out.println("The original bitset is : " + bset);

  // using flip(fromnum,tonum) to remove 1 and 2
  bset.flip(1,3);

  //  printing final bitset
  // 1 and 2 are removed
  System.out.println("The flipped bitset is : " + bset);
  }
}
```

**输出:**

```java
The original bitset is : {0, 1, 2, 3}
The flipped bitset is : {0, 3} 
```

**本文由 **Astha Tyagi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。**