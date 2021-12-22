# 将长字符串转换为字符串的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-convert-long-to-string/](https://www.geeksforgeeks.org/java-program-to-convert-long-to-string/)

当我们必须在图形用户界面应用程序中显示一个长数字时，通常需要将长类型转换为字符串类型，因为所有内容都以字符串形式显示。

给定一个长数字，任务是在 Java 中将它转换成字符串。

**示例:**

```
Input:Long = 20L
Output:"20"

Input:Long = 999999999999L
Output:"999999999999"
```

### A.使用+运算符

为了将任何数据类型转换为字符串类型，我们可以简单地添加由双引号("")指示的/+空字符串。

**语法:**

```
String str = l+" ";
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert Long to String 
// using + operator

public class GFG { 

    // main method 
    public static void main(String args[]) 
    { 

        // create a Long 
        Long varLong = 999999999999L; 

        // convert into String
        String str = varLong+" ";

        // printing the type of str to
        // show that long has been converted to string
        System.out.println("Converted type : "+str.getClass().getName());

        // print Long as String 
        System.out.println(str); 
    } 
}
```

**Output**

```
Converted type : java.lang.String
999999999999
```

### B.使用[字符串. valueOf()](https://www.geeksforgeeks.org/data-conversion-using-valueof-method-java/)

**valueOf()** 方法将数据从其内部形式转换为人类可读的形式。它是一个静态方法，在一个字符串中重载了所有的 Java 内置类型，这样每个类型都可以正确地转换成一个字符串。
当需要其他类型数据的字符串表示时调用它，例如在串联操作期间。您可以使用任何数据类型调用此方法，并获得合理的字符串表示形式。

**语法:**

```
String str = String.valueOf(varLong);
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert Long to String
// using valueOf() Method

public class GFG {

    // main method
    public static void main(String args[])
    {

        // create a Long
        Long varLong = 999999999999L;

        // convert into String
        String str = String.valueOf(varLong);

        // printing the type of str to
        // show that long has been converted to string
        System.out.println("Converted type : "
                           + str.getClass().getName());

        // print Long as String
        System.out.println(str);
    }
}
```

**Output**

```
Converted type : java.lang.String
999999999999
```

### C.使用龙。 [toString()](https://www.geeksforgeeks.org/object-tostring-method-in-java/)

对象类包含 toString()方法。我们可以使用 toString()方法来获取对象的字符串表示形式。每当我们试图打印对象引用时，就会在内部调用 toString()方法。如果我们没有在您的类中定义 toString()方法，那么将调用 Object 类 toString()方法，否则将调用我们实现的/overrided toString()方法。

**语法:**

```
String str = Long.toString(varLong);
```

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to convert Long to String 
// using toString() method

public class GFG { 

    // main method 
    public static void main(String args[]) 
    { 

        // create a Long 
        Long varLong = 999999999999L; 

        // convert into String
        String str = Long.toString(varLong); 

        // printing the type of str to
        // show that long has been converted to string
        System.out.println("Converted type : "
                           + str.getClass().getName());

        // print Long as String 
        System.out.println(str); 
    } 
}
```

**Output**

```
Converted type : java.lang.String
999999999999
```