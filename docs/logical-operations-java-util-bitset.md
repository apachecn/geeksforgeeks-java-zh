# Java.util.Bitset 类|逻辑运算

> 原文:[https://www . geesforgeks . org/logic-operations-Java-util-bitset/](https://www.geeksforgeeks.org/logical-operations-java-util-bitset/)

Bitset 类还允许对两个 bitset 进行一些逻辑操作。支持的逻辑运算有:and、andNot、or、Xor。这些将在本文中讨论。

**1。和(位集设置):**该方法对该目标位集和自变量位集执行**逻辑“与”**，并返回第二位集中也存在的第一位集的值。

```java
Declaration : 
 public void and(BitSet set)
Parameters : 
    set :  a bit set
Return Value : 
   This method does not return a value.   

```

```java
// Java code to demonstrate the working
// of and(Bitset set) in Bitset
import java.util.*;
public class BitSetAnd {

public static void main(String[] args)
    {

        // Declaring 2 bitsets
        BitSet bset1 = new BitSet(5);
        BitSet bset2 = new BitSet(5);

        // adding the values to bset1
        // using set()
        bset1.set(0);
        bset1.set(1);
        bset1.set(2);
        bset1.set(3);

        // adding the values to bset2
        // using set()
        bset2.set(2);
        bset2.set(4);
        bset2.set(6);
        bset2.set(0);

        // printing the initial sets
        System.out.println("The elements of Bitset 1 are : " + bset1);

        System.out.println("The elements of Bitset 2 are : " + bset2);

        // perform "and" operation between two bitsets
        // using and()
        bset1.and(bset2);

        // printing the new bset1
        System.out.println("The resultant bset1 after and operation is : " + bset1);
    }
}
```

输出:

```java
The elements of Bitset 1 are : {0, 1, 2, 3}
The elements of Bitset 2 are : {0, 2, 4, 6}
The resultant bset1 after and operation is : {0, 2}

```

**2。andNot(位集):**此方法执行**逻辑与非**，并返回第一个位集的元素，这些元素不在参数位集中。

```java
Declaration : 
 public void andNot(BitSet set)
Parameters : 
   set: the BitSet with which to mask this BitSet.
Return Value : 
   This method does not return a value.

```

```java
// Java code to demonstrate the working
// of andNot(Bitset set) in Bitset
import java.util.*;
public class BitSetNotAnd {

public static void main(String[] args)
    {

        // Declaring 2 bitsets
        BitSet bset1 = new BitSet(5);
        BitSet bset2 = new BitSet(5);

        // adding the values to bset1
        // using set()
        bset1.set(0);
        bset1.set(1);
        bset1.set(2);
        bset1.set(3);

        // adding the values to bset2
        // using set()
        bset2.set(2);
        bset2.set(4);
        bset2.set(6);
        bset2.set(0);

        // printing the initial sets
        System.out.println("The elements of Bitset 1 are : " + bset1);

        System.out.println("The elements of Bitset 2 are : " + bset2);

        // perform "not-and" operation between two bitsets
        // using andNot()
        bset1.andNot(bset2);

        // printing the new bset1
        System.out.println("The resultant bset1 after andNot operation is : " + bset1);
    }
}
```

输出:

```java
The elements of Bitset 1 are : {0, 1, 2, 3}
The elements of Bitset 2 are : {0, 2, 4, 6}
The resultant bset1 after andNot operation is : {1, 3}

```

**3。或(位集设置):**该方法对该目标位集和参数位集执行**逻辑或**，并返回两个位集中的**所有值，不返回重复的**元素。

```java
Declaration : 
 public void or(BitSet set)
Parameters : 
    set :  a bit set
Return Value : 
   This method does not return a value.   

```

```java
// Java code to demonstrate the working
// of or(Bitset set) in Bitset
import java.util.*;
public class BitSetOr {

public static void main(String[] args)
    {

        // Declaring 2 bitsets
        BitSet bset1 = new BitSet(5);
        BitSet bset2 = new BitSet(5);

        // adding the values to bset1
        // using set()
        bset1.set(0);
        bset1.set(1);
        bset1.set(2);
        bset1.set(3);

        // adding the values to bset2
        // using set()
        bset2.set(2);
        bset2.set(4);
        bset2.set(6);
        bset2.set(0);

        // printing the initial sets
        System.out.println("The elements of Bitset 1 are : " + bset1);

        System.out.println("The elements of Bitset 2 are : " + bset2);

        // perform "or" operation between two bitsets
        // using or()
        bset1\. or (bset2);

        // printing the new bset1
        System.out.println("The resultant bset1 after or operation is : " + bset1);
    }
}
```

输出:

```java
The elements of Bitset 1 are : {0, 1, 2, 3}
The elements of Bitset 2 are : {0, 2, 4, 6}
The resultant bset1 after or operation is : {0, 1, 2, 3, 4, 6}

```

**4。异或(位集):**该方法执行**逻辑异或**，并返回存在于一个位集中但不存在于另一个位集中的那些元素**。**

```java
Declaration : 
   public void xor(BitSet set)
Parameters : 
    set a bit set.
Return Value : 
   This method does not return a value.

```

```java
// Java code to demonstrate the working
// of xor(Bitset set) in Bitset
import java.util.*;
public class BitSetXor {

public static void main(String[] args)
    {

        // Declaring 2 bitsets
        BitSet bset1 = new BitSet(5);
        BitSet bset2 = new BitSet(5);

        // adding the values to bset1
        // using set()
        bset1.set(0);
        bset1.set(1);
        bset1.set(2);
        bset1.set(3);

        // adding the values to bset2
        // using set()
        bset2.set(2);
        bset2.set(4);
        bset2.set(6);
        bset2.set(0);

        // printing the initial sets
        System.out.println("The elements of Bitset 1 are : " + bset1);

        System.out.println("The elements of Bitset 2 are : " + bset2);

        // perform "xor" operation between two bitsets
        // using xor()
        bset1\. xor (bset2);

        // printing the new bset1
        System.out.println("The resultant bset1 after xor operation is : " + bset1);
    }
}
```

输出:

```java
The elements of Bitset 1 are : {0, 1, 2, 3}
The elements of Bitset 2 are : {0, 2, 4, 6}
The resultant bset1 after xor operation is : {1, 3, 4, 6}

```

本文由 [**阿斯特哈·泰亚吉**](https://auth.geeksforgeeks.org/profile.php?user=Astha Tyagi&list=practice) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。