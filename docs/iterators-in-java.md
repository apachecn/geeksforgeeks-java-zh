# Java 中的迭代器

> 原文:[https://www.geeksforgeeks.org/iterators-in-java/](https://www.geeksforgeeks.org/iterators-in-java/)

Java 中的[集合框架](https://www.geeksforgeeks.org/collections-in-java-2/)中使用迭代器来逐个检索元素。Java 中有**三个迭代器**

1.  列举
2.  迭代程序
3.  列表迭代器

### 1.列举

这是一个用于获取遗留集合(矢量，哈希表)元素的接口。枚举是 JDK 1.0 中出现的第一个迭代器，休止符包含在 JDK 1.2 中，功能更多。枚举也用于指定*序列输入流*的输入流。我们可以通过在任何向量对象
上调用向量类的*元素()*方法来创建枚举对象

```java
// Here "v" is an Vector class object. e is of
// type Enumeration interface and refers to "v"
Enumeration e = v.elements();
```

枚举界面有两种**方法，即:**

```java
// Tests if this enumeration contains more elements
public boolean hasMoreElements();

// Returns the next element of this enumeration 
// It throws NoSuchElementException
// if no more element present
public Object nextElement();
```

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to demonstrate Enumeration

// Importing Enumeration and Vector classes
// from java.util package
import java.util.Enumeration;
import java.util.Vector;

// Main class
public class Test
{
    // Main driver method
    public static void main(String[] args)
    {
        // Creating a vector object
        Vector v = new Vector();

      // Iterating over vector object
      for (int i = 0; i < 10; i++)
            v.addElement(i);

      // Printing elements in vector object 
      System.out.println(v);

        // At beginning e(cursor) will point to
        // index just before the first element in v
        Enumeration e = v.elements();

        // Checking the next element availability where
        // condition holds true till threre is a single element
      // remaining in the List
        while (e.hasMoreElements())
        {
            // Moving cursor to next element
            int i = (Integer)e.nextElement();

            // Print above elements in object
            System.out.print(i + " ");
        }
    }
}
```