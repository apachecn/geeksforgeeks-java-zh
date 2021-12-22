# Java 中的枚举接口

> 原文:[https://www . geesforgeks . org/enumeration-interface-in-Java/](https://www.geeksforgeeks.org/enumeration-interface-in-java/)

**java.util.Enumeration** 接口是预定义接口之一，其对象用于从 collections 框架变量中检索数据(如 [Stack](https://www.geeksforgeeks.org/stack-class-in-java/) 、 [Vector](https://www.geeksforgeeks.org/java-util-vector-class-java/) 、 [HashTable](https://www.geeksforgeeks.org/hashtable-in-java/) 等)。)仅在向前的方向，而不在向后的方向。这个接口已经被迭代器取代了。

枚举接口定义了函数，通过这些函数我们可以枚举元素集合中的元素。对于新代码，枚举被认为是过时的。但是，遗留类的一些方法，如向量和属性、几个应用编程接口类、应用程序代码都使用这个枚举接口。

**重要特性**

*   枚举是同步的。
*   它不支持添加、移除或替换元素。
*   可以使用枚举向前访问旧集合的元素。
*   遗留类有处理枚举的方法，并返回枚举对象。

**申报**

```
public interface Enumeration<E>
```

其中 **E** 是存储在集合中的元素类型。

枚举接口的子接口为 NamingEnumeration，实现类为 [StringTokenizer](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/stringtokenizer-class-java-example-set-1-constructors/&sa=U&ved=2ahUKEwipt9Ww2OrsAhXsH7cAHaYQAcIQFjAAegQIBhAC&usg=AOvVaw1YcZciZ9mHQEzgF6N_jBZ3) 。

**创建枚举对象**

```
Vector ve = new Vector();
Enumeration e = v.elements();
```

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to test Enumeration
import java.util.Vector;
import java.util.Enumeration;

public class EnumerationClass {

    public static void main(String args[])
    {
        Enumeration months;
        Vector<String> monthNames = new Vector<>();

        monthNames.add("January");
        monthNames.add("February");
        monthNames.add("March");
        monthNames.add("April");
        monthNames.add("May");
        monthNames.add("June");
        monthNames.add("July");
        monthNames.add("August");
        monthNames.add("September");
        monthNames.add("October");
        monthNames.add("November");
        monthNames.add("December");
        months = monthNames.elements();

        while (months.hasMoreElements()) {
            System.out.println(months.nextElement());
        }
    }
}
```

**Output**

```
January
February
March
April
May
June
July
August
September
October
November
December
```

**带 SequenceInputStream 的 Java 枚举接口**

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.io.*;
import java.util.*;
class GFG {
    public static void main(String args[])
        throws IOException
    {
        // creating the FileInputStream objects for all the
        // files
        FileInputStream fin
            = new FileInputStream("file1.txt");
        FileInputStream fin2
            = new FileInputStream("file2.txt");
        FileInputStream fin3
            = new FileInputStream("file3.txt");
        FileInputStream fin4
            = new FileInputStream("file4.txt");
        // creating Vector object to all the stream
        Vector v = new Vector();
        v.add(fin);
        v.add(fin2);
        v.add(fin3);
        v.add(fin4);

        // creating enumeration object by calling the
        // elements method
        Enumeration e = v.elements();

        // passing the enumeration object in the constructor
        SequenceInputStream bin
            = new SequenceInputStream(e);
        int i = 0;
        while ((i = bin.read()) != -1) {
            System.out.print((char)i);
        }
        bin.close();
        fin.close();
        fin2.close();
    }
}
```

**自定义枚举的创建**

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.Enumeration;
import java.lang.reflect.Array;

public class EnumerationClass implements Enumeration {
    private int size;
    private int cursor;
    private final Object array;
    public EnumerationClass(Object obj)
    {
        Class type = obj.getClass();
        if (!type.isArray()) {
            throw new IllegalArgumentException(
                "Invalid type: " + type);
        }
        size = Array.getLength(obj);
        array = obj;
    }
    public boolean hasMoreElements()
    {
        return (cursor < size);
    }
    public object nextElements()
    {
        return Array.get(array, cursor++);
    }
}
```

**使用字符串数组创建 Java 枚举**

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.util.*;
import java.io.*;

public class EnumerationExample {
    public static void main(String args[])
    {
        // String Array Creation
        String str[] = { "apple", "facebook", "google" };

        // Array Enumeration Creation
        ArrayEnumeration aenum = new ArrayEnumeration(str);

        // usageof array enumeration
        while (aenum.hasMoreElements()) {
            System.out.println(aenum.nextElement());
        }
    }
}
```

### 枚举接口的方法

*   **E–**元素类型

<figure class="table">

| 

**修改器和类型**

 | 

**方法**

 | 

**解释**

 |
| --- | --- | --- |
| 默认迭代器 | [asIterator()](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/enumeration-asiterator-method-in-java-with-examples/&sa=U&ved=2ahUKEwik2dWY0ejsAhWE7XMBHf81C10QFjAAegQIBBAB&usg=AOvVaw1RgNhRPGYXuVjfRAyg0cG_) | 这个方法返回一个迭代器，遍历这个枚举覆盖的所有剩余元素。 |
| 布尔 | [【has more elements()](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/enumeration-hasmoreelements-method-in-java-with-examples/&sa=U&ved=2ahUKEwjky-Gq0ejsAhVR8HMBHc4tBT0QFjAAegQIARAC&usg=AOvVaw06LO5Jqmaw0cibLQ-urvfo) | 在实现时，如果有更多的元素要提取或不提取，它将返回布尔值，当所有的元素都被枚举后，它将返回 false。 |
| E | [nextElement()](https://www.google.com/url?client=internal-element-cse&cx=009682134359037907028:tj6eafkv_be&q=https://www.geeksforgeeks.org/enumeration-nextelement-method-in-java-with-examples/&sa=U&ved=2ahUKEwjZ8M2w0ejsAhVU6XMBHZMqA7QQFjAAegQIBRAC&usg=AOvVaw2ohTAZLxQhYhgiPKkfFFeg) | 此方法返回枚举的下一个元素。当没有更多元素时，它会抛出 **NoSuchElementException** 。 |

</figure>