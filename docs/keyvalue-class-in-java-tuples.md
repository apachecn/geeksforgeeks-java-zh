# JavaToPles 中的键值类

> 原文:[https://www . geesforgeks . org/key value-in-Java-class-元组/](https://www.geeksforgeeks.org/keyvalue-class-in-java-tuples/)

一个**键值**是一个来自 [**JavaTuples**](https://www.geeksforgeeks.org/javatuples-introduction/) 库的元组，它只处理两个元素——一个键和值。因为这个键值是一个泛型类，所以它可以保存任何类型的值。

由于键值是一个元组，因此它也具有 JavaTuples 的所有特征:

*   它们是**型安全**
*   它们是**不可改变的**
*   它们是**可重复的**
*   它们是**可序列化的**
*   它们是**可比的**(实现可比的<元组>
*   它们实现了**等于()**和**哈希码()**
*   它们还实现了 **toString()**

### 类别声明

```java
public final class KeyValue<A, B> extends Tuple 
           implements IValueKey<A>, IValueValue<B>
```

### 类层次

```java
Object
  ↳ org.javatuples.Tuple
      ↳ org.javatuples.KeyValue<A, B>
```

### 创建键值元组

*   **从建造师**:
    T3】语法:

```java
KeyValue<A, B> kv = new KeyValue<A, B>(value1, value2);
```

**例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to create
// a KeyValue tuple from Constructor

import java.util.*;
import org.javatuples.KeyValue;

class GfG {
    public static void main(String[] args)
    {
        KeyValue<Integer, String> kv
            = new KeyValue<Integer, String>(Integer.valueOf(1), "GeeksforGeeks");

        System.out.println(kv);
    }
}
```