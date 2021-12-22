# Java 中的 Java.util.BitSet.set()方法

> 原文:[https://www . geesforgeks . org/Java-util-bitset-set-method-Java/](https://www.geeksforgeeks.org/java-util-bitset-set-method-java/)

set()方法有**四个**变体。本文描述了所有这些，如下所示:

**1。set(int Index) :** 此方法将指定索引处的位设置为 true，即添加一个值。

```
Declaration : 
public void set(int bitIndex)
Parameters : 
     Index :  a bit index.
Result : 
  This method does not return a value.
Exception : 
     IndexOutOfBoundsException :  if the specified index is negative.

```

```
// Java code to demonstrate the working
// of set() in BitSet
import java.util.*;
public class BitSet1 {
public static void main(String[] args)
    {
        // creating two bitsets
        BitSet bset = new BitSet(5);

        // assigning value using set()
        bset.set(3);
        bset.set(5);

        // printing the bitset
        System.out.println("The constructed bitset is : " + bset);
    }
}
```

输出:

```
The constructed bitset is : {3, 5}

```

**2。set(int num，布尔值):**此方法将指定索引处的位设置为指定值，如果布尔值为 true，则添加值，否则不添加。

```
Declaration : 
  public void set(int num, boolean value)
Parameters : 
   num :  a bit value.
   value :  a boolean value to set.
Return Value
    This method does not return a value.

```

```
// Java code to demonstrate the working
// of set(num, value) in BitSet
import java.util.*;
public class BitSet2 {
public static void main(String[] args)
    {
        // creating two bitsets
        BitSet bset = new BitSet(5);

        // assigning value using set(num, value)
        // adds 3
        bset.set(3, true);

        // doesn't add 5
        bset.set(5, false);
        bset.set(7, true);
        bset.set(4, false);

        // printing the bitset
        System.out.println("The constructed bitset is : " + bset);
    }
}
```

输出:

```
The constructed bitset is : {3, 7}

```

**3。set(int fromnum，int tonum) :** 此方法将从指定 fromnum(包括)到指定 tonum(不包括)的位设置为 true，即**将 fromnum 的值与 tonum-1** 相加。

```
Declaration : 
   public void set(int fromnum, int tonum)
Parameters : 
    fromnum :  value to start insert.
    tonum :  value to end insertion.
Return Value : 
   This method does not return a value.

```

```
// Java code to demonstrate the working
// of set(fromnum, tonum) in BitSet
import java.util.*;
public class BitSet3 {
public static void main(String[] args)
    {
        // creating two bitsets
        BitSet bset = new BitSet(9);

        // assigning value using set(fromnum, tonum)
        // adds 3 to 8
        bset.set(3, 9);

        // printing the bitset
        System.out.println("The constructed bitset is : " + bset);
    }
}
```

输出:

```
The constructed bitset is : {3, 4, 5, 6, 7, 8}

```

**4。set(int fromnum，int tonum，布尔值):**此方法将指定 fromnum(包括)到指定 tonum(不包括)的位设置为指定值，即插入 fromnum 到 tonum-1 **如果传递的布尔值为真，否则不插入**。

```
Declaration : 
  public void set(int fromnum, int tonum, boolean value)
Parameters : 
   fromnum :  num to start inserting.
   tonum :  last number of insertion.
   value :  value to set the selected bits to.
Return Value : 
   This method does not return a value.

```

```
// Java code to demonstrate the working
// of set(fromnum, tonum, value) in BitSet
import java.util.*;
public class BitSet4 {
public static void main(String[] args)
    {
        // creating two bitsets
        BitSet bset = new BitSet(9);

        // assigning value using set(fromnum, tonum, value)
        // doesn't adds 3 to 8
        bset.set(3, 9, false);

        // assigning value using set(fromnum, tonum, value)
        // adds 5 to 10
        bset.set(5, 11, true);

        // printing the bitset
        System.out.println("The constructed bitset is : " + bset);
    }
}
```

输出:

```
The constructed bitset is : {5, 6, 7, 8, 9, 10}

```

本文由 **Astha Tyagi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。