# 5 个最常见的 Java 陷阱

> 原文:[https://www.geeksforgeeks.org/5-most-common-java-pitfalls/](https://www.geeksforgeeks.org/5-most-common-java-pitfalls/)

**<u>1。不理解字符串是不可变的类:</u>**
Java 字符串类是不可变的*(不可修改)*。这是因为字符串对象缓存在字符串池中。字符串引用的对象可以更改，但字符串对象本身不能更改。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
public class Main {
    public static void main(String[] args)
    {
        String str = "GeeksFor";
        // A new string will be returned, but the actual String will remain the same
        str.concat("Geeks");
        // Prints initial value "GeeksFor"
        System.out.println(str);
        // Now we change the reference of "str" to point to the new String returned
        str = str.concat("Geeks");
        // Prints the new concatenated String
        System.out.println(str);
    }
}
```

```java
Output : GeeksFor 
 GeeksForGeeks
```

**<u>2。内存泄漏:</u>**
Java 的核心优势之一是 [*Java 垃圾收集器*](https://www.geeksforgeeks.org/garbage-collection-java/) ，它管理堆上的对象内存。每当一个对象不可访问时，它就会被自动释放。
然而，对于新的和有经验的程序员来说，一个常见的缺点是通过允许不再使用的对象被访问来防止内存被释放。这对于项目来说是一个非常大的缺点，因为内存泄漏会阻塞资源并降低应用程序的性能。甚至会导致[*Java . lang . out of memory error*](https://www.geeksforgeeks.org/understanding-outofmemoryerror-exception-java/)。

常见情况有:

*   **静态字段**声明一个*静态字段*，在不再需要其数据后忘记将其设置为空
*   **未关闭的流**Java 虚拟机为每个打开的连接分配内存。忘记关闭连接会消耗内存。这样的连接可以是:*输入流*、*数据库连接*、*会话*等。
*   **[***finalize()***](https://practice.geeksforgeeks.org/problems/what-is-finalize-in-java)**方法**当我们覆盖 *finalize()* 方法时，该类的对象不再直接被垃圾收集。然后，垃圾收集器等待终结，这将在稍后的时间点发生。**

****<u>3。前/后递增运算符和副作用:</u>**
Java 中运算符的求值顺序似乎是从左到右求值，副作用瞬间可见:**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
public class Main {
    public static void main(String[] args)
    {
        int num = 0;
        /* First case */
        // The increment operator happens after the value is pushed onto the stack and assigned
        num = num++;
        // Prints initial value
        System.out.println(num);
        /* Second case */
        // Increment occurs first, and then it is pushed to the stack and assigned to num
        num = ++num;
        System.out.println(num);
    }
}
```

```java
**Output : 0** 
 **1** 
```

**<u>第一种情况的执行上下文如下:</u>**

1.  **存储操作数的上一个值。**
2.  **增加该值。**
3.  **返回上一个值**

**<u>第二种情况的执行上下文如下:</u>**

1.  **增加该值。**
2.  **存储操作数*的值(递增)***
3.  **返回值**

****<u>4。使用关系运算符</u>*****<u>" = "</u>*****<u>进行对象比较。</u>**
许多新手程序员试图使用“==”运算符来比较对象，当他们的代码的行为不如预期时，他们会感到困惑。需要注意的是，关系运算符“==”正在进行引用比较，它检查两个对象是否指向内存中的相同位置。使用*。equals()* 方法将消除这个问题，因为它比较对象内部的值。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
public class Main {
    public static void main(String[] args)
    {
        String s1 = new String("GeeksForGeeks");
        String s2 = new String("GeeksForGeeks");
        // Comparing using the relational operator
        if (s1 == s2) { // false
            System.out.println("Both objects point to the same memory location!");
        }
        // Comparing using the .equals()
        if (s1.equals(s2)) { // true
            System.out.println("The value inside the object instances match!");
        }
        // Declaring a string with a reference to s1
        String s3 = s1;
        if (s3 == s1) { // true
            System.out.println("Both objects point to the same memory location!");
        }
    }
}
```

```java
**Output : The value inside the object instances match!** 
 **Both objects point to the same memory location!** 
```

**虽然有时“==”运算符会给出预期的答案:**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
public class Main {
    public static void main(String[] args)
    {
        String s1 = "GeeksForGeeks";
        String s2 = "GeeksForGeeks";
        // Comparing using the relational operator
        if (s1 == s2) { // true
            System.out.println("The two strings are the same!");
        }
        else {
            System.out.println("The two strings are the different!");
        }
    }
}
```

```java
**Output : The two strings are the same!** 
```

**原因在 [Java 语言规范字符串文字](https://docs.oracle.com/javase/specs/jls/se8/html/jls-3.html#jls-3.10.5):“同一包中同一类内的文字字符串表示对同一字符串对象的引用”。代码中的条件为真，因为文字由相同的字符组成。**

****<u>5。使用原始类型</u>**
在 Java 开始使用泛型类型之前，还没有原始类型*(非参数化的类型)*的替代品。出于向后兼容的原因，仍然可以定义这些:**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
public class Main {
    public static void main(String[] args)
    {
        // Defining a raw list, without specifying its type parameter
        List geeksList = new ArrayList();
        // Due to the unspecified type we can add any data type and the code will compile
        geeksList.add(100);
        geeksList.add(200);
        geeksList.add("GeeksForGeeks");
        // When the second element is reached the compiler will throw a runtime error
        // because we are trying to cast a string to an integer
        geeksList.forEach(k -> System.out.println((int)k * 2));
    }
}
```

```java
**Output : 200**
 **400**
**Exception in thread "main" java.lang.ClassCastException:** 
**java.base/java.lang.String cannot be cast to java.base/java.lang.Integer**
```

**可以通过定义列表的一般类型来防止这个问题:**

```java
**List geeksList = new ArrayList<string>();</string>**
```

**现在代码无法编译，因为我们试图向整数类型集合中添加一个字符串类型。泛型类型的创建是有原因的，可以防止程序员产生讨厌的错误和开销。**