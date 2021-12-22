# JavaTuples 中的标签值类

> 原文:[https://www . geeksforgeeks . org/labelvalue-class-in-Java-元组/](https://www.geeksforgeeks.org/labelvalue-class-in-java-tuples/)

一个**标签值**是一个来自 [**JavaTuples**](https://www.geeksforgeeks.org/javatuples-introduction/) 库的元组，它只处理两个元素——一个标签和值。因为这个标签值是一个泛型类，所以它可以保存任何类型的值。

由于标签值是一个元组，因此它也具有 JavaTuples 的所有特征:

*   它们是**型安全**
*   它们是**不可改变的**
*   它们是**可重复的**
*   它们是**可序列化的**
*   它们是**可比的**(实现可比的<元组>
*   它们实现了**等于()**和**哈希码()**
*   它们还实现了 **toString()**

### 类别声明

```java
public final class LabelValue<A, B> extends Tuple 
           implements IValueLabel<A>, IValueValue<B> 
```

### 类层次

```java
Object
  ↳ org.javatuples.Tuple
      ↳ org.javatuples.LabelValue<A, B> 
```

### 创建标签值元组

*   **从建造师**:
    T3】语法:

```java
LabelValue<A, B> kv = new LabelValue<A, B>(value1, value2);
```

*   **例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to create
// a LabelValue tuple from Constructor

import java.util.*;
import org.javatuples.LabelValue;

class GfG {
    public static void main(String[] args)
    {
        LabelValue<Integer, String> kv
            = new LabelValue<Integer, String>(Integer.valueOf(1),
                                              "GeeksforGeeks");

        System.out.println(kv);
    }
}
```

输出:

```java
[1, GeeksforGeeks]
```

*   **使用 with()方法**:with()方法是 JavaTuples 库提供的一个函数，用这样的值来实例化对象。
    **句法**:

```java
LabelValue<type1, type2> kv = LabelValue.with(value1, value2);
```

*   **例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to create
// a LabelValue tuple from with() method

import java.util.*;
import org.javatuples.LabelValue;

class GfG {
    public static void main(String[] args)
    {
        LabelValue<Integer, String> kv
            = LabelValue.with(Integer.valueOf(1), "GeeksforGeeks");

        System.out.println(kv);
    }
}
```

输出:

```java
[1, GeeksforGeeks]
```

*   **来自其他集合**:From collection()方法用于从集合创建 Tuple，fromArray()方法用于从数组创建。集合/数组的类型必须与元组的类型相同，并且集合/数组中的值的数量必须与元组类匹配。
    **句法**:

```java
LabelValue<type1, type2> kv = LabelValue.fromCollection(collectionWith_2_value);
LabelValue<type1, type2> kv = LabelValue.fromArray(arrayWith_2_value);
```

*   **例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to create
// a LabelValue tuple from Collection

import java.util.*;
import org.javatuples.LabelValue;

class GfG {
    public static void main(String[] args)
    {
        // Creating LabelValue from List
        List<String> list = new ArrayList<String>();
        list.add("GeeksforGeeks");
        list.add("A computer portal");
        LabelValue<String, String> kv
            = LabelValue.fromCollection(list);

        // Creating LabelValue from Array
        String[] arr = { "GeeksforGeeks", "A computer portal" };
        LabelValue<String, String> otherLabelValue
            = LabelValue.fromArray(arr);

        System.out.println(kv);
        System.out.println(otherLabelValue);
    }
}
```

输出:

```java
[GeeksforGeeks, A computer portal]
[GeeksforGeeks, A computer portal]
```

### 获取价值

getValue()和 getLabel()方法可用于分别获取 LabelValue 元组中的值和键。

*   **getLabel()**:
    T3】语法:

```java
LabelValue<type1, type2> kv = 
    new LabelValue<type1, type2>(value1, value2);

type2 val1 = kv.getLabel();
```

*   **例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to get
// a LabelValue value

import java.util.*;
import org.javatuples.LabelValue;

class GfG {
    public static void main(String[] args)
    {
        LabelValue<Integer, String> kv
            = LabelValue.with(Integer.valueOf(1), "GeeksforGeeks");

        System.out.println(kv.getLabel());
    }
}
```

输出:

```java
1
```

*   **getValue()**:
    T3】语法:

```java
LabelValue<type1, type2> kv = 
    new LabelValue<type1, type2>(value1, value2);

type2 val1 = kv.getValue();
```

*   **例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to get
// a LabelValue value

import java.util.*;
import org.javatuples.LabelValue;

class GfG {
    public static void main(String[] args)
    {
        LabelValue<Integer, String> kv
            = LabelValue.with(Integer.valueOf(1), "GeeksforGeeks");

        System.out.println(kv.getValue());
    }
}
```