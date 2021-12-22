# Java–λ表达式变量捕捉示例

> 原文:[https://www . geesforgeks . org/Java-lambda-expression-variable-captureing-with-examples/](https://www.geeksforgeeks.org/java-lambda-expression-variable-capturing-with-examples/)

由 lambda 表达式的封闭范围定义的变量可以在 lambda 表达式中访问。例如，lambda 表达式可以使用由其封闭类定义的实例或静态变量。lambda 表达式还可以访问(显式和隐式)，这是指 lambda 表达式的封闭类的调用实例。因此，lambda 表达式可以获取或设置内部变量或静态变量的值，并调用由其封闭类定义的方法。

[Java 中的 Lambda 表达式使用](https://www.geeksforgeeks.org/lambda-expressions-java-8/)一个局部变量如上所述。

但是，当 lambda 表达式使用其封闭范围内的局部变量时，会产生一种特殊情况，称为变量捕获。在这种情况下，lambda 表达式可能只使用实际上是[最终](https://www.geeksforgeeks.org/final-keyword-java/)的局部变量。有效的最终变量是其值在首次赋值后不变的变量。没有必要显式地将这样的变量声明为 final，尽管这样做不会出错。

重要的是要理解封闭范围的局部变量不能被 lambda 表达式修改。这样做将实际上消除其最终地位，从而使其非法捕获。

有一些要点需要记住，如下所示:

1.  lambda 表达式中使用但未声明的任何局部变量、形式参数或异常参数必须声明为 final 或实际上是 final，否则在尝试使用时会出现编译时错误。
2.  在 lambda 主体中使用但未声明的任何局部变量必须在 lambda 主体之前明确赋值，否则会发生编译时错误。
3.  类似的变量使用规则也适用于内部类的主体。对有效最终变量的限制禁止了对动态变化的局部变量的访问，局部变量的捕获可能会引入并发问题。与最后的限制相比，它减轻了程序员的文书负担。
4.  对有效最终变量的限制包括标准循环变量，但不包括增强的循环变量，这些变量在循环的每次迭代中都被视为不同的。

以下程序说明了有效最终变量和可变局部变量之间的区别:

**例 1**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Illustrating Difference between
// Effectively final and Mutable Local Variables

// Importing reqiored classes
import java.io.*;
// An example of capturing a local variable from the
// enclosing scope

// Inrterface
interface MyFunction {

    // Method inside the interface
    int func(int n);
}

// Main class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Custom local variable that can be captured
        int number = 10;

        MyFunction myLambda = (n) ->
        {

            // This use of number is OK It does not modify
            // num
            int value = number + n;

            // However, the following is illegal because it
            // attempts to modify the value of number

            // number++;
            return value;
        };

        // The following line would also cause an error,
        // because it would remove the effectively final
        // status from num. number = 9;

        System.out.println("GFG!");
    }
}
```

**Output**

```
GFG!
```

输出解释:

如注释所示，数字实际上是最终的，因此可以在 myLambda 中使用。但是，如果要修改 number，无论是在 lambda 内部还是外部，number 都将失去其有效的最终状态。这将导致错误，程序将无法编译。

**例 2**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program Illustrating Difference between
// Effectively final and Mutable Local Variables

// Importing input output classes
import java.io.*;

// Interface
interface MyInterface {

    // Method inside the interface
    void myFunction();
}

// Main class
class GFG {

    // Custom initialization
    int data = 170;

    // Main driver method
    public static void main(String[] args)
    {

        // Creating object of this class
        // inside the main() method
        GFG gfg = new GFG();

        // Creating object of interface
        // inside the main() method
        MyInterface intFace = () ->
        {
            System.out.println("Data : " + gfg.data);
            gfg.data += 500;

            System.out.println("Data : " + gfg.data);
        };

        intFace.myFunction();
        gfg.data += 200;

        System.out.println("Data : " + gfg.data);
    }
}
```

**Output**

```
Data : 170
Data : 670
Data : 870
```

> **注意:**需要强调的是，lambda 表达式可以从其调用类中使用和修改实例变量。它只是不能使用其封闭范围的局部变量，除非该变量实际上是最终的。