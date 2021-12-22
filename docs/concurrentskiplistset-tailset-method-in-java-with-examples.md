# Java 中的 ConcurrentSkipListSet tailSet()方法，带示例

> 原文:[https://www . geeksforgeeks . org/concurrentskiplistset-tailset-method-in-Java-with-examples/](https://www.geeksforgeeks.org/concurrentskiplistset-tailset-method-in-java-with-examples/)

[**的 **tailSet()** 方法是 java 中的一个内置函数，返回等于或大于指定元素的元素。
函数的语法给出了对指定元素的清晰理解，后面是示例。
**语法:****](https://www.geeksforgeeks.org/concurrentskiplistset-in-java-with-examples/) 

```
tailSet(E fromElement)
           or 
tailSet(E fromElement, boolean inclusive)
```

**参数:**
这个方法的第一个变体只取一个参数，即 fromElement **E** ，大于或等于这个元素的元素从集合中返回。
第二个变化与第一个相似，但是这里第二个参数是布尔型的，如果设置为假
，那么元素 **E** (如果出现在列表中)将不被包括在内。
**返回:**
该方法返回该集合中元素大于或等于 fromElement 的部分的视图。
在第二种变化的情况下，这个 fromElement 的包含由布尔类型决定。
**异常:**
**空指针异常:**如果指定的元素为空。
下面是用 Java 说明 ConcurrentSkipListSet tailSet()的示例程序:
**示例:1**
返回大于 200 的元素。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate ConcurrentSkipListSet tailSet() method

import java.util.concurrent.ConcurrentSkipListSet;

class ConcurrentSkipListSetLastExample1 {
    public static void main(String[] args)
    {

        // Initializing the set using ConcurrentSkipListSet()
        ConcurrentSkipListSet<Integer>
            set = new ConcurrentSkipListSet<Integer>();

        // Adding elements to this set
        set.add(199);
        set.add(256);
        set.add(958);
        set.add(421);
        set.add(80);

        // Printing the ConcurrentSkipListSet
        System.out.println("ConcurrentSkipListSet: "
                           + set);

        // Printing the elements of ConcurrentSkipListSet that
        // are returned by tailSet() method
        System.out.println("The returned elements are: "
                           + set.tailSet(200));
    }
}
```

**Output:** 

```
ConcurrentSkipListSet: [80, 199, 256, 421, 958]
The returned elements are: [256, 421, 958]
```

**示例:2**
在本例中，因为布尔包含为假，所以不返回元素 35。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate ConcurrentSkipListSet tailSet() method

import java.util.concurrent.ConcurrentSkipListSet;

class ConcurrentSkipListSetLastExample1 {
    public static void main(String[] args)
    {

        // Initializing the set using ConcurrentSkipListSet()
        ConcurrentSkipListSet<Integer>
            set = new ConcurrentSkipListSet<Integer>();

        // Adding elements to this set
        set.add(13);
        set.add(35);
        set.add(9);
        set.add(41);
        set.add(90);

        // Printing the ConcurrentSkipListSet
        System.out.println("ConcurrentSkipListSet: "
                           + set);

        // Printing the elements of ConcurrentSkipListSet that
        // are returned by tailSet() method
        System.out.println("The returned elements are: "
                           + set.tailSet(35, false));
    }
}
```

**Output:** 

```
ConcurrentSkipListSet: [9, 13, 35, 41, 90]
The returned elements are: [41, 90]
```