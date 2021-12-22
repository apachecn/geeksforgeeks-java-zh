# 洗牌矢量元素的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序转洗牌-向量-元素/](https://www.geeksforgeeks.org/java-program-to-shuffle-vector-elements/)

向量基本上属于遗留类，但现在它与集合完全兼容。Java 有很多内置函数，可以对集合或其他数据类型执行不同的操作，其中之一就是 **shuffle。**对矢量元素[进行洗牌，使用](https://www.geeksforgeeks.org/collections-shuffle-java-examples/)方法。Collections 类的 shuffle 方法使用随机的默认来源对指定的 Vector 对象的元素进行 shuffle。它随机置换传入参数的向量元素。

shuffle()方法的应用

*   它用于加密应用。
*   为付款字段生成唯一的交易编号。
*   火箭、卫星、飞机、密码学中的软件利用随机化在算法上获得良好结果的概率很高。

集合洗牌功能也可以通过两种方式调用:

1.  **指定随机性的随机参数。**
2.  **无参数。**

[**洗牌** **方法**](https://www.geeksforgeeks.org/shuffle-or-randomize-a-list-in-java/) 使用默认随机性源从矢量中选择随机元素。这个函数不需要太多时间，并且以线性时间运行，每次执行的结果可能不同。

**等级等级:**

```
java
   ↳ util 
      ↳ Collections 
```

**语法:**

```
Collections.shuffle(vector).
```

**参数:**你要通过的向量将被洗牌。

**返回:**混洗功能混洗矢量元素。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to shuffle Vector Elements

// Importing libraries
import java.util.Vector;
import java.util.Collections;

public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Create a Vector object
        Vector<String> vec = new Vector<String>();

        // Add elements to Vector(Random)
        vec.add("5");
        vec.add("6");
        vec.add("7");
        vec.add("8");
        vec.add("9");

        // Prints vector element before Shuffling
        System.out.println("Original Vector : " + vec);

        // The shuffle method of the Collections class
        Collections.shuffle(vec);

        // Prints vector element after Shuffling and
        // each time executed the result can be different
        System.out.println("After shuffling : " + vec);
    }
}
```

**输出:**

```
Original Vector : [5, 6, 7, 8, 9] 
After shuffling, Vector : [8, 9, 5, 6, 7]
```

使用随机函数对向量进行洗牌，这将成为随机性的来源。

**语法:**

```
Collections.shuffle(Vector, Random random)
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to shuffle Vector Elements

// Importing java libraries
import java.util.*;
import java.util.Vector;
import java.util.Collections;

public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Create a Vector object
        Vector<String> vec = new Vector<String>();

        // Add elements to Vector (Random)
        vec.add("geeksforgeeks");
        vec.add("course");
        vec.add("practice");
        vec.add("archive");
        vec.add("interview");

        // Prints vector element before Shuffling
        System.out.println("Original Vector : " + vec);

        // The Random Function
        Collections.shuffle(vec, new Random());
        System.out.println(
            "\nShuffled Vector with Random() : \n" + vec);

        // Random(3) to shuffle given vector
        Collections.shuffle(vec, new Random(3));
        System.out.println(
            "\nShuffled Vector with Random(3) : \n" + vec);

        // Random(3) to shuffle given list
        Collections.shuffle(vec, new Random(5));
        System.out.println(
            "\nShuffled Vector with Random(5) : \n" + vec);
    }
}
```

**输出:**

```
Original Vector : [geeksforgeeks, course, practice, archive, interview]

Shuffled Vector with Random() : 
[interview, practice, geeksforgeeks, archive, course]

Shuffled Vector with Random(3) : 
[archive, practice, interview, geeksforgeeks, course]

Shuffled Vector with Random(5) : 
[geeksforgeeks, practice, course, archive, interview]
```