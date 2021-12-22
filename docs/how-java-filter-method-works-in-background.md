# 【Java filter()方法在后台是如何工作的？

> 原文:[https://www . geesforgeks . org/how-Java-filter-method-works-in-background/](https://www.geeksforgeeks.org/how-java-filter-method-works-in-background/)

**filter()方法**在函数编程中作为中间方法使用。谓词是一种无干扰的无状态谓词，应用于每个元素以确定是否应该包含它。

**语法:** filter()方法

```
filter(Predicate predicate)
```

**参数:**一个谓词

**返回类型:**由符合给定谓词的传递流的元素组成的流。

你有没有想过，当我们编写下面的示例时会发生什么，这个示例是一个 lambda 表达式，它的元素映射到一个“*元素% 2 = = 0*”*？*那么屏幕背后到底发生了什么，它实际上是如何工作的？这一切的魔力都是基于一个叫做**功能接口**的东西，因为功能接口只有一个抽象方法。因为默认方法有实现，所以它们不是抽象的。例如，谓词接口、消费者接口都是功能接口。

```
List.of(10,5,23,54).stream().filter(element -> element%2==0);
```

**实现:**考虑下面的程序，该程序使用 filter()方法消除奇数并返回可被 2 整除的数字流，即偶数。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to demonstrate Use of filter() Method

// Importing all. input output classes
import java.io.*;
// Importing List class from java.util package
import java.util.List;

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // 1\. Creating List of integers later on
        // 2\. converting List to a Stream in which
        // 3\. logic is to eliminate the odd numbers and
        // finally
        // 4\. Printing each element of stream returned by
        // filter() method
        List.of(12, 34, 67, 19, 32, 4)
            .stream()
            .filter(element -> element % 2 == 0)
            .forEach(
                element -> System.out.println(element));
    }
}
```

**Output**

```
12
34
32
4
```

**内部工作流程:**

*   当[12，34，67，19，32，4]的流传递给 filter 方法时，它使用提供的谓词(元素→元素%2==0)测试每个元素，并返回偶数[12，34，32，4]的流。
*   现在，屏幕后面发生了什么？代码片段“ ***元素→元素%2 == 0*** 是如何被发送到过滤方法的。
*   如果我们看一下 filter()方法的签名，可以看到它在参数中使用了一个谓词。

```
public abstract Stream<T> filter(Predicate<? super T> predicate)
```

*   所以当我们查看谓词的文档时，它有如下签名，上面写着@FunctionalInterface 注释

```
public interface Predicate<T>
```

*   谓词接口中的功能方法如下:

```
boolean Test(T t) ;
```

*   它返回一个复合谓词，表示这个谓词和另一个谓词的逻辑“与”。评估组合谓词时，如果此谓词为假，则不评估另一个谓词。
*   在谓词接口中，Test()是唯一没有编写任何默认实现的方法。那么现在，元素“*->元素%2 == 0* 是如何映射到谓词接口的实现的。
*   我们有一个方法 **test()** ，它接受一个接口**谓词**作为参数，那么我们只能将该接口实现的对象作为参数传递给该方法。

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Implementation of the Predicate interface

// Importing input output classes
import java.io.*;
// Importing classes from java.util package
import java.util.List;
import java.util.function.Predicate;

// Class 1
// helper class
// Implementation of Predicate interface
class EvenNumberPredicate implements Predicate<Integer> {

    // Implementing all unimplemented method of the
    // Predicate interface.
    // @Override
    public boolean test(Integer number)
    {

        // Returns true for Even and false for Odd
        return number % 2 == 0;
    }
}

// Class 2
// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // 1\. Creating List of integers then
        // 2\. Converting list to stream further
        // 3\. Passing the object of Predicate to the filter
        // method
        List.of(12, 34, 67, 19, 32, 4)
            .stream()
            .filter(new EvenNumberPredicate())
            .forEach(
                element -> System.out.println(element));
    }
}
```

**Output**

```
12
34
32
4
```

> **注意:**两个程序产生相同的输出。

当我们将***evennnumberpredicate()***的对象作为参数传递给 filter 方法时，它所做的是针对传递给它的流的每个元素，它将检查在*evennnumberpredicate()*的 overridden test()方法中提供的条件，如果 test()返回 true，它将元素包含到返回的流中，否则如果 test()方法返回 false，它将拒绝将元素包含到返回的流中。例如:对于元素 12， ***test()*** 方法返回 true，所以它包含在返回流中，而对于元素 67 test()返回 false，所以 67 不包含在返回流中。示例 2 展示了当我们向 filter()方法传递一些逻辑时发生的事情。这意味着，当我们向 filter()方法传递一些逻辑时，后台的 java 编译器会创建一个函数接口的实现。

> **注意:**像谓词一样的函数接口最重要的特征是它只有一个没有定义的方法，基本上我们在创建 Lambda 表达式时所做的就是为那个特定的方法提供实现(或逻辑代码)。

在这种情况下(即 filter())，我们是在对编译器说，在 Predicate 的情况下，它将唯一没有实现的方法 test()作为它的实现，并提供在 filter 方法中编写的逻辑。