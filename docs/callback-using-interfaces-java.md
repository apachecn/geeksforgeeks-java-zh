# 使用 Java 中的接口进行回调

> 原文:[https://www . geesforgeks . org/callback-use-interfaces-Java/](https://www.geeksforgeeks.org/callback-using-interfaces-java/)

**C/c++中的回调:**从另一个函数调用一个函数的机制称为“回调”。在像 C 和 C++这样的语言中，函数的内存地址被表示为“函数指针”。因此，回调是通过将函数 1()的指针传递给函数 2()来实现的。
**Java 中的回调:**但是回调函数的概念在 Java 中并不存在，因为 Java 没有指针的概念。然而，在某些情况下，人们可以谈论回调对象或回调接口。**接口不是传递函数的内存地址，而是传递引用函数位置的接口。**

**例**

让我们举一个例子来理解回调可以在哪里使用。假设一个程序员想设计一个计算一个州总税收的税收计算器。假设只有两种税，中央税和州税。中央税收是常见的，而州税因州而异。总税收是两者的总和。这里，像 stateTax()这样的单独方法为每个州实现，并从另一个方法 calculateTax()调用该方法，如下所示:

```
static void calculateTax(address of stateTax() function)
{
    ct = 1000.0
    st = calculate state tax depending on the address
    total tax = ct+st;
}
```

在前面的代码中，stateTax()的地址被传递给 calculateTax()。calculateTax()方法将使用该地址调用特定州的 stateTax()方法，并计算州税“st”。
由于 stateTax()方法的代码从一个状态变为另一个状态，不如在一个接口中声明为抽象方法，如:

```
interface STax
{
     double stateTax();
}
```

以下是旁遮普邦州税()的执行情况:

```
class Punjab implements STax{
    public double stateTax(){
    return 3000.0;
     }
}
```

以下是惠普状态的 stateTax()的实现:

```
class HP implements STax
{
    public double stateTax()
    {
        return 1000.0;
    }
}
```

现在，calculateTax()方法可以设计为:

```
static void calculateTax(STax t)
{
    // calculate central tax
    double ct = 2000.0;

    // calculate state tax
    double st = t.stateTax();
    double totaltax = st + ct;

    // display total tax
    System.out.println(“Total tax  =”+totaltax);
}
```

这里，观察 calculateTax()方法中的参数“STax t”。“t”是“STax”接口的引用，该接口作为参数传递给方法。使用此引用，调用 stateTax()方法，如下所示:

```
double st = t.stateTax();
```

这里，如果“t”指的是旁遮普类的 stateTax()方法，那么调用该方法并计算其税收。同样，对于惠普级。这样，通过将接口引用传递给 calculateTax()方法，就可以调用任何状态的 stateTax()方法。这叫**回调机制。**
通过传递引用一个方法的接口引用，可以从另一个方法调用和使用该方法。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate callback mechanism
// using interface is Java

// Create interface
import java.util.Scanner;
interface STax {
    double stateTax();
}

// Implementation class of Punjab state tax
class Punjab implements STax {
    public double stateTax()
    {
        return 3000.0;
    }
}

// Implementation class of Himachal Pardesh state tax
class HP implements STax {
    public double stateTax()
    {
        return 1000.0;
    }
}

class TAX {
    public static void main(String[] args)
throws ClassNotFoundException, IllegalAccessException, InstantiationException
    {
        Scanner sc = new Scanner(System.in);
        System.out.println("Enter the state name");
        String state = sc.next(); // name of the state

        // The state name is then stored in an object c
        Class c = Class.forName(state);

        // Create the new object of the class whose name is in  c
        // Stax interface reference is now referencing that new object
        STax ref = (STax)c.newInstance();

        /*Call the method to calculate total tax
        and pass interface reference - this is callback .
        Here, ref may refer to stateTax() of Punjab or HP classes
        depending on the class for which the object is created
        in the previous step
         */

        calculateTax(ref);
    }
    static void calculateTax(STax t)
    {
        // calculate central tax
        double ct = 2000.0;

        // calculate state tax
        double st = t.stateTax();
        double totaltax = st + ct;

        // display total tax
        System.out.println("Total tax =" + totaltax);
    }
}
```

**输出:**

```
Enter the state name
Punjab
Total tax = 5000.0
```

参考文献:
[如何在 Java 中实现回调函数？](http://www.xyzws.com/javafaq/how-to-implement-callback-functions-in-java/157)
[核心 Java:集成方法](http://www.amazon.in/Core-Java-Integrated-Nageswara-Rao/dp/8177228366)