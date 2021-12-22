# JavaTuples 中的十年类

> 原文:[https://www.geeksforgeeks.org/decade-class-in-java-tuples/](https://www.geeksforgeeks.org/decade-class-in-java-tuples/)

一个**十年**是一个来自 **JavaTuples** 库的元组，处理 3 个元素。因为这个十年是一个泛型类，所以它可以包含任何类型的值。
由于十年是一个元组，因此它也具有 JavaTuples 的所有特征:

*   它们是**型安全**
*   它们是**不可改变的**
*   它们是**可重复的**
*   它们是**可序列化的**
*   它们是**可比的**(实现可比的<元组>
*   它们实现了**等于()**和**哈希码()**
*   它们还实现了 **toString()**

### 类别声明

```
public final class Decade<A, B, C, D, E, F, G, H, I, J>
extends Tuple
implements IValue0<A>, IValue1<B>, IValue2<C>, IValue3<D>, IValue4<E>, 
           IValue5<F, IValue6<G, IValue7<H>, IValue8<I, J>
```

### 类层次

```
Object
  ↳ org.javatuples.Tuple
      ↳ org.javatuples.Decade<A, B, C, D, E, F, G, H, I, J>
```

**创建十年元组**

*   **从构造器**:
    T3】语法 :

```
Decade<A, B, C, D, E, F, G, H, I, J> decade = 
    new Decade<A, B, C, D, E, F, G, H, I, J>
        (value1, value2, value3, value4, value5, value6, value7, value8, value9, value10);
```

*   **例** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to create
// a Decade tuple from Constructor

import java.util.*;
import org.javatuples.Decade;

class GfG {
    public static void main(String[] args)
    {
        Decade<Integer, Integer, Integer, Integer, Integer, Integer, Integer,
                                            Integer, Integer, Integer> decade
            = Decade.with(Integer.valueOf(1),
                        Integer.valueOf(2),
                        Integer.valueOf(3),
                        Integer.valueOf(4),
                        Integer.valueOf(5),
                        Integer.valueOf(6),
                        Integer.valueOf(7),
                        Integer.valueOf(8),
                        Integer.valueOf(9),
                        Integer.valueOf(10));

        System.out.println(decade);
    }
}
```

*   输出:

```
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

*   **使用 with()方法**:with()方法是 JavaTuples 库提供的一个函数，用这样的值来实例化对象。
    **语法** :

```
Decade<type1, type2, type3, type4, type5, type6, type7, type8, type9> decade = 
    Decade.with(value1, value2, value3, value4, value5, value6, value7, value8, value9, value10);
```

*   **例** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to create
// a Decade tuple from with() method

import java.util.*;
import org.javatuples.Decade;

class GfG {
    public static void main(String[] args)
    {
        Decade<Integer, Integer, Integer, Integer, Integer, Integer, Integer, Integer,
                                                               Integer, Integer> decade
            = Decade.with(Integer.valueOf(1),
                          Integer.valueOf(2),
                          Integer.valueOf(3),
                          Integer.valueOf(4),
                          Integer.valueOf(5),
                          Integer.valueOf(6),
                          Integer.valueOf(7),
                          Integer.valueOf(8),
                          Integer.valueOf(9),
                          Integer.valueOf(10));

        System.out.println(decade);
    }
}
```

*   输出:

```
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

*   **来自其他集合**:From collection()方法用于从集合创建 Tuple，fromArray()方法用于从数组创建。集合/数组的类型必须与元组的类型相同，并且集合/数组中的值的数量必须与元组类匹配。
    **语法** :

```
Decade<type1, type2, type3, type4, type5, type6, type7, type8, type9> decade = 
    Decade.fromCollection(collectionWith_10_value);

Decade<type1, type2, type3, type4, type5, type6, type7, type8, type9> decade = 
    Decade.fromArray(arrayWith_10_value);
```

*   **例** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to create
// a Decade tuple from Collection

import java.util.*;
import org.javatuples.Decade;

class GfG {
    public static void main(String[] args)
    {
        // Creating Decade from List
        List<Integer> list = new ArrayList<Integer>();
        list.add(1);
        list.add(2);
        list.add(3);
        list.add(4);
        list.add(5);
        list.add(6);
        list.add(7);
        list.add(8);
        list.add(9);
        list.add(10);

        Decade<Integer, Integer, Integer, Integer, Integer, Integer, Integer,
                                              Integer, Integer, Integer> decade
            = Decade.fromCollection(list);

        // Creating Decade from Array
        Integer[] arr = { 1, 2, 3, 4, 5, 6, 7, 8, 9, 10 };

        Decade<Integer, Integer, Integer, Integer, Integer, Integer, Integer,
                                           Integer, Integer, Integer> otherDecade
            = Decade.fromArray(arr);

        System.out.println(decade);
        System.out.println(otherDecade);
    }
}
```

*   输出:

```
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```

### 获取价值

getValueX()方法可用于在索引 x 处获取元组中的值。元组中的索引从 0 开始。因此，索引 X 处的值代表位置 X+1 处的值。
**语法** :

```
Decade<type1, type2, type3, type4, type5, type6, type7, type8, type9> decade = 
    new Decade<type1, type2, type3, type4, type5, type6, type7, type8, type9>
        (value1, value2, value3, value4, value5, value6, value7, value8, value9, value10);

type1 val1 = decade.getValue0();
```

**例** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to get
// a Decade value

import java.util.*;
import org.javatuples.Decade;

class GfG {
    public static void main(String[] args)
    {
        Decade<Integer, Integer, Integer, Integer, Integer, Integer, Integer,
                                               Integer, Integer, Integer> decade
            = Decade.with(Integer.valueOf(1),
                          Integer.valueOf(2),
                          Integer.valueOf(3),
                          Integer.valueOf(4),
                          Integer.valueOf(5),
                          Integer.valueOf(6),
                          Integer.valueOf(7),
                          Integer.valueOf(8),
                          Integer.valueOf(9),
                          Integer.valueOf(10));

        System.out.println(decade.getValue0());
        System.out.println(decade.getValue2());
    }
}
```

输出:

```
1
3
```

### 设置十进制值

由于元组是**不可变的**，这意味着在任何索引处修改值都是不可能的。
因此 JavaTuples 提供 **setAtX(value)** ，它在索引 X 处创建一个具有新值的元组的副本，并返回该元组。
**语法** :

```
Decade<type1, type2, type3, type4, type5, type6, type7, type8, type9> decade = 
    new Decade<type1, type2, type3, type4, type5, type6, type7, type8, type9>
                (value1, value2, value3, value4, value5, value6, value7, value8, value9, value10);

Decade<type1, type2, type3, type4, type5, type6, type7, type8, type9> 
    otherDecade = decade.setAtX(value);
```

**例** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to set
// a Decade value

import java.util.*;
import org.javatuples.Decade;

class GfG {
    public static void main(String[] args)
    {
        Decade<Integer, Integer, Integer, Integer, Integer, Integer, Integer,
                                               Integer, Integer, Integer> decade
            = Decade.with(Integer.valueOf(1),
                          Integer.valueOf(2),
                          Integer.valueOf(3),
                          Integer.valueOf(4),
                          Integer.valueOf(5),
                          Integer.valueOf(6),
                          Integer.valueOf(7),
                          Integer.valueOf(8),
                          Integer.valueOf(9),
                          Integer.valueOf(10));

        Decade<Integer, Integer, Integer, Integer, Integer, Integer, Integer,
                                            Integer, Integer, Integer> otherDecade
            = decade.setAt3(40);

        System.out.println(otherDecade);
    }
}
```

输出:

```
[1, 2, 3, 40, 5, 6, 7, 8, 9, 10]
```

### 添加值

JavaTuples 不支持超过 10 个值的元组。因此**没有在十进制中增加值的功能**。

### 十年寻找

可以使用预定义的方法**在元组中搜索元素，该方法包含()**。无论该值是否存在，它都会返回一个布尔值。
**语法** :

```
Decade<type1, type2, type3, type4, type5, type6, type7, type8, type9> decade = 
    new Decade<type1, type2, type3, type4, type5, type6, type7, type8, type9>
        (value1, value2, value3, value4, value5, value6, value7, value8, value9, value10);

boolean res = decade.contains(value2);
```

**例** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to search
// a value in a Decade

import java.util.*;
import org.javatuples.Decade;

class GfG {
    public static void main(String[] args)
    {
        Decade<Integer, Integer, Integer, Integer, Integer, Integer, Integer,
                                             Integer, Integer, Integer> decade
            = Decade.with(Integer.valueOf(1),
                          Integer.valueOf(2),
                          Integer.valueOf(3),
                          Integer.valueOf(4),
                          Integer.valueOf(5),
                          Integer.valueOf(6),
                          Integer.valueOf(7),
                          Integer.valueOf(8),
                          Integer.valueOf(9),
                          Integer.valueOf(10));

        boolean exist = decade.contains(5);
        boolean exist1 = decade.contains(false);

        System.out.println(exist);
        System.out.println(exist1);
    }
}
```

输出:

```
true
false
```

### 十年迭代

十年以来实现**可迭代<对象>T1】界面。这意味着它们可以像集合或数组一样迭代。
**语法** :** 

```
Decade<type1, type2, type3, type4, type5, type6, type7, type8, type9> decade = 
    new Decade<type1, type2, type3, type4, type5, type6, type7, type8, type9>
            (value1, value2, value3, value4, value5, value6, value7, value8, value9, value10);

for (Object item : decade) {
        ...
}
```

**例** :

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Below is a Java program to iterate
// a Decade

import java.util.*;
import org.javatuples.Decade;

class GfG {
    public static void main(String[] args)
    {
        Decade<Integer, Integer, Integer, Integer, Integer, Integer, Integer,
                                               Integer, Integer, Integer> decade
            = Decade.with(Integer.valueOf(1),
                          Integer.valueOf(2),
                          Integer.valueOf(3),
                          Integer.valueOf(4),
                          Integer.valueOf(5),
                          Integer.valueOf(6),
                          Integer.valueOf(7),
                          Integer.valueOf(8),
                          Integer.valueOf(9),
                          Integer.valueOf(10));

        for (Object item : decade)
            System.out.println(item);
    }
}
```

输出:

```
1
2
3
4
5
6
7
8
9
10
```