# 如何解决 Java List 不支持操作异常？

> 原文:[https://www . geesforgeks . org/how-solution-Java-list-unsupportedoperationexception/](https://www.geeksforgeeks.org/how-to-solve-java-list-unsupportedoperationexception/)

UnsupportedOperationException 是我们在使用一些列表实现的应用编程接口时出现的常见异常之一。引发它是为了指示不支持请求的操作。

这个类是 Java 集合框架的成员。

所有 java 错误都实现了 java.lang.Throwable 接口，或者是从另一个类继承的。这个例外的层次结构是-

> java.lang.Object
> 
> java.lang.Throwable
> 
> java.lang.Exception
> 
> java.lang.RuntimeException
> 
> Java . lang . unsupportedoperationexception

**语法:**

```
public class UnsupportedOperationException
extends RuntimeException
```

出现这个错误的主要原因是 java.util.Arrays 类的 asList 方法返回了一个 ArrayList 的对象，该对象嵌套在类 [java.util.Arrays](https://www.geeksforgeeks.org/array-class-in-java/) 中。ArrayList 扩展了 [java.util.AbstractList](https://www.geeksforgeeks.org/abstractlist-in-java-with-examples/) ，它没有实现 add 或 remove 方法。因此，当在列表对象上调用此方法时，它会调用 AbstractList 类的添加或移除方法，从而引发此异常。此外，asList 方法返回的列表是一个固定大小的列表，因此无法修改。

下面的示例将导致 UnsupportedOperationException，因为它试图向固定大小的列表对象添加新元素

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.Arrays;
import java.util.List;

public class Example {
    public static void main(String[] args)
    {
        String str[] = { "Apple", "Banana" };
        List<String> l = Arrays.asList(str);
        System.out.println(l);

        // It will throw java.lang.UnsupportedOperationException

        l.add("Mango");
    }
}
```

**输出:**

```
Exception in thread "main" java.lang.UnsupportedOperationException
    at java.base/java.util.AbstractList.add(AbstractList.java:153)
    at java.base/java.util.AbstractList.add(AbstractList.java:111)
    at Example.main(Example.java:14)
```

我们可以通过使用可修改的可变列表来解决这个问题，例如**数组列表**。我们使用前面使用的 Arrays.asList 方法创建一个列表，并传递结果列表来创建一个新的 ArrayList 对象。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.ArrayList;
import java.util.List;
import java.util.*;

public class Example {

    public static void main(String[] args) {

        String str[] = { "Apple", "Banana" };
        List<String> list = Arrays.asList(str); 

        List<String> l = new ArrayList<>(list);

        l.add("Mango"); // modify the list

        for(String s: l )
          System.out.println(s);

    }

}
```

**Output**

```
Apple
Banana
Mango

```