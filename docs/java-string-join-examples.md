# Java 字符串连接()带示例

> 原文:[https://www.geeksforgeeks.org/java-string-join-examples/](https://www.geeksforgeeks.org/java-string-join-examples/)

**java.lang.string.join()** 方法用分隔符连接给定的元素，并返回连接的字符串。请注意，如果元素为空，则添加空。从 JDK 1.8 开始，java 字符串中就包含了 **join()** 方法。
Java 字符串中有两种类型的 **join()** 方法。
**语法:**

```
public static String **join**(CharSequence deli, CharSequence... ele) 
and  
public static String join
(CharSequence deli, Iterable<? extends CharSequence> ele)     
Parameters:
deli- delimiter to be attached with each element 
ele- string or char to be attached with delimiter
Returns :  string joined with delimiter.

```

```
// Java program to demonstrate
// working of join() method

class Gfg1 {
    public static void main(String args[])
    {
        // delimiter is "<" and elements are "Four", "Five", "Six", "Seven"
        String gfg1 = String.join(" < ", "Four", "Five", "Six", "Seven");

        System.out.println(gfg1);
    }
}
```

**输出:**

```
Four < Five < Six < Seven

```

```
// Java program to demonstrate
// working of join() method

class Gfg2 {
    public static void main(String args[])
    {
        // delimiter is "  " and elements are "My",
        // "name", "is", "Niraj", "Pandey"
        String gfg2 = String.join("  ", "My", "name", "is", "Niraj", "Pandey");

        System.out.println(gfg2);
    }
}
```

**输出:**

```
My name is Niraj Pandey

```

```
// Java program to demonstrate
// working of join() method

class Gfg3 {
    public static void main(String args[])
    {
        // delimiter is "->" and elements are "Wake up", 
        // "Eat", "Play", "Sleep", "Wake up"

        String gfg3 = String.join("-> ", "Wake up", "Eat",
                      "Play", "Sleep", "Wake up");

        System.out.println(gfg3);
    }
}
```

**输出:**

```
Wake up-> Eat-> Play-> Sleep-> Wake up

```