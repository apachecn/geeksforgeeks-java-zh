# 比较 Java 中的流和循环

> 原文:[https://www . geesforgeks . org/comparison-streams-to-loops-in-Java/](https://www.geeksforgeeks.org/comparing-streams-to-loops-in-java/)

流是聚合操作(filter()、map()、forEach()和 collect())的有序管道，这些操作处理(概念上无界的)元素序列。流管道由一个源，后跟零个或多个中间操作组成；和终端操作。聚合操作执行一个功能。理想情况下，函数在流中的输出仅取决于其输入参数。一个流没有非瞬态阶段。每个流的工作原理基本相同，即:

*   从数据源开始。
*   通过中间操作管道处理数据。
*   以终端操作结束。

默认情况下，流中的每个聚合操作都按顺序运行其函数，即在调用方的控制线程中一个接一个地运行。可以从文件的集合、列表、集合、整数、长整型、双精度型、数组、行创建流。

流操作要么是中间的，要么是终端的。过滤、映射或排序等中间操作返回一个流，因此我们可以链接多个中间操作。forEach、collect 或 reduce 等终端操作要么无效，要么返回非流结果。流带来了 Java 中的函数式编程，从 Java 8 开始支持。Java 8 流是 PQSA1 管道和过滤器模式的实现。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Compare Streams to Loops

// Importing required libraries
import java.io.IOException;
import java.lang.String;
import java.nio.file.*;
import java.util.*;
import java.util.Arrays;
import java.util.List;
import java.util.stream.*;

// Main class
// JavaStreams
class GFG {

    // Main driver method
    public static void main(String[] args)
        throws IOException
    {

        // 1\. Integer Stream
        System.out.println("Integer Stream : ");
        IntStream.range(1, 10).forEach(System.out::print);

        // New line
        System.out.println();

        // 2\. Integer Stream with skip
        System.out.println("Integer Stream with skip : ");
        IntStream.range(1, 10).skip(5).forEach(
            x -> System.out.println(x));

        // New line
        System.out.println();

        // 3\. Integer Stream with sum
        System.out.println("Integer Stream with sum : ");
        System.out.println(IntStream.range(1, 5).sum());

        // New line
        System.out.println();

        // 4\. Stream.of, sorted and findFirst
        System.out.println(
            "Stream.of, sorted and findFirst : ");
        Stream.of("Java ", "Scala ", "Ruby ")
            .sorted()
            .findFirst()
            .ifPresent(System.out::println);

        // New line
        System.out.println();

        // 5\. Stream from Array, sort, filter and print
        String[] names = { "AI",        "Matlab",
                           "Scikit",    "TensorFlow",
                           "OpenCV",    "DeepLearning",
                           "NLP",       "NeuralNetworks",
                           "Regression" };
        System.out.println(
            "Stream from Array, sort, filter and print : ");
        Arrays
            .stream(names) // same as Stream.of(names)
            .filter(x -> x.startsWith("S"))
            .sorted()
            .forEach(System.out::println);

        // New line
        System.out.println();

        // 6\. average of squares of an int array
        System.out.println(
            "Average of squares of an int array : ");
        Arrays.stream(new int[] { 2, 4, 6, 8, 10 })
            .map(x -> x * x)
            .average()
            .ifPresent(System.out::println);

        // New line
        System.out.println();

        // 7\. Stream from List, filter and print

        // Display message only
        System.out.println(
            "Stream from List, filter and print : ");

        List<String> people = Arrays.asList(
            "AI", "Matlab", "Scikit", "TensorFlow",
            "OpenCV", "DeepLearning", "NLP",
            "NeuralNetworks");
        people.stream()
            .map(String::toLowerCase)
            .filter(x -> x.startsWith("a"))
            .forEach(System.out::println);

        // New line
        System.out.println();

        // 8\. Reduction - sum

        // Display message only
        System.out.println("Reduction - sum : ");

        double total
            = Stream.of(7.3, 1.5, 4.8)
                  .reduce(0.0,
                          (Double a, Double b) -> a + b);

        // Print and display
        System.out.println("Total = " + total);

        System.out.println();

        // 9\. Reduction - summary statistics
        System.out.println(
            "Reduction - summary statistics : ");
        IntSummaryStatistics summary
            = IntStream.of(7, 2, 19, 88, 73, 4, 10)
                  .summaryStatistics();

        // Print and display
        System.out.println(summary);

        System.out.println();
    }
}
```

**Output**

```
Integer Stream : 
123456789
Integer Stream with skip : 
6
7
8
9

Integer Stream with sum : 
10

Stream.of, sorted and findFirst : 
Java 

Stream from Array, sort, filter and print : 
Scikit

Average of squares of an int array : 
44.0

Stream from List, filter and print : 
ai

Reduction - sum : 
Total = 13.600000000000001

Reduction - summary statistics : 
IntSummaryStatistics{count=7, sum=203, min=2, average=29.000000, max=88}
```

现在，讨论循环以便找出结论性差异。循环是 Java 中的一个特性，它有助于执行一组指令，直到控制布尔表达式的结果为假。提供不同类型的循环来满足任何编程需求。每个循环都有自己的目的和合适的用例。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Comparing Streams to Loops

// Importing utility packages
import java.util.*;

// Class 1
// helper class
class ProgrammingLanguage {

    // Member variables of this class
    int rank;
    String name;
    int value;

    // Member method of this class
    public ProgrammingLanguage(int rank, String name,
                               int value)
    {

        // this keyword is used to reger current object
        // itself
        this.rank = rank;
        this.name = name;
        this.value = value;
    }
}

// Class 2
// JavaStreamExample
public class GFG {

    // MAin driver method
    public static void main(String[] args)
    {

        // Creating an object of List class
        // Declaring object of user defined type (above
        // class)
        List<ProgrammingLanguage> programmingLanguage
            = new ArrayList<ProgrammingLanguage>();

        // Adding elements to the object of this class
        // Custom input entries
        programmingLanguage.add(
            new ProgrammingLanguage(1, "Java", 7000));
        programmingLanguage.add(
            new ProgrammingLanguage(2, "Rust", 2000));
        programmingLanguage.add(
            new ProgrammingLanguage(3, "Ruby", 1500));
        programmingLanguage.add(
            new ProgrammingLanguage(4, "Scala", 2500));
        programmingLanguage.add(
            new ProgrammingLanguage(5, "Groovy", 4000));

        // Creating object of List class of integer type
        List<Integer> languageValueList
            = new ArrayList<Integer>();

        // For each loops for iteration
        for (ProgrammingLanguage language :
             programmingLanguage) {

            // Filtering data of List
            if (language.value < 3000) {

                // Adding price to above elements
                languageValueList.add(language.value);
            }
        }

        // Print and display al elements inside the object
        System.out.println(languageValueList);
    }
}
```

**Output**

```
[2000, 1500, 2500]
```

> 到目前为止，我们已经理解了这两个概念，并认识到它们并不密切相关，根据使用的场合，一个概念比另一个概念更有优势。因此，通过举例说明以下优点来结束本文:

**溪流的优势**

*   流是一种更具声明性的风格。或者更有表现力的风格。
*   流与函数有很强的相似性。Java 8 引入了 lambdas 和函数接口，这打开了一个强大技术的工具箱。流提供了将函数应用于对象序列的最方便、最自然的方式。
*   溪流鼓励较少的可变性。这在某种程度上与函数式编程有关，即我们使用流编写的程序往往是不修改对象的程序。
*   流鼓励更松散的耦合。我们的流处理代码不需要知道流的来源或者它最终的终止方法。
*   流可以简洁地表达相当复杂的行为。

**循环的优势**

*   **性能**:在堆和 CPU 使用方面，通过数组的 for 循环都非常轻量级。如果原始速度和内存节约是优先考虑的，那么使用流就更糟了。
*   **熟悉度**:这个世界充满了经验丰富的程序程序员，来自很多语言背景，对于他们来说循环是熟悉的，流是新奇的。在某些环境中，您希望编写这种人熟悉的代码。
*   **认知开销:**由于它的声明性，以及从下面发生的事情中增加的抽象性，你可能需要建立一个新的关于代码如何与执行相关的心智模型。实际上，您只需要在事情出错时，或者需要深入分析性能或细微的 bug 时，才需要这样做。当它“刚刚工作”时，它就刚刚工作。
*   **调试器**正在改进，但即使是现在，当我们在调试器中单步执行流代码时，它可能比等效循环更难，因为简单循环非常接近传统调试器使用的变量和代码位置。

**结论:**

如果你有一个小清单；如果你有一个很大的列表，那么 for 循环会表现得更好；并行流会表现得更好。因为并行流有相当多的开销，所以不建议使用这些，除非您确定值得开销。