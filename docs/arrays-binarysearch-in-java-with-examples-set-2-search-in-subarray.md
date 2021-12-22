# Java 中的 Arrays.binarySearch()示例| Set 2(子数组中的搜索)

> 原文:[https://www . geesforgeks . org/arrays-binary search-in-Java-with-examples-set-2-search-in-subarray/](https://www.geeksforgeeks.org/arrays-binarysearch-in-java-with-examples-set-2-search-in-subarray/)

[arrays . binary search()| Set 1](https://www.geeksforgeeks.org/arrays-binarysearch-java-examples-set-1/)介绍了如何在 Java 中查找排序数组中的元素。这一集将涵盖“如何在给定范围内搜索数组中的键，只包括起始索引”。

**语法:**

> 公共静态 int binarySearch(data_type[] arr，int fromIndex，int toIndex，data_type 键)

**参数:**

> **arr**–要搜索的数组
> 
> **from index**–要搜索的第一个元素(含)的索引
> 
> **到索引**–要搜索的最后一个元素(不包括)的索引
> 
> **键**–要搜索的值

*   它是 java 中 **Arrays (java.util.Arrays)** 类定义的静态内置方法，返回在指定范围内找到的指定键的索引。
*   这里，**数据类型**可以是任何一种原始的**数据类型**:字节、字符、双精度、整数、浮点、短、长和对象。
*   上述函数使用二分搜索法算法在给定数据类型的指定数组范围内搜索指定键。
*   在进行此调用之前，必须对要搜索的指定关键字进行排序的范围(如通过 [Arrays.sort()](https://www.geeksforgeeks.org/arrays-sort-in-java-with-examples/) 方法)。否则，结果将是未定义的。如果指定的数组包含多个与指定键相同的值，则不能保证找到哪个值。

> **返回:**
> 在指定数组的指定范围内找到指定键的索引，否则(-(插入点)–1)。

插入点被定义为指定键的插入点:大于该键的范围内第一个元素的索引，如果该范围内的所有元素都小于指定键，则定义为索引。
注意:这保证了当且仅当找到密钥时返回值将为> = 0。

**示例:**

> 字节数组[] = {10，20，15，22，35}
> 
> key = 22，在指定数组的 2 到 4 范围内搜索。
> 
> 产出:3
> 
> charArr[] = {'g '，' p '，' q '，' c '，' i'}
> 
> key =要在指定数组的 1 到 4 范围内搜索的 p。
> 
> 产出:3
> 
> 愤怒吧
> 
> key = 3，在指定数组的 1 到 4 范围内搜索。
> 
> 产出:2
> 
> doubleArr[] = {10.2，1.51，2.2，3.5}
> 
> key = 1.5，在指定数组的 1 到 4 范围内搜索。
> 
> 输出:-2，因为它是 1.5 的插入点
> 
> floatArr[] = {10.2f，15.1f，2.2f，3.5f}
> 
> key = 35.0，在指定数组的 1 到 4 范围内搜索。
> 
> 输出:-5
> 
> shortArr[] = {10，20，15，22，35}
> 
> key = 5，在指定数组的 0 到 4 范围内搜索。
> 
> 输出:-1

**执行:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate working of  binarySearch()
// method for specified range in a sorted array.
import java.util.Arrays;

public class GFG {
    public static void main(String[] args)
    {
        byte byteArr[] = { 10, 20, 15, 22, 35 };
        char charArr[] = { 'g', 'p', 'q', 'c', 'i' };
        int intArr[] = { 1, 2, 3, 4, 5, 6 };
        double doubleArr[] = { 10.2, 15.1, 2.2, 3.5 };
        float floatArr[] = { 10.2f, 15.1f, 2.2f, 3.5f };
        short shortArr[] = { 10, 20, 15, 22, 35 };

        Arrays.sort(byteArr);
        Arrays.sort(charArr);
        Arrays.sort(intArr);
        Arrays.sort(doubleArr);
        Arrays.sort(floatArr);
        Arrays.sort(shortArr);

        byte byteKey = 22;
        char charKey = 'p';
        int intKey = 3;
        double doubleKey = 1.5;
        float floatKey = 35;
        short shortKey = 5;

        System.out.println(
            byteKey + " found at index = "
            + Arrays.binarySearch(byteArr, 2, 4, byteKey));
        System.out.println(
            charKey + " found at index = "
            + Arrays.binarySearch(charArr, 1, 4, charKey));
        System.out.println(
            intKey + " found at index = "
            + Arrays.binarySearch(intArr, 1, 4, intKey));
        System.out.println(doubleKey + " found at index = "
                           + Arrays.binarySearch(
                               doubleArr, 1, 4, doubleKey));
        System.out.println(floatKey + " found at index = "
                           + Arrays.binarySearch(
                               floatArr, 1, 4, floatKey));
        System.out.println(shortKey + " found at index = "
                           + Arrays.binarySearch(
                               shortArr, 0, 4, shortKey));
    }
}
```

**Output**

```
22 found at index = 3
p found at index = 3
3 found at index = 2
1.5 found at index = -2
35.0 found at index = -5
5 found at index = -1

```

**异常:**

1.  **IllegalArgumentException** :当起始索引(fromIndex)大于指定范围的结束索引(toIndex)时抛出。(指:从索引>到索引)
2.  **arrayinDexOutofBoundSexception**:如果一个或两个索引无效，抛出表示从索引< 0 或到索引> arr.length。

**要点:**

*   如果输入列表没有排序，结果是未定义的。
*   如果有重复，不能保证会找到哪一个。

**参考:**

[https://docs . Oracle . com/javase/7/docs/API/Java/util/Array . html # BinarySearch(int[]，%20int)](https://docs.oracle.com/javase/7/docs/api/java/util/Arrays.html#binarySearch(int[],%20int))

本文由 **Nitsdheerendra** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。