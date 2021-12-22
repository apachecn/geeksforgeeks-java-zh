# Java 中的 Java.util.BitSet.get()

> 原文:[https://www.geeksforgeeks.org/java-util-bitset-get-java/](https://www.geeksforgeeks.org/java-util-bitset-get-java/)

Bitset 中有两个 get()的**变体，本文将对这两个变体进行讨论。**

**1.**布尔 get( int 值):**如果位集中存在**值，则返回 true，否则返回 false。****

```java
****Declaration :** 
public boolean get(int value)
**Parameters :** 
**value :** The value to check.
**Return Value :** 
Returns boolean true, if element present else returns false.** 
```

 ```java
// Java code to demonstrate the
// working of get() in Bitset

import java.util.*;

public class BitGet1 {

public static void main(String[] args)
    {

        // declaring bitset
        BitSet bset = new BitSet(5);

        // adding values using set()
        bset.set(0);
        bset.set(1);
        bset.set(2);
        bset.set(4);

        // checking if 3 is in BitSet
        System.out.println("Does 3 exist in Bitset? : " + bset.get(3));

        // checking if 4 is in BitSet
        System.out.println("Does 4 exist in Bitset? : " + bset.get(4));
    }
}
```** 

输出:

```java
Does 3 exist in Bitset? : false
Does 4 exist in Bitset? : true

```

2. **BitSet get(int fromval，int toval) :** 方法返回一个新的 Bitset，该 Bitset 由从 fromvale(包含)到 toval(不包含)的 Bitset 中存在的元素组成。

```java
Declaration : 
public BitSet get(int fromval, int toval)
Parameters : 

fromval :  first value to include.
toval : last value to include(ex).

Return Value
This method returns a new BitSet from a range of this BitSet.

```

```java
// Java code to demonstrate the
// working of get(int fromval, int toval)
// in Bitset

import java.util.*;

public class BitGet2 {

public static void main(String[] args)
    {

        // declaring bitset
        BitSet bset = new BitSet(5);

        // adding values using set()
        bset.set(0);
        bset.set(1);
        bset.set(2);
        bset.set(3);

        // Printing values in range 0-2
        System.out.println("Values in BitSet from 0-2 are : " + bset.get(0, 3));
    }
}
```

输出:

```java
Values in BitSet from 0-2 are : {0, 1, 2}

```

本文由 **Astha Tyagi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。**