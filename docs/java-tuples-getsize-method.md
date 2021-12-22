# JavaTuples getSize()方法

> 原文:[https://www.geeksforgeeks.org/java-tuples-getsize-method/](https://www.geeksforgeeks.org/java-tuples-getsize-method/)

[org.javatuples](https://www.geeksforgeeks.org/javatuples-introduction/) 中的 **getSize()** 方法用于获取 TupleClassObject 的大小。也就是说，它用于获取 TupleClassObject 中存在的值的数量。这个方法可以用于 javatuples 库的任何元组类对象。它返回一个整数值，该整数值等于 TupleClassObject 中存在的元素数。

**方法申报:**

```java
public abstract int getSize()
```

**语法:**

```java
int size = TupleClassObject.getSize()
```

这里 **TupleClassObject** 代表像 Unit、Quintet、Decade 等使用的 JavaTuple 类对象。

**参数:**该方法不取任何参数。

**返回值:**该方法以整数格式返回 TupleClassObject 中存在的元素数量。

下面的程序说明了使用 getSize()方法的各种方法:

**程序 1:** 使用 getSize()配合单位类:

```java
// Below is a Java program to use getSize() method

import java.util.*;
import org.javatuples.Unit;

class GfG {
    public static void main(String[] args)
    {
        // Creating an Unit with one value
        Unit<String> unit = Unit.with("GeeksforGeeks");

        // Using getSize() method
        int size = unit.getSize();

        System.out.println("Size = " + size);
    }
}
```

**输出:**

```java
Size = 1
```

**程序二:**使用 getSize()配合四方类:

```java
// Below is a Java program to use getSize() method

import java.util.*;
import org.javatuples.Quartet;

class GfG {
    public static void main(String[] args)
    {
        // Creating an Quartet with four values

        Quartet<String, String, String, String> quartet
            = Quartet.with("GeeksforGeeks",
                           "A computer portal",
                           "for geeks",
                           "by Sandeep Jain");

        // Using getSize() method
        int size = quartet.getSize();

        System.out.println("Size = " + size);
    }
}
```

**输出:**

```java
Size = 4
```

**注意:**同样，它也可以用于任何其他 JavaTuple 类。