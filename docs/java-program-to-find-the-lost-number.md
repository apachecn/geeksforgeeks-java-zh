# 寻找丢失号码的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序查找丢失的号码/](https://www.geeksforgeeks.org/java-program-to-find-the-lost-number/)

鲍勃是个小孩，刚学会数数。他坐在家里，开始玩他的许多玩具。他左手拿着一些***【n】***玩具号码，右手数着那些***【n】***玩具。突然他妈妈打电话给他，他把所有的号码混在一起就走了。当他回来时，他意识到他忘记了他正在数的数字。给定所有的玩具号码，帮助他找到 ***n*** 的值，如果在数组或 print -1 中存在的话。

**示例**

> **输入** : 5 7 4 3 2 6
> 
> **输出** : 5
> 
> **说明**:有 6 个玩具号码，其中一个是长度，所以我们打印 5 个。
> 
> **输入** : 10 14 11 15
> 
> **输出** : -1
> 
> **解释**:有 4 个玩具号码，但我们没有 3 作为数组中的值，因此我们打印-1。

**接近**

解决办法很简单。我们可以只取一个[字符串](https://www.geeksforgeeks.org/string-class-in-java/)中的输入，计算空格数，这将是数组的实际长度。

**算法**

> 1.  Enter as a string.
> 2.  Count the number of spaces in the string.
> 3.  If the number of spaces is equal to any element in the array, print the number; otherwise, print -1.
> 4.  To find out whether the element exists, we use the [string.indexof ()](https://www.geeksforgeeks.org/java-string-indexof/) method.

#### 它是如何工作的？

*   当我们把输入当作一个字符串时，字符串中的元素数等于空格数+1。
*   元素的实际数量等于字符串中的元素数量-1。

> 必需答案=空格数+1 -1 =空格数

一**实施:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to find the lost count

import java.util.*;
public class GFG {

    // find lost count
    public static void findLostCount(String s)
    {

        // counting the number of elements using the split
        // function -1
        int count = s.split(" ").length - 1;

        // if the value count is present then print count
        // else print -1
        if (s.indexOf(Integer.toString(count)) != -1)
            System.out.println("Number of elements "
                               + count);
        else
            System.out.println(-1);
    }

    public static void main(String args[])
    {
        Scanner in = new Scanner(System.in);

        // Taking input as string
        String s = "5 7 4 3 2 6";

        findLostCount(s);
    }
}
```

**Output**

```java
Number of elements 5
```