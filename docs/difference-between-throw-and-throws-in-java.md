# Java 中投掷和抛投的区别

> 原文:[https://www . geesforgeks . org/Java 中抛出和抛出的区别/](https://www.geeksforgeeks.org/difference-between-throw-and-throws-in-java/)

**先决条件:** [投掷和爪哇投掷](https://www.geeksforgeeks.org/throw-throws-java/)

throw 和 throw 是 Java 中异常处理的概念，throw 关键字显式地从方法或代码块中抛出异常，而 throw 关键字用在方法的签名中。

**Java 中的抛出和抛出的区别是:**

<figure class="table">

| 

南号码

 | 

关键的区别

 | 

扔

 | 

投

 |
| --- | --- | --- | --- |
| 1. | 使用点 | 函数内部使用了 **throw** 关键字。当需要从逻辑上引发异常时，使用它。 | 函数签名中使用了**抛出**关键字。当函数有一些可能导致异常的语句时，使用它。 |
| 2. | 抛出异常 | **throw** 关键字用于显式抛出异常。它一次只能抛出一个异常。 | **抛出**关键字可以用来声明多个异常，用逗号分隔。无论发生哪种异常，如果与声明的异常匹配，就会自动抛出。 |
| 3. | 句法 | **throw** 关键字的语法包括要抛出的异常的实例。语法正确的 throw 关键字后面是实例变量。 | **抛出**关键字的语法包括要抛出的异常的类名。语法方面抛出关键字后是异常类名。 |
| 4. | 异常的传播 | **抛出**关键字不能传播被检查的异常。它仅用于传播未使用 throws 关键字检查的未检查异常。 | **抛出**关键字仅用于传播选中的异常。 |

</figure>

### 例子

**1。爪哇扔**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the working 
// of throw keyword in exception handling

public class GFG {
    public static void main(String[] args)
    {
        // Use of unchecked Exception
        try {
            // double x=3/0;
            throw new ArithmeticException();
        }
        catch (ArithmeticException e) {
            e.printStackTrace();
        }
    }
}
```

**输出:**

```
java.lang.ArithmeticException
    at GFG.main(GFG.java:10)
```

**2。Java 抛出**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate the working
// of throws keyword in exception handling
import java.io.*;
import java.util.*;

public class GFG {

    public static void writeToFile() throws Exception
    {
        BufferedWriter bw = new BufferedWriter(
            new FileWriter("myFile.txt"));
        bw.write("Test");
        bw.close();
    }

    public static void main(String[] args) throws Exception
    {
        try {
            writeToFile();
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```

**输出:**

```
java.security.AccessControlException: access denied ("java.io.FilePermission" "myFile.txt" "write")
  at GFG.writeToFile(GFG.java:10)
```