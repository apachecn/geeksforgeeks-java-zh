# Java 中的突变测试(使用混搭)

> 原文:[https://www.geeksforgeeks.org/mutation-testing-java/](https://www.geeksforgeeks.org/mutation-testing-java/)

变异测试是一种白盒测试技术，它改变代码的某些部分来揭示可能的错误。在很高的层次上，它是用一些已知或可能的错误或差异以小的方式重写源代码以消除源代码中的冗余的过程。突变测试的目标是评估测试的覆盖范围。Java 有很多变异测试工具。

1.  混乱
2.  凹陷
3.  Java(Java)
4.  小丑

<pstyle center="">**Jumble**

这篇文章讨论的是 Java 中的混乱突变测试工具。Jumble 是一个突变测试工具，它在**字节代码**级别改变 Java 代码。它运行一个单元测试用例，并应用特定的突变集。

*   **通过突变**:不影响最终输出的代码变化
*   **失败的突变**:改变最终输出的代码变化

**评分**:是传递的突变占总突变的百分比。它用于评估我们测试套件的有效性。
**安装**
下载 Eclipse IDE，安装 Jumble 到 Eclipse。

**Java 中的简单代码片段**

```java
int index = 0;
while(true)
{
   index++;
   if (index == 10) 
        break;
}

```

**JAVA 中的变异代码**

```java
int index = 0;
while (true)
{
   index++;
   if (index >= 10) 
        break;
}

```

**说明:**上面的突变代码将**通过 Jumble 测试**，因为==到>的变化=不影响代码的输出。当 index == 10 时，执行将停止，因为我们将值增加 1，而 index 从 0 开始，所以输出将保持不变。

**Jumble 示例** 下面写的代码已经在 Eclipse 中用 Jumble 插件测试过了。该代码检测到第一次出现重复，并将该值返回给调用函数。这个程序在很多方面都有缺陷，你可以试着弄清楚。

```java
// Java program to illustrate mutation Testing
// The code detects the first occurrence of a 
// duplicate and returns the value to the calling
// function
package testPackage;

import java.util.Arrays;
import java.util.List;
public class SampProg
{
    protected int repeatedNumber(final List a)
    {
        int len = a.size(),i,dup = -1;
        int[] arr = new int[len];
        for (i=0; i<len; i++)
        {
            arr[i] = a.get(i);
        }

        Arrays.sort(arr);
        try
        {
            for (i=1; i<len; i++)
            {
                if(arr[i] == arr[i-1])
                {
                    dup = arr[i];
                    break;
                }
            }
        }
        catch(Exception e)
        {
            System.out.println(e.getMessage());
        }
        return dup;
    }
}
```

写完程序后，我们用 Java 中的 [JUnit](http://junit.org/junit4/) 创建测试用例。下面给出了执行旧杂货分析时获得的输出:

```java
Mutating testPackage.SampProg
Tests: testPackage.SampProgTest
Mutation points = 11, unit test time limit 2.94s
M FAIL: (testPackage.SampProg.java:8): -1 -> 1
M FAIL: (testPackage.SampProg.java:10): 0 -> 1
.M FAIL: (testPackage.SampProg.java:10): negated conditional
M FAIL: (testPackage.SampProg.java:16): 1 -> 0
M FAIL: (testPackage.SampProg.java:18): 1 -> 0
M FAIL: (testPackage.SampProg.java:18): - -> +
M FAIL: (testPackage.SampProg.java:18): negated conditional
M FAIL: (testPackage.SampProg.java:16): += -> -=
M FAIL: (testPackage.SampProg.java:16): negated conditional
.
Jumbling took 7.595s
Score: 18%
```

**解释结果**

1.  在第一行的 M FAIL 中，输出-1 被更改为 1。在主程序中，如果没有重复，我们希望该值返回为-1。但是我们得到的值是 1。我们可以通过检查值突变来修复突变。
2.  接下来，我们可以在条件被否定的第 3、7、9 行看到“被否定的条件”。然而在这里，我们不能修复这个程序的错误。
3.  变异不能给出正确输出的其他情况是当操作符被改变为其他操作符时。在这个和许多算法代码中，与操作符变化相关的突变是无法修复的。然而，突变测试在一些突变中给出了关于测试用例薄弱或者源代码中有错误的简单想法。这个[链接](http://jumble.sourceforge.net/mutations.html)给出了由混杂执行的突变

本文由**益普西**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。</pstyle>