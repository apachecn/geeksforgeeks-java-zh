# Java 中的匿名数组

> 原文:[https://www.geeksforgeeks.org/anonymous-array-java/](https://www.geeksforgeeks.org/anonymous-array-java/)

爪哇 **的一个没有名字的[数组被称为**一个匿名数组**。它是一个数组，只用于即时创建和使用。使用匿名数组，我们可以传递带有用户值的数组，而不用引用变量。](https://www.geeksforgeeks.org/arrays-in-java/)**

**匿名数组的属性:**

*   We can create an array without a name. This type of nameless array is called anonymous array.
*   The main purpose of anonymous arrays is only for immediate use (only for one-time use).
*   Anonymous arrays are passed as parameters of the method.

> **注意:**对于匿名数组创建，不要在[]中提及大小。在{}中传递的值的数量将变成大小。

**语法:**

```java
new <data type>[]{<list of values with comma separator>};
```

**例:**

```java
// anonymous int array 
new int[] { 1, 2, 3, 4};  

// anonymous char array 
new char[] {'x', 'y', 'z'); 

// anonymous String array
new String[] {"Geeks", "for", "Geeks"}; 

// anonymous multidimensional array
new int[][] { {10, 20}, {30, 40, 50} };
```

### 实施:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate the
// concept of anonymous array

class Test {
    public static void main(String[] args)
    {
          // anonymous array
          sum(new int[]{ 1, 2, 3 });
    }

    public static void sum(int[] a)
    {
        int total = 0;

        // using for-each loop
        for (int i : a)
            total = total + i;

        System.out.println("The sum is: " + total);
    }
}
```

**Output**

```java
The sum is: 6
```

**说明:**在上面的例子中，只是为了调用 sum 方法，我们需要一个数组，但是实现 sum 方法之后，我们就不再使用这个数组了。因此对于这种一次性需求，匿名数组是最好的选择。根据我们的要求，我们可以稍后给匿名数组命名，这样它就不再是匿名的了。

本文由**比沙尔·库马尔·杜贝**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。