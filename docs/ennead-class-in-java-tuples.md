# JavaTuples 中的 Ennead 类

> 原文:[https://www.geeksforgeeks.org/ennead-class-in-java-tuples/](https://www.geeksforgeeks.org/ennead-class-in-java-tuples/)

一个来自**的元组处理 9 个元素。因为这个 Ennead 是一个泛型类，所以它可以保存任何类型的值。**

由于 Ennead 是一个元组，因此它也具有 JavaTuples 的所有特征:

*   它们是**型安全**
*   它们是**不可改变的**
*   它们是**可重复的**
*   它们是**可序列化的**
*   它们是**可比的**(实现可比的<元组>
*   它们实现了**等于()**和**哈希码()**
*   它们还实现了 **toString()**

### 类别声明

```java
public final class Ennead<A, B, C, D, E, F, G, H, I>
extends Tuple
implements IValue0<A&gt, IValue1<B>, IValue2<C>, IValue3<D>, IValue4<E>, 
           IValue5<F, IValue6<G, IValue7<H&gt, IValue8<I> 
```

### 类层次

```java
Object
  ↳ org.javatuples.Tuple
      ↳ org.javatuples.Ennead<A, B, C, D, E, F, G, H, I> 
```

### 创建恩内元组

*   **从建造师**:
    T3】语法:

```java
Ennead<A, B, C, D, E, F, G, H, I> ennead = 
    new Ennead<A, B, C, D, E, F, G, H, I>
        (value1, value2, value3, value4, value5, value6, value7, value8, value9);
```

*   **例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to create
// a Ennead tuple from Constructor

import java.util.*;
import org.javatuples.Ennead;

class GfG {
    public static void main(String[] args)
    {
        Ennead<Integer, Integer, Integer, Integer, Integer, Integer, Integer, Integer, Integer> ennead
            = Ennead.with(Integer.valueOf(1),
                          Integer.valueOf(2),
                          Integer.valueOf(3),
                          Integer.valueOf(4),
                          Integer.valueOf(5),
                          Integer.valueOf(6),
                          Integer.valueOf(7),
                          Integer.valueOf(8),
                          Integer.valueOf(9));

        System.out.println(ennead);
    }
}
```

输出:

```java
[1, 2, 3, 4, 5, 6, 7, 8, 9]
```

*   **使用 with()方法**:with()方法是 JavaTuples 库提供的一个函数，用这样的值来实例化对象。
    **句法**:

```java
Ennead<type1, type2, type3, type4, type5, type6, type7, type8> ennead = 
    Ennead.with(value1, value2, value3, value4, value5, value6, value7, value8, value9);
```

*   **例**:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Below is a Java program to create
// a Ennead tuple from with() method

import java.util.*;
import org.javatuples.Ennead;

class GfG {
    public static void main(String[] args)
    {
        Ennead<Integer, Integer, Integer, Integer, Integer, Integer, Integer, Integer, Integer> ennead
            = Ennead.with(Integer.valueOf(1),
                          Integer.valueOf(2),
                          Integer.valueOf(3),
                          Integer.valueOf(4),
                          Integer.valueOf(5),
                          Integer.valueOf(6),
                          Integer.valueOf(7),
                          Integer.valueOf(8),
                          Integer.valueOf(9));

        System.out.println(ennead);
    }
}
```