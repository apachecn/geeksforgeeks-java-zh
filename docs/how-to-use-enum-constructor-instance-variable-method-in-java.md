# 如何在 Java 中使用枚举、构造函数、实例变量&方法？

> 原文:[https://www . geeksforgeeks . org/如何使用-枚举-构造函数-实例-变量-java 中的方法/](https://www.geeksforgeeks.org/how-to-use-enum-constructor-instance-variable-method-in-java/)

[枚举](https://www.geeksforgeeks.org/enum-in-java/)用于在编程语言中表示一组命名常数。当我们在编译时知道所有可能的值时，例如菜单上的选项、舍入模式、命令行标志等，就使用枚举。枚举类型中的常量集不必一直保持固定。在 Java 中，枚举是使用枚举数据类型来表示的。Java 枚举比 C/C++枚举更强大。在 Java 中，我们还可以向其中添加变量、方法和构造函数。枚举的主要目的是定义我们自己的数据类型(枚举数据类型)。

> **注意:**实例变量是非静态变量，在任何方法、构造函数或块之外的类中声明。

现在进入我们的问题描述，因为它是为了说明如何在 Java 中使用枚举构造函数、实例变量和方法。因此，对于这个解决方案，我们将看到下面的示例使用构造函数& totalPrice()方法初始化枚举，并显示枚举的值。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Illustrate Usage of Enum
// Constructor, Instance Variable & Method

// Importing required classes
import java.io.*;
import java.util.*;

// Enum
enum fruits {
    // Attributes associated to enum
    Apple(120),
    Kiwi(60),
    Banana(20),
    Orange(80);

    // internal data
    private int price;

    // Constructor
    fruits(int pr) { price = pr; }

    // Method
    int totalPrice() { return price; }
}

// Main class
class GFG {

    // main driver method
    public static void main(String[] args)
    {
        // Print statement
        System.out.println("Total price of fruits : ");

        // Iterating using enhanced for each loop
        for (fruits f : fruits.values())

            // Print anddispaly the cost and perkg cost of
            // fruits
            System.out.println(f + " costs "
                               + f.totalPrice()
                               + " rupees per kg.");
    }
}
```

**Output**

```java
Total price of fruits : 
Apple costs 120 rupees per kg.
Kiwi costs 60 rupees per kg.
Banana costs 20 rupees per kg.
Orange costs 80 rupees per kg.
```