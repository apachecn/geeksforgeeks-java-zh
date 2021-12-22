# 如何用 Java 创建包？

> 原文:[https://www . geesforgeks . org/如何创建 java 包/](https://www.geeksforgeeks.org/how-to-create-a-package-in-java/)

Java 中的 [Package](https://www.geeksforgeeks.org/packages-in-java/) 是封装一组类、子包和接口的机制。我们所需要做的就是将相关的类放入包中。之后，我们可以简单地从现有的包中编写一个导入类，并在我们的程序中使用它。包是一组相关类的容器，其中一些类是可访问的，被公开，而另一些被保留用于内部目的。我们可以在程序中根据需要多次重用包中的现有类。包名和目录结构密切相关

**方式:**java 中有两种类型的包:

1.  User-defined package (create your own package)
2.  Built-in packages are packages from Java application programming interface and Java API, such as **swing, util, net, io, AWT, lang, javax** , etc.

在本文中，我们将看到如何用 Java 创建一个包？。包是一组相似类型的类、接口和子包。我们使用包是为了避免名称冲突。

**语法:**导入包

```java
import package.name.*;
```

**示例:**导入包

T5】Java

```java
// Java Program to Import a package

// Importing java utility package
import java.util.*;

// Main Class
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Scanner to take input from the user object
        Scanner myObj = new Scanner(System.in);
        String userName;

        // Display message
        // Enter Your Name And Press Enter
        System.out.println("Enter You Name");

        // Reading the integer age entered using
        // nextInt() method
        userName = myObj.nextLine();

        // Print and display
        System.out.println("Your Name IS : " + userName);
    }
}
```

**输出**

```java
Enter You Name
Your Name IS : 0
```

> 在上面的程序中，导入了‘Java . util’包，并为一个简单的程序运行。这些被称为[内置包](https://www.geeksforgeeks.org/packages-in-java/)。

现在，为了用 java 创建一个包，请按照下面描述的特定步骤操作:

1.  First, we should choose a name for the package to be created and included. The command is in the first line of java program source code.
2.  You can further include classes, interfaces, annotation types, etc. required in the package. For example, the following single statement creates a package name named " *first package"* .

**语法:**声明要创建的包的名称。package 语句只是定义定义的类属于哪个包。

```java
package FirstPackage ;
```

**实现:**要在包内创建类

1.  First, declare the package name as the first statement of our program.
2.  Then we can use a class as part of the package.

**例 1:**

## 爪哇

```java
// Name of package to be created
package FirstPackage;

// Class in which the above created package belong to
class Welcome {
    // main driver method
    public static void main(String[] args)
    {
        // Print statement for the successful
        // compilation and execution of the program
        System.out.println(
            "This Is The First Program Geeks For Geeks..");
    }
}
```