# Java 中的 Java.util.Dictionary 类

> 原文:[https://www . geesforgeks . org/Java-util-dictionary-class-Java/](https://www.geeksforgeeks.org/java-util-dictionary-class-java/)

**util。字典**是一个抽象类，表示**键值**关系，工作方式类似于地图。给定一个键，您可以存储值，并在需要时使用它的键将值检索回来。因此，它是键值对的列表。

**申报**

```java
public abstract class Dictionary extends Object
```

**建造师:**
**【词典()**独家建造师。

**使用方法。词典类:**

**1。put(K 键，V 值):java.util.Dictionary.put(K 键，V 值)**向字典中添加键值对。

**语法:**

```java
public abstract V put(K key, V value)
Parameters : 
-> key
-> value
Return : 
key-value pair mapped in the dictionary
```

**2。elements():Java . util . dictionary . elements()**返回字典中的值表示。

**语法:**

```java
public abstract Enumeration elements()
Parameters : 
--------
Return : 
value enumeration in dictionary
```

**3。get(Object key):Java . util . dictionary . get(Object key)**返回与字典中的 argumented key 映射的值。

**语法:**

```java
public abstract V get(Object key)
Parameters : 
key - key whose mapped value we want
Return : 
value mapped with the argumented key
```

**4。isEmpty():Java . util . dictionary . isEmpty()**检查字典是否为空。

**语法:**

```java
public abstract boolean isEmpty()
Parameters : 
------
Return : 
true, if there is no key-value relation in the dictionary; else false
```

**5。keys():Java . util . dictionary . keys()**返回字典中的键表示。

**语法:**

```java
public abstract Enumeration keys()
Parameters : 
--------
Return : 
key enumeration in dictionary
```

**6。移除(对象键):java.util.Dictionary.remove(对象键)**移除用参数化键映射的键值对。

**语法:**

```java
public abstract V remove(Object key)
Parameters : 
key : key to be removed
Return : 
value mapped with the key
```

**7。size():Java . util . Dictionary . size()**返回字典中键值对的个数。

**语法:**

```java
public abstract int size()
Parameters : 
-------
Return : 
returns the no. of key-value pairs in the Dictionary
```

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program explaining util.Dictionary class Methods
// put(), elements(), get(), isEmpty(), keys()
// remove(), size()

import java.util.*;
public class New_Class
{
    public static void main(String[] args)
    {

        // Initializing a Dictionary
        Dictionary geek = new Hashtable();

        // put() method
        geek.put("123", "Code");
        geek.put("456", "Program");

        // elements() method :
        for (Enumeration i = geek.elements(); i.hasMoreElements();)
        {
            System.out.println("Value in Dictionary : " + i.nextElement());
        }

        // get() method :
        System.out.println("\nValue at key = 6 : " + geek.get("6"));
        System.out.println("Value at key = 456 : " + geek.get("123"));

        // isEmpty() method :
        System.out.println("\nThere is no key-value pair : " + geek.isEmpty() + "\n");

        // keys() method :
        for (Enumeration k = geek.keys(); k.hasMoreElements();)
        {
            System.out.println("Keys in Dictionary : " + k.nextElement());
        }

        // remove() method :
        System.out.println("\nRemove : " + geek.remove("123"));
        System.out.println("Check the value of removed key : " + geek.get("123"));

        System.out.println("\nSize of Dictionary : " + geek.size());

    }
}
```

**输出:**

```java
Value in Dictionary : Code
Value in Dictionary : Program

Value at key = 6 : null
Value at key = 456 : Code

There is no key-value pair : false

Keys in Dictionary : 123
Keys in Dictionary : 456

Remove : Code
Check the value of removed key : null

Size of Dictionary : 1
```

本文由**莫希特·古普塔 _OMG 供稿😀**。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。