# 对于 Java 中的每个循环

> 原文:[https://www.geeksforgeeks.org/for-each-loop-in-java/](https://www.geeksforgeeks.org/for-each-loop-in-java/)

先决条件:[Java 中的决策制定](https://www.geeksforgeeks.org/decision-making-javaif-else-switch-break-continue-jump/)
For-每一个都是另一种数组遍历技术，如 Java5 中引入的 For 循环、while 循环、do-while 循环。

*   它以的关键字**开始，就像普通的 for 循环一样。**
*   您不是声明和初始化循环计数器变量，而是声明一个与数组的基类型相同的变量，后跟一个冒号，再跟一个数组名。
*   在循环体中，可以使用创建的循环变量，而不是使用索引数组元素。

*   它通常用于迭代数组或集合类(如数组列表)

**语法:**

```java
for (type var : array) 
{ 
    statements using var;
}
```

**相当于:**

```java
for (int i=0; i<arr.length; i++) 
{ 
    type var = arr[i];
    statements using var;
}
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to illustrate
// for-each loop
class For_Each    
{
    public static void main(String[] arg)
    {
        {
            int[] marks = { 125, 132, 95, 116, 110 };

            int highest_marks = maximum(marks);
            System.out.println("The highest score is " + highest_marks);
        }
    }
    public static int maximum(int[] numbers)
    {
        int maxSoFar = numbers[0];

        // for each loop
        for (int num : numbers)
        {
            if (num > maxSoFar)
            {
                maxSoFar = num;
            }
        }
    return maxSoFar;
    }
}
```

输出:

```java
The highest score is 132
```

**每个循环的限制**
决策

1.  for-当你想修改数组 :
    时，每个循环都**不合适**

```java
for (int num : marks) 
{
    // only changes num, not the array element
    num = num*2; 
}
```

2.对于每个循环**，不要跟踪索引**。因此，我们无法使用 For-Each 循环
获得数组索引

```java
for (int num : numbers) 
{ 
    if (num == target) 
    {
        return ???;   // do not know the index of num
    }
}
```

3.for-每个**仅在单个步骤中向前迭代数组**

```java
// cannot be converted to a for-each loop
for (int i=numbers.length-1; i>0; i--) 
{
      System.out.println(numbers[i]);
}
```

4.for-每个**不能同时处理两个决策语句**

```java
// cannot be easily converted to a for-each loop 
for (int i=0; i<numbers.length; i++) 
{
    if (numbers[i] == arr[i]) 
    { ...
    } 
}
```

5.for-每一个都有一些简单迭代的**性能开销**:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
/*package whatever //do not write package name here */

import java.io.*;
import java.util.*;

class GFG {
    public static void main (String[] args) {
        List<Integer> list = new ArrayList<>();
        long startTime;
        long endTime;
        for (int i = 0; i < 1000000; i++) {
            list.add(i);
        }
        // Type 1
        startTime = Calendar.getInstance().getTimeInMillis();
        for (int i : list) {
            int a = i;
        }
        endTime = Calendar.getInstance().getTimeInMillis();
        System.out.println("For each loop :: " + (endTime - startTime) + " ms");

        // Type 2
        startTime = Calendar.getInstance().getTimeInMillis();
        for (int j = 0; j < list.size(); j++) {
            int a = list.get(j);
        }
        endTime = Calendar.getInstance().getTimeInMillis();
        System.out.println("Using collection.size() :: " + (endTime - startTime) + " ms");

        // Type 3
        startTime = Calendar.getInstance().getTimeInMillis();
        int size = list.size();
        for (int j = 0; j < size; j++) {
            int a = list.get(j);
        }
        endTime = Calendar.getInstance().getTimeInMillis();
        System.out.println("By calculating collection.size() first :: " + (endTime - startTime) + " ms");

        // Type 4
        startTime = Calendar.getInstance().getTimeInMillis();
        for(int j = list.size()-1; j >= 0; j--) {
            int a = list.get(j);
        }
        endTime = Calendar.getInstance().getTimeInMillis();
        System.out.println("Using [int j = list.size(); j > size ; j--] :: " + (endTime - startTime) + " ms");
    }
}

// This code is contributed by Ayush Choudhary @gfg(code_ayush)
```

？list = plqm7 alhxfysf5 ereha1 bxgibg 7 uqma 4 _
**相关文章:**
[For-每个在 c++ vs Java](https://www.geeksforgeeks.org/g-fact-40-foreach-in-c-and-java/)
T7】迭代器 vs-每个在 Java
本文由 **Abhishek 维尔马**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。