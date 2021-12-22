# JavaTuples getLabel()方法

> 原文:[https://www.geeksforgeeks.org/java-tuples-getlabel-method/](https://www.geeksforgeeks.org/java-tuples-getlabel-method/)

[组织. javatuples](https://www.geeksforgeeks.org/javatuples-introduction/) 中的 **getLabel()** 方法用于从标签值类中的 TupleClassObject 获取标签。此方法只能用于 javatuples 库的 LabelValue 类对象。它返回一个标签，该标签是标签值类对象的索引 0 处的元素。返回的标签确保类型安全。

**方法声明:**

```
public A getLabel()
```

**语法:**

```
LabelValue 
```

**返回值:**这个方法返回一个标签，它是标签值类对象的索引 0 处的元素。

下面的程序说明了使用 getLabel()方法的各种方法:

**例 1** :

```
// Below is a Java program to get
// a LabelValue value

import java.util.*;
import org.javatuples.LabelValue;

class GfG {
    public static void main(String[] args)
    {
        // Creating a LabelValue object
        LabelValue<Integer, String> lv
            = LabelValue.with(Integer.valueOf(1), "GeeksforGeeks");

        // Using getLabel() method
        int label = lv.getLabel();

        // Printing the Label
        System.out.println(label);
    }
}
```

**输出**:

```
1

```

**例 2** :

```
// Below is a Java program to get
// a LabelValue value

import java.util.*;
import org.javatuples.LabelValue;

class GfG {
    public static void main(String[] args)
    {
        // Creating a LabelValue object
        LabelValue<String, String> lv
            = LabelValue.with("GeeksforGeeks",
                              "A Computer Science Portal for Geeks");

        // Using getLabel() method
        String label = lv.getLabel();

        // Printing the Label
        System.out.println(label);
    }
}
```

**输出**:

```
GeeksforGeeks

```