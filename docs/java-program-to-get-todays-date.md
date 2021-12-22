# 获取今日日期的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-get-today-date/](https://www.geeksforgeeks.org/java-program-to-get-todays-date/)

Java 是最强大的编程语言，通过它我们可以执行许多任务，Java 是一种行业首选语言。所以它充满了大量的特征。在这里，我们将讨论 Java 最好的特性之一，即如何使用 Java 获取今天或当前的日期。

**方法:**

有两种方法可以获得今天的日期，如下所示:

1.  [使用 LocalDate 类的 now()方法](https://www.geeksforgeeks.org/localdate-now-method-in-java-with-examples/)
2.  使用 java.sql.Date()函数

让我们一个接一个地看一遍，以便对它们有一个公平的了解。

**方法 1:** 使用[现在()LocalDate 类的方法](https://www.geeksforgeeks.org/localdate-now-method-in-java-with-examples/)

*now()* *方法*的一个 LocalDate 类用来从默认时区的系统时钟中获取当前日期。此方法将根据系统时钟和默认时区返回本地日期，以获取当前日期。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Get Today's Date
// Using now() method of LocalDate class

// Importing required classes
import java.text.SimpleDateFormat;
import java.util.Date;

// Main class
// Day of Today
public class GFG {

    // Main Driver Method
    public static void main(String[] args) {

        // Printing Today's date by calling
        // java.time.LocalDate.now() function
        System.out.println(java.time.LocalDate.now());
    }
}
```

**Output**

```
2021-05-31

```

**方法二:**使用 java.sql.Date()函数

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Get Today's Date
// Using java.sql.Date() function

// Importing required classes
import java.text.SimpleDateFormat;
import java.util.Date;

// Main class
public class GFG {

    // Main Driver Method
    public static void main(String[] args)
    {

        // Printing Today's date by calling
        // java.sql.Date() function
        long millis = System.currentTimeMillis();
        java.sql.Date date = new java.sql.Date(millis);
        System.out.println(date);
    }
}
```

**Output**

```
2021-05-31

```