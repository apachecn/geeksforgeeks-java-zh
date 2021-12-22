# Java 中的 Java.util.BitSet.clear()

> 原文:[https://www.geeksforgeeks.org/java-util-bitset-clear-java/](https://www.geeksforgeeks.org/java-util-bitset-clear-java/)

**清()法有**三个**变型:**

1.  **clear() :** The clear() method sets all of the bits in this BitSet to false.

    ```
    public void clear()
    Return Value
    This method does not return a value.

    ```

    ```
    // Java code to demonstrate the working
    // of clear() in BitSet
    import java.util.*;
    public class BitClr1 {
    public static void main(String[] args)
        {

            // Declaring Bitset
            BitSet bset = new BitSet(8);

            // assigning values to bitset
            for (int i = 0; i < 5; i++)
                bset.set(i);

            // printing original bitset
            System.out.println
            ("The bitset before clear() operation is : " + bset);

            // using clear() to clear contents of bitset
            bset.clear();

            // printing bitset after clear() operation
            // empty bitset
            System.out.println
            ("The bitset after clear() operation is : " + bset);
        }
    }
    ```

    输出:

    ```
    The bitset before clear() operation is : {0, 1, 2, 3, 4}
    The bitset after clear() operation is : {}

    ```

2.  **clear(int pos) :** The clear(int pos) method sets the bit specified by the index to false. i.e **removes from bitset**.

    ```
    public void clear(int pos)
    Parameters
       pos : the index of the bit to be cleared.
    Return Value
    This method does not return a value.
    Exception
       IndexOutOfBoundsException : if the specified index is negative.

    ```

    ```
    // Java code to demonstrate the working
    // of clear(int pos) in BitSet
    import java.util.*;
    public class BitClr2 {
    public static void main(String[] args)
        {

            // Declaring Bitset
            BitSet bset = new BitSet(8);

            // assigning values to bitset
            for (int i = 0; i < 5; i++)
                bset.set(i);

            // printing original bitset
            System.out.println
            ("The bitset before clear(pos) operation is : " + bset);

            // using clear(pos) to clear element at specified position
            bset.clear(3);

            // printing bitset after clear(pos) operation
            // removes 3
            System.out.println
            ("The bitset after clear(pos) operation is : " + bset);
        }
    }
    ```

    输出:

    ```
    The bitset before clear(pos) operation is : {0, 1, 2, 3, 4}
    The bitset after clear(pos) operation is : {0, 1, 2, 4}

    ```

3.  **clear(int frompos, int topos) :** The clear(int frompos, int topos) method sets the bits from the specified frompos (inclusive) to the specified topos (exclusive) to false i.e **performs removal in a range**.

    ```
    public void clear(int frompos, int topos)
    Parameters
        frompos : index of the first bit to be cleared
        topos : index of the last bit to be cleared
    Return Value
    This method does not return a value.
    Exception
        IndexOutOfBoundsException: if frompos is negative, 
    or topos is negative, or frompos is larger than topos.

    ```

    ```
    // Java code to demonstrate the working
    // of clear(int frompos, int topos) in BitSet
    import java.util.*;
    public class BitClr3 {
    public static void main(String[] args)
        {

            // Declaring Bitset
            BitSet bset = new BitSet(8);

            // assigning values to bitset
            for (int i = 0; i < 5; i++)
                bset.set(i);

            // printing original bitset
            System.out.println
            ("The bitset before clear(frompos, topos) operation is : " + bset);

            // using clear(frompos, topos) to clear elements in range
            bset.clear(2, 4);

            // printing bitset after clear(frompos, topos) operation
            // removes 2, 3
            System.out.println
            ("The bitset after clear(frompos, topos) operation is : " + bset);
        }
    }
    ```

    输出:

    ```
    The bitset before clear(frompos, topos) operation is : {0, 1, 2, 3, 4}
    The bitset after clear(frompos, topos) operation is : {0, 1, 4}

    ```

本文由 **Astha Tyagi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。