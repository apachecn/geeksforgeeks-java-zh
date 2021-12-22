# Java.util.BitSet 类方法在 Java 中用示例| Set 2

> 原文:[https://www . geesforgeks . org/bitset-class-methods-Java-examples-set-2/](https://www.geeksforgeeks.org/bitset-class-methods-java-examples-set-2/)

```java
Methods discussed in this post:
                       BitSet class methods.
               /      /     |      |       \       \
           set()  xor()  clone() clear()  length()  cardinality()

```

我们强烈建议将以下第 1 组作为先决条件。
**[Java 中的 BitSet 类| Set 1](https://www.geeksforgeeks.org/bitset-class-java-set-1/)**

1.  **set():****Java . util . bitset . set()**方法是将指定索引处的位设置为指定值。
    **语法:**

    ```java
    public void set(int bitpos)
    public void set(int bitpos, boolean val)
    Parameters:
    bitpos : a bit index
    val : a boolean value to set
    Return: Nothing
    Throws: IndexOutOfBoundsException - if the specified index is negative

    ```

2.  **clone():****Java . util . BitSet . clone()**方法克隆一个 BitSet，产生一个与其相等的新 BitSet。该位集的克隆是另一个位集，它具有与该位集完全相同的设为真的位。
    **语法:**

    ```java
    public Object clone()
    Return: a clone of this bit set

    ```

3.  **基数:****Java . util . BitSet . cardinality()**方法用于查找 Bitset 中的元素个数。
    **语法:**

```java
public int cardinality()
Return: the number of bits set to true in this BitSet.

```

```java
// Java program explaining BitSet class methods
// set(), clone(), cardinality()
import java.util.*;
public class NewClasss
{
    public static void main(String[] args)
    {
        BitSet bs1 = new BitSet();
        BitSet bs2 = new BitSet(8);
        BitSet bs3 = new BitSet();

        // assign values to bs1 using set()
        bs1.set(0);
        bs1.set(1);
        bs1.set(2);
        bs1.set(4);

        // assign values to bs2
        bs2.set(4);
        bs2.set(6);
        bs2.set(5);

        // Here we are using .clone() method to make
        // bs3 as bs1
        bs3 = (BitSet) bs1.clone();

        // Printing the 3 Bitsets
        System.out.println("bs1 : " + bs1);
        System.out.println("bs2 : " + bs2);
        System.out.println("bs3 cloned from bs1 : " + bs3);

        // Using .cardinality() method to print the no. of
        // elements of Bitset
        System.out.println("Cardinality of bs1 : " +
                                       bs1.cardinality());
        System.out.println("Cardinality of bs2 : " +
                                       bs2.cardinality());
    }
}
```

输出:

```java
bs1 : {0, 1, 2, 4}
bs2 : {4, 5, 6}
bs3 cloned from bs1 : {0, 1, 2, 4}
Cardinality of bs1 : 4
Cardinality of bs2 : 3

```

*   **clear():****Java . util . BitSet . clear()**方法用于清除元素，即将所有 Bitset 元素设置为 false。
    **语法:**

    ```java
    public void clear(int frompos,int topos)
    public void clear(int bitIndex)
    public void clear()
    Parameters:
    frompos - index of the first bit to be cleared
    topos - index after the last bit to be cleared
    bitIndex - the index of the bit to be cleared
    Throws:
    IndexOutOfBoundsException - if pos value is negative or frompos is larger than topos

    ```

    *   **xor() :** **java.util.BitSet.xor()** method performs the logical Xor operation on the bitsets.
    This bit set is modified so that a bit in it has the value true if and only if :
    *   该位最初的值为 true，参数中对应的位的值为 false。
    *   该位最初的值为 false，参数中对应的位的值为 true。

    **语法:**

    ```java
    public void xor(BitSet set)
    Parameters:
    set - the BitSet with which we need to perform operation

    ```

    *   **length() :** **java.util.BitSet.length()** method return returns logical size of the bitset.
    The index of the highest set bit in the bitset plus one. Returns zero if the bitset contains no set bits.
    **Syntax:**

    ```java
    public int length()
    Returns:
    the logical size of this BitSet

    ```

    ```java
    // Java program explaining BitSet class methods
    //  xor(), length(), clear() methods
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
            System.out.println("bs1 : " + bs1);
            System.out.println("bs2 : " + bs2);

            // use of length() method
            System.out.println("use of length() : " + bs1.length());

            // use of xor() to perform logical Xor operation
            bs1.xor(bs2);
            System.out.println("Use of xor() : " + bs1);
            bs2.xor(bs1);
            System.out.println("Use of xor() : " + bs2);

            // clear from index 2 to index 4 in bs1
            bs2.clear(1, 2);
            System.out.println("bs2 after clear method : " + bs2);

            // clear complete Bitset
            bs1.clear();
            System.out.println("bs1 after clear method : " + bs1);
        }
    }
    ```

    输出:

    ```java
    bs1 : {1, 2, 3, 4, 6, 7}
    bs2 : {2, 3, 4, 6, 9}
    use of length() : 8
    Use of xor() : {1, 7, 9}
    Use of xor() : {1, 2, 3, 4, 6, 7}
    bs2 after clear method : {2, 3, 4, 6, 7}
    bs1 after clear method : {}

    ```

     **[Java 中的 BitSet 类方法示例| Set 3](https://www.geeksforgeeks.org/bitset-class-methods-java-examples-set-3/)**

    **参考文献:**
    [https://docs . Oracle . com/javase/7/docs/API/Java/util/bitset . html](https://docs.oracle.com/javase/7/docs/api/java/util/BitSet.html)

    本文由**莫希特·古普塔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。