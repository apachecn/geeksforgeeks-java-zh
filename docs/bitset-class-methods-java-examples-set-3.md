# Java 中的 BitSet 类方法，带示例| Set 3

> 原文:[https://www . geesforgeks . org/bitset-class-methods-Java-examples-set-3/](https://www.geeksforgeeks.org/bitset-class-methods-java-examples-set-3/)

```
                       BitSet class methods in Set 3.
               /      /      |       |     |       \      \
            and  notand    flip  isEmpty  equal   get   intersect

```

[Java 中的 BitSet 类方法，带示例| Set 2](https://www.geeksforgeeks.org/bitset-class-methods-java-examples-set-2/)

**BitSet 类方法解释如下:**

1.  **和/notand:****java.util.BitSet . and()**和**Java . util . bitset . notand()**方法是一个 Java . util . bitset 类方法。
    。and()方法执行位集(目标)的逻辑与运算，位集作为参数传递。当且仅当两个被操作的位都为真时，这将返回一个位(置位)。
    。notand()方法–使用此方法

    ```
    Syntax:
    public void and(BitSet bitset)
               or
    public void andNot(BitSet bitste)
    Parameters:
    bitset - set to perform the operation

    ```

    清除所有设置了相应位的位
2.  **equal:**T3】Java . util . BitSet . equal()方法在比较两个 bitset 时发挥作用。它是通过比较一个物体和其他物体来实现的。

    ```
    Syntax:
    public boolean equals(Object o)
    Parameters: 
    o - the object to compare with
    Overrides: equals in class Object
    Return: if object are same then true; otherwise false

    ```

3.  **get() :** **java.util.BitSet.get()** method creates a new BitSet with elements from the given Bitset having positions from from_Index (inclusive) to_Index(exclusive).

    ```
    Syntax:
    public BitSet get(int from_Index,  int to_Index)
    Parameters:
    from_Index - index of the first bit of given BitSet to include
    to_Index - index after the last bit of the BitSet to include
    Throws:
    IndexOutOfBoundsException - if from_Index is negative, or to_Index is negative,
                                or from_Index is larger than to_Index

    ```

    **解释 and()，notand()，equal()，get()方法使用的 Java 代码。**

    ```
    // Java program explaining BitSet class methods
    // and(), notand(), equal(), get()
    import java.util.*;
    public class GFG
    {
        public static void main(String[] args)
        {
            BitSet bs1 = new BitSet();
            BitSet bs2 = new BitSet();

            // assign values to bs1 using set()
            bs1.set(7);
            bs1.set(1);
            bs1.set(2);
            bs1.set(4);
            bs1.set(3);
            bs1.set(6);

            // assign values to bs2
            bs2.set(4);
            bs2.set(6);
            bs2.set(3);
            bs2.set(9);
            bs2.set(2);

            // Printing the Bitsets
            System.out.println("bs1         : " + bs1);
            System.out.println("bs2         : " + bs2);

            // use of get() to get index 3 to 6 of bs1
            System.out.println("\nUse of get() on bs1 : "
                                          + bs1.get(1,4));

            // use of get() to get index 1 to 4 of bs2
            System.out.println("Use of get() on bs2 : "
                                        + bs2.get(1,4));

            // perform not operation in b/w the sets
            bs1.andNot(bs2);
            System.out.println("\nNot b/w bs1 and bs2 : " + bs1);

            // perform and operation between two bitsets
            bs1.and(bs2);
            System.out.println("And b/w bs1 and bs2 : "  + bs1);

            // equal() method to compare the bs1 and bs2
            if (bs1.equals(bs2))
                System.out.println("\nUsing equal method : Equal");
            else
                System.out.println("\nUsing equal method : Not Equal");
        }
    }
    ```

    输出:

    ```
    bs1         : {1, 2, 3, 4, 6, 7}
    bs2         : {2, 3, 4, 6, 9}

    Use of get() on bs1 : {0, 1, 2}
    Use of get() on bs2 : {1, 2}

    Not b/w bs1 and bs2 : {1, 7}
    And b/w bs1 and bs2 : {}

    Using equal method : Not Equal

    ```

4.  **flip():****Java . util . bitset . flip(from_Index，to_Index)** 方法将从给定的 from _ Index(包含)到指定的 to_Index(不包含)的每个位设置为当前值的补码。

    ```
    Syntax:
    public void flip(int from_Index, int to_Index)
    Parameters:
    from_Index - index of the first bit of the given BitSet to flip
    to_Index - index after the last bit of the given BitSet to flip
    Throws:
    IndexOutOfBoundsException - if from_Index is negative, or to_Index is negative, 
                                or from_Index is larger than to_Index

    ```

5.  **intersect():****Java . util . BitSet . intersect()**如果目标 BitSet 和给定 BitSet 中的位都被设置，则方法返回 true。

    ```
    Syntax:
    public boolean intersects(BitSet set)
    Parameters:
    set - BitSet to intersect with
    Returns: true if the given BitSet intersects the target BitSet

    ```

6.  **isEmpty() :** **java.util.BitSet.isEmpty()** method whether there is any bit, that is set to true or not in the given Bitset.

    ```
    Syntax:
    public boolean isEmpty()
    Return: boolean indicating whether the given BitSet is empty

    ```

    **解释 intersect()，isEmpty()，flip()方法使用的 Java 代码。**

    ```
    // Java program explaining BitSet class methods
    // intersect(), isEmpty(), flip() methods
    import java.util.*;
    public class NewClass
    {
        public static void main(String[] args)
        {
            BitSet bs1 = new BitSet();
            BitSet bs2 = new BitSet();

            // assign values to bs1 using set()
            bs1.set(7);
            bs1.set(1);
            bs1.set(2);
            bs1.set(4);
            bs1.set(3);
            bs1.set(6);

            // assign values to bs2
            bs2.set(4);
            bs2.set(6);
            bs2.set(3);
            bs2.set(9);
            bs2.set(2);

            // Printing the Bitsets
            System.out.println("bs1      : " + bs1);
            System.out.println("bs2      : " + bs2);
            System.out.println("");

            // use of intersect() to check if the bitsets
            // intersects
            System.out.println("Using intersect() : "
                         + bs2.intersects(bs1));

            // use of flip() from_index - 1 to_index - 5
            bs1.flip(1,5);
            System.out.println("\nbs1 using flip : " + bs1);

            // use of flip() from_index - 2 to_index - 4
            bs2.flip(2,4);
            System.out.println("bs2 using flip : " + bs2);
            System.out.println("");

            // use of isEmpty() to check if bitsets are empty
            System.out.println("Use of isEmpty() : "
                                + bs1.isEmpty());
            System.out.println("Use of isEmpty() : "
                                 + bs2.isEmpty());
        }
    }
    ```

    输出:

    ```
    bs1      : {1, 2, 3, 4, 6, 7}
    bs2      : {2, 3, 4, 6, 9}

    Using intersect() : true

    bs1 using flip : {6, 7}
    bs2 using flip : {4, 6, 9}

    Use of isEmpty() : false
    Use of isEmpty() : false

    ```

    **参考文献:**
    [https://docs . Oracle . com/javase/7/docs/API/Java/util/bitset . html](https://docs.oracle.com/javase/7/docs/api/java/util/BitSet.html)

    本文由 <font color="green">**莫希特·古普塔**</font> 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。