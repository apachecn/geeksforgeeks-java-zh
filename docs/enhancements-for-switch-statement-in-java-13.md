# Java 13 中开关语句的增强功能

> 原文:[https://www . geesforgeks . org/enhancements-for-switch-statement-in-Java-13/](https://www.geeksforgeeks.org/enhancements-for-switch-statement-in-java-13/)

Java 12 改进了传统的 switch 语句，使其更加有用。Java 13 进一步引入了新特性。在详细介绍新特性之前，让我们先来看看传统 Switch 语句面临的缺点。

### 传统交换机存在的问题

**1。** **因错过休息而违约失败**

默认的失败行为容易出错。我们用一个例子来理解。

```
switch (itemCode) {
    case 001 : 
        System.out.println("It's a laptop!");
        break;
    case 002 :
        System.out.println("It's a desktop!");
        break;
    case 003 :
        System.out.println("It's a mobile phone!");
        break;
    default :
        System.out.println("Unknown device!");
}

```

上面的代码通过匹配相应的案例并执行特定的代码块来工作。只要您提供必要的中断语句，它就能正常工作。

但是，如果我们忘记了任何必需的中断语句，会发生什么呢:

```
 switch (itemCode) {
    case 001 : 
        System.out.println("It's a laptop!");
        // missed out break here 
    case 002 :
        System.out.println("It's a desktop!");
        break;
}

```

这里，如果我们传递 001，第一个大小写匹配，代码块执行。但是由于错过休息，执行失败，继续执行 **002** 号案件。我们得到以下错误输出:

```
It's a laptop!
It's a desktop!

```

显然，这不是预期的输出。这是意外遗漏中断语句的结果。

**2。不支持每个案例多个值**

可能存在需要对多个案例值进行类似处理的情况。但是传统的转换是通过行为来跟随下跌。

```
case 001:
case 002:
case 003:
System.out.println("It's an electronic gadget!");

```

改进后的开关每种情况下接受多个值。

```
case 001, 002, 003 : 
        System.out.println("It's an electronic gadget!");

```

### 升级的交换机

对 switch 语句的增强是由 Java 12 引入的，然后由 Java 13 进一步修改。

让我们深入了解 Switch 语句的这个改进版本的重要特性。

**1。每种情况支持多个值**

由于每个案例指定了多个值，它简化了代码结构，并消除了使用失败的需要。

这些值需要用逗号分隔，分隔符应该跟在大小写块后面。

```
switch (itemCode) {
    case 001, 002, 003 : 
        System.out.println("It's an electronic gadget!");
        break;

    case 004, 005:
        System.out.println("It's a mechanical device!");
        break;
}

```

**2。** **收益率用来返回值**

引入了新的关键词**产量**。它只从开关分支返回值。

屈服后我们不需要休息，因为它会自动终止开关表达式。

```
int val = switch (code) {
    case "x", "y" :
        yield 1;
    case "z", "w" :
        yield 2;
}

```

**3。Switch 可以作为一个表达式**

开关现在可以用作表达式。这意味着**开关现在可以根据我们的输入返回值**。为了适应这种变化，开关语法略有变化。开关块需要用分号分隔。yield 关键字用于返回值。收益表不需要中断。

让我们看一下代码片段，以便更好地理解这些变化。

```
String text = switch (itemCode) {
    case 001 : 
        yield "It's a laptop!";
    case 002 :
        yield "It's a desktop!";        
    case 003 :
        yield "It's a mobile phone!";
    default :
        throw new IllegalArgumentException(itemCode + "is an unknown device!");
}

```

**4。必要返回值/异常**

开关表达式需要指定所有可能输入值的处理。我们要么提供所有可能的情况，要么指定默认情况。这意味着，不管输入值是什么，switch 表达式应该总是返回某个值或者显式抛出一个异常。

例如，如果将上述代码块更改为–

```
String text = switch (itemCode) {
    case 001 : 
        yield "It's a laptop!";
    case 002 :
        yield "It's a desktop!";        
    case 003 :
        yield "It's a mobile phone!";
    // default :
    //    throw new IllegalArgumentException(itemCode + "is an unknown device!");
}

```

这将导致一个错误，说开关表达式没有覆盖所有可能的值。

**5。** **用箭头切换**

为交换机引入了新的箭头 **⇾** 语法。它可以与**开关**一起用作表达和陈述。

如果一个精确的案例与左边的匹配，则执行⇾右边的语句。

在 **⇾的右侧**我们可以有以下任何一种–

*   Statement/expression
*   **Throw** statement
*   {} Blocked

这种语法的主要优点是我们不需要 break 语句来避免默认的失败。所以规则是，如果我们需要摔倒，用**格:**否则不用**格**t5】⇾。还要注意，对于所有案例分支，应该是**案例:**或**案例⇾** 。开关中不能有不同的情况，否则会导致错误。

```
switch (itemCode) {
    case 001 -> System.out.println("It's a laptop!");
    case 002 -> System.out.println("It's a desktop!");
    case 003,004 -> System.out.println("It's a mobile phone!");
}

```

正如我们在上面的代码中看到的，语法也可以用于每个案例的多个值。

**6。** **范围**

传统开关中声明的变量一直存在到开关语句结束。如果我们希望变量有一个用例级别的作用域，我们可以使用 Java 13 中增强开关引入的{}。

```
switch (errorCode) {
    case 101: {
        // This variable exists just in this {} block
        int num = 200;
        break;
    }
    case 300: {
        // This is ok, {} block has a separate scope
        int num = 300;
        break;
    }
}

```

**7。** **预览功能**

在深入研究了与增强交换机相关的特性之后，值得注意的一点是——增强交换机功能仅作为 Java 13 中的预览特性提供。这意味着默认情况下不会启用它。要使用它，我们需要显式启用它。

在编译时，向 javac 添加以下参数:

```
javac -- release 13 --enable-preview MyClass.java

```

在运行时，添加以下内容:

```
java --enable-preview MyClass

```

Java 13 中的增强交换机为传统交换机提供了许多令人印象深刻的特性。然而，它仍处于实验阶段，尚未用于生产。