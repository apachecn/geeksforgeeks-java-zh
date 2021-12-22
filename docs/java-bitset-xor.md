# Java 比特集| xorg

> 哎哎哎:# t0]https://www . geeksforgeeks . org/Java-bit set-xorg/

[位集](https://www.geeksforgeeks.org/bitset-class-java-set-1/)是在 [java.util](https://www.geeksforgeeks.org/java-util-package-java/) 包中定义的一个类。它创建一个由布尔值表示的位数组。

**语法**

```java
public void xor(BitSet set);
```

**解释:**
该方法执行**逻辑异或**，使得在比特集中，当且仅当比特最初具有值 true，并且参数中的对应比特具有值 false 时，比特被设置，反之亦然。

**示例:**

```java
Input : 
set1 : {1, 2, 4}
set2 : {2, 3, 4}

Output :
After performing st1.xor(set2)
set2 : {1, 3}
```

**程序:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program illustrating Bitset Class Function.
import java.util.*;
public class GFG {
    public static void main(String[] args)
    {
        // Constructors of BitSet class
        BitSet bs1 = new BitSet();
        BitSet bs2 = new BitSet(6);

        /* set is BitSet class method
        explained in next articles */
        bs1.set(0);
        bs1.set(1);
        bs1.set(2);
        bs1.set(4);

        // assign values to bs2
        bs2.set(4);
        bs2.set(6);
        bs2.set(5);
        bs2.set(1);
        bs2.set(2);
        bs2.set(3);

        // Printing the 2 Bitsets
        System.out.println("bs1 : " + bs1);
        System.out.println("bs2 : " + bs2);

        // Performing logical AND
        // on bs2 set with bs1
        bs2.xor(bs1);

        // bs2 set after Performing AND
        System.out.println("After Performing XOR :");
        System.out.println(bs2);
    }
}
```

**Output:** 

```java
bs1 : {0, 1, 2, 4}
bs2 : {1, 2, 3, 4, 5, 6}
After Performing XOR :
{0, 3, 5, 6}
```

**相关文章:**

1.  [位集类示例集 1](https://www.geeksforgeeks.org/bitset-class-java-set-1/)
2.  [位集类示例集 2](https://www.geeksforgeeks.org/bitset-class-methods-java-examples-set-2/)
3.  [位集类示例集 3](https://www.geeksforgeeks.org/bitset-class-methods-java-examples-set-3/)