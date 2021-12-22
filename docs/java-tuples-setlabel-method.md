# JavaTuples setLabel()方法

> 原文:[https://www.geeksforgeeks.org/java-tuples-setlabel-method/](https://www.geeksforgeeks.org/java-tuples-setlabel-method/)

[组织. javatuples](https://www.geeksforgeeks.org/javatuples-introduction/) 中的**设置标签()**方法用于设置标签值类对象的标签。此方法只能用于 javatuples 库的 LabelValue 类对象。它返回另一个标签值类对象，标签是作为参数传递的元素，值来自上一个标签值类对象。

**方法声明:**

```java
public <X> LabelValue<X, B> setLabel(X label)
```

**语法:**

```java
LabelValue<X, B> LabelValueClassObject = LabelValue.setLabel(X label)
```

**返回值:**这个方法返回另一个 LabelValueClassObject，其中 Label 是作为参数传递的元素，而 Value 来自上一个 LabelValueClassObject。

以下程序将说明使用 setLabel()方法的各种方法:

**例 1** :

```java
// Below is a Java program to set
// label in a LabelValue pair

import java.util.*;
import org.javatuples.LabelValue;

class GfG {
    public static void main(String[] args)
    {
        // Creating a LabelValue object
        LabelValue<Integer, String> lv
            = LabelValue.with(Integer.valueOf(1),
                              "A computer science portal");

        // Using setLabel() method
        LabelValue<String, String> lv1 = lv.setLabel("GeeksforGeeks");

        // Printing the returned LabelValue
        System.out.println(lv1);
    }
}
```

**输出**:

```java
[GeeksforGeeks, A computer science portal]

```

**例 2** :

```java
// Below is a Java program to set
// label in a LabelValue pair

import java.util.*;
import org.javatuples.LabelValue;

class GfG {
    public static void main(String[] args)
    {
        // Creating a LabelValue object
        LabelValue<Integer, String> lv
            = LabelValue.with(Integer.valueOf(1),
                              "1");

        // Using setLabel() method
        LabelValue<String, String> lv1 = lv.setLabel("One");

        // Printing the returned LabelValue
        System.out.println(lv1);
    }
}
```

**输出**:

```java
[One, 1]

```