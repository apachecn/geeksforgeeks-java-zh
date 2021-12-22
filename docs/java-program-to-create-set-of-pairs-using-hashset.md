# 使用 HashSet 创建一组对的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-create-set-of-pairs-use-hashset/](https://www.geeksforgeeks.org/java-program-to-create-set-of-pairs-using-hashset/)

**问题陈述:**我们需要在所有给定的对中找到并打印唯一的对。

一般来说，如果我们必须在所有给定的数字中找到唯一的数字，那么我们就把所有的数字放在 HashSet 中并打印出来。让我们考虑一个示例来更好地解释问题陈述。假设我们有三对，它们是(3，5)，(4，5)，(3，5)。现在，如果我们把它放在集合中，那么输出将是。

```
Output: (3, 5), (4, 5), (3, 5)
```

> **注:**但是在 Pair 的情况下，我们不能只写如下所示，但是如果我们试图将 **Pair** 放在一个集合中，那么它就给了我们用于说明的问题。

```
HashSet<Pair> set = new HashSet<>();
```

从示例中，我们可以清楚地看到重复对仍然存在。这是因为对于集合来说，**对**是同一类型的对象，无法区分。所以为了克服这个问题，我们可以把**对**做成一串索引和值，以字符串的形式存储在 Set 中，然后打印出来，就可以得到所有唯一的对了。

**示例**

## Java

```
// Java Program to Create Set of Pairs
// using HashSet

// Importing required classes
import java.io.*;
import java.util.HashSet;

// Class 1
// Helper class for creating pairs
class Pair {

    // Pair attributes
    public int index;
    public int value;

    // Constructor to initialize pair
    public Pair(int index, int value)
    {
        // This keyword refers to current instance
        this.index = index;
        this.value = value;
    }
}

// Class 2
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Initializing an array of Pair
        // Custom input elements
        Pair arr[] = new Pair[4];
        arr[0] = new Pair(2, 3);
        arr[1] = new Pair(3, 4);
        arr[2] = new Pair(5, 10);
        arr[3] = new Pair(3, 4);

        // Creating a hashSet by
        // declaring object of string type
        HashSet<String> set = new HashSet<>();

        // Adding pair in set in form of string
        for (int i = 0; i < 4; i++) {
            set.add(arr[i].index + ", " + arr[i].value);
        }

        // Lastly iterating using for each loop annd
        // printing the elements pairs
        for (String e : set)
            System.out.println("(" + e + ")");
    }
}
```

**输出**

```
(5, 10)
(2, 3)
(3, 4)
```

输出解释:

因此，从代码和输出中，您可以清楚地看到重复的对被删除，我们可以在不覆盖 [*hashCode()方法*](https://www.geeksforgeeks.org/equals-hashcode-methods-java/) 和 [*等于()方法*](https://www.geeksforgeeks.org/compare-two-strings-in-java/) 的情况下获得所有唯一的对。