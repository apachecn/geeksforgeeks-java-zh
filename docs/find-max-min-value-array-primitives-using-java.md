# 使用 Java 在一组原语中找到最大值或最小值

> 原文:[https://www . geesforgeks . org/find-max-min-value-array-primitive-using-Java/](https://www.geeksforgeeks.org/find-max-min-value-array-primitives-using-java/)

作为一个整体，Java 是一种通常需要大量编码来执行特定任务的语言。因此，拥有几种实用程序的简写可能是有益的。本文使用“ **aslist()** ”解释了一个在数组中寻找最大和最小元素的实用程序。aslist()类型从传入其参数的数组中强制转换列表。该函数在“ **Java.utils.Arrays** 中定义。
要从数组中获取最小值或最大值，我们可以使用 **Collections.min()** 和 **Collections.max()** 方法。
但是由于这个方法需要列表类型的数据，我们需要先使用上面解释的“ **aslist()** ”函数将数组转换为列表。

**注意:**“您正在传递给 Arrays.asList()的数组必须具有 Integer 或您想要使用的任何类的返回类型”，因为 Collections.sort()接受 ArrayList **对象**作为参数。

**注意:**如果在声明数组时使用类型 int，您将最终看到以下错误:“没有为 min 找到合适的方法(List < int[] >)”

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to demonstrate how to
// extract minimum and maximum number
// in 1 line.
import java.util.Arrays;
import java.util.Collections;

public class MinNMax {
    public static void main(String[] args)
    {

        // Initializing array of integers
        Integer[] num = { 2, 4, 7, 5, 9 };

        // using Collections.min() to
        // find minimum element
        // using only 1 line.
        int min = Collections.min(Arrays.asList(num));

        // using Collections.max()
        // to find maximum element
        // using only 1 line.
        int max = Collections.max(Arrays.asList(num));

        // printing minimum and maximum numbers
        System.out.println("Minimum number of array is : "
                           + min);
        System.out.println("Maximum number of array is : "
                           + max);
    }
}
```

**Output**

```
Minimum number of array is : 2
Maximum number of array is : 9

```

本文由 **Astha Tyagi** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。