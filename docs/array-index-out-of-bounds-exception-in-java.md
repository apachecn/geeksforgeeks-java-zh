# Java 中数组索引越界异常

> 原文:[https://www . geesforgeks . org/array-index-越界-java 中的异常/](https://www.geeksforgeeks.org/array-index-out-of-bounds-exception-in-java/)

Java 支持[数组](https://www.geeksforgeeks.org/data-structures/#Array)作为数据结构的创建和操作。数组的索引是一个整数值，其值在区间[0，n-1]内，其中 n 是数组的大小。如果请求一个负数或大于或等于数组大小的索引，那么 JAVA 会抛出一个 ArrayIndexOutOfBounds 异常。这与 C/C++不同，在 C/c++中，绑定检查没有索引。

**ArrayindexOutofBoundSexception**是一个只在运行时抛出的运行时异常。Java 编译器在编译程序时不会检查这个错误。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// A Common cause index out of bound
public class NewClass2 {
    public static void main(String[] args)
    {
        int ar[] = { 1, 2, 3, 4, 5 };
        for (int i = 0; i <= ar.length; i++)
            System.out.println(ar[i]);
    }
}
```

**预期输出:**

```java
1
2
3
4
5
```

**原始输出:**

**运行时错误引发异常:**

```java
Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException: 5
    at NewClass2.main(NewClass2.java:5)
```

这里如果你仔细看，数组的大小是 5。因此，当使用 for 循环访问它的元素时，最大索引值可以是 4，但是在我们的程序中，它一直到 5，因此是异常。

让我们看看另一个使用数组列表的例子:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// One more example with index out of bound
import java.util.ArrayList;
public class NewClass2
{
    public static void main(String[] args)
    {
        ArrayList<String> lis = new ArrayList<>();
        lis.add("My");
        lis.add("Name");
        System.out.println(lis.get(2));
    }
}
```

这里的运行时错误比上一次提供的信息要多一点-

```java
Exception in thread "main" java.lang.IndexOutOfBoundsException: Index: 2, Size: 2
    at java.util.ArrayList.rangeCheck(ArrayList.java:653)
    at java.util.ArrayList.get(ArrayList.java:429)
    at NewClass2.main(NewClass2.java:7)
```

让我们详细了解一下:

*   这里的索引定义了我们试图访问的索引。
*   大小给了我们关于列表大小的信息。
*   由于大小是 2，我们可以访问的最后一个索引是(2-1)=1，因此是例外。

访问数组的正确方式是:

```java
for (int i=0; i<ar.length; i++){

}
```

**正确代码–**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Correct code for Example 1
public class NewClass2 {
    public static void main(String[] args)
    {
        int ar[] = { 1, 2, 3, 4, 5 };

        for (int i = 0; i < ar.length; i++)
            System.out.println(ar[i]);
    }
}
```

**Output**

```java
1
2
3
4
5
```