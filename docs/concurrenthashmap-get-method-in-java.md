# Java 中的 ConcurrentHashMap get()方法

> 原文:[https://www . geesforgeks . org/concurrenthashmap-get-method-in-Java/](https://www.geeksforgeeks.org/concurrenthashmap-get-method-in-java/)

[java . util . concurrenthashmap](https://www.geeksforgeeks.org/concurrenthashmap-in-java/)的 **get()** 方法是 Java 中的一个内置函数，它接受一个键作为参数，并返回映射到它的值。如果作为参数传递的键不存在映射，则返回 null。

**语法:**

```
Concurrent.get(Object key_element)
```

**参数:**该方法接受对象类型的单个参数 **key_element** ，该参数是指其关联值应该被返回的键。

**返回值:**该方法返回与参数中**键 _ 元素**相关联的值。

**异常:**当指定的 **key_element** 为空时，函数抛出 **NullPointerException** 。

下面的程序说明了**Java . util . concurrent . concurrenthashmap . get()**方法的使用:

**程序 1:** 该程序涉及将字符串值映射到整数键。

```
// Java Program Demonstrate get()
// method of ConcurrentHashMap

import java.util.concurrent.*;

class GFG {
    public static void main(String[] args)
    {

        ConcurrentHashMap<Integer, String>
            chm = new ConcurrentHashMap<Integer, String>();

        chm.put(100, "Geeks");
        chm.put(101, "for");
        chm.put(102, "Geeks");
        chm.put(103, "Contribute");

        // Displaying the HashMap
        System.out.println("The Mappings are: ");
        System.out.println(chm);

        // Display the value of 100
        System.out.println("The Value associated to "
                           + "100 is : " + chm.get(100));

        // Getting the value of 103
        System.out.println("The Value associated to "
                           + "103 is : " + chm.get(103));
    }
}
```

**输出:**

```
The Mappings are: 
{100=Geeks, 101=for, 102=Geeks, 103=Contribute}
The Value associated to 100 is : Geeks
The Value associated to 103 is : Contribute

```

**程序 2:** 该程序涉及将整数值映射到字符串键。

```
// Java Program Demonstrate get()
// method of ConcurrentHashMap

import java.util.concurrent.*;

class GFG {
    public static void main(String[] args)
    {

        ConcurrentHashMap<String, Integer>
            chm = new ConcurrentHashMap<String, Integer>();

        chm.put("Geeks", 100);
        chm.put("GFG", 10);
        chm.put("GeeksforGeeks", 25);
        chm.put("Contribute", 102);

        // Displaying the HashMap
        System.out.println("The Mappings are: ");
        System.out.println(chm);

        // Display the value of Geeks
        System.out.println("The Value associated to "
                           + "Geeks is : " + chm.get("Geeks"));

        // Getting the value of Contribute
        System.out.println("The Value associated to "
                           + "Contribute is : " + chm.get("Contribute"));
    }
}
```

**输出:**

```
The Mappings are: 
{GeeksforGeeks=25, Geeks=100, GFG=10, Contribute=102}
The Value associated to Geeks is : 100
The Value associated to Contribute is : 102

```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/util/concurrenthashmap . html # get()](https://docs.oracle.com/javase/7/docs/api/java/util/concurrent/ConcurrentHashMap.html#get(java.lang.Object))