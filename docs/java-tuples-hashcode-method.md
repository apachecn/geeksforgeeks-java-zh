# JavaTuples hashcode()方法

> 原文:[https://www.geeksforgeeks.org/java-tuples-hashcode-method/](https://www.geeksforgeeks.org/java-tuples-hashcode-method/)

[org.javatuples](https://www.geeksforgeeks.org/javatuples-introduction/) 方法中的 **hashCode()** 方法返回 JavaTuple 类对象的哈希代码。如果对象没有改变，hashcode 总是相同的。Hashcode 是 JVM 在创建对象时生成的唯一代码。它可以用来对哈希表、哈希表等哈希相关算法进行操作。也可以用这个唯一的代码搜索一个对象。

**方法声明:**

```
public final int hashCode()
```

**语法:**

```
int code = TupleClassObject.hashCode()
```

这里 **TupleClassObject** 代表像单位、四重奏、十年、键值等使用的 JavaTuple 类。

**返回:**它返回一个**整数**值，该值代表此 TupleClassObject 的哈希值。

下面的程序说明了 TupleClassObject:
**的 hashcode()方法程序 1:** 获取一个四方类对象的 hash 代码。

```
// Below is a Java program to use hashCode()
// with a LabelValue tuple

import java.util.*;
import org.javatuples.Quartet;

class GfG {
    public static void main(String[] args)
    {
        // Creating a Quartet with 4 values
        Quartet<Integer, String, String, Double> quartet
            = Quartet.with(Integer.valueOf(1),
                           "GeeksforGeeks",
                           "A computer portal",
                           Double.valueOf(20.18));

        // Using the hashCode() method
        int code = quartet.hashCode();

        // Printing the returned hashCode
        System.out.println(code);
    }
}
```

**输出:**

```
-1296686340

```

**程序 2:** 获取一个 LabelValue Class 对象的哈希代码。

```
// Below is a Java program to use hashCode()
// with a LabelValue tuple

import java.util.*;
import org.javatuples.LabelValue;

class GfG {
    public static void main(String[] args)
    {
        // Creating a LabelValue object
        LabelValue<Integer, String> lv
            = LabelValue.with(Integer.valueOf(1),
                              "A computer science portal");

        // Using the hashCode() method
        int code = lv.hashCode();

        // Printing the returned hashCode
        System.out.println(code);
    }
}
```

**输出:**

```
-1587127699

```

**注意:**同样，它也可以用于任何其他 JavaTuple 类。