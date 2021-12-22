# 用 Java 初始化 HashMap

> 原文:[https://www.geeksforgeeks.org/initialize-hashmap-in-java/](https://www.geeksforgeeks.org/initialize-hashmap-in-java/)

[HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java/) 是 java.util 包的一部分。HashMap 扩展了抽象类 AbstractMap，也提供了 Map 接口的不完整实现。它以(键、值)对的形式存储数据。
我们可以通过四种不同的方式使用构造函数初始化 HashMap:
**1。**
HashMap():初始容量 16，负载系数 0.75 的默认构造函数。
`HashMap hs=new HashMap();`

```java
// Java program to demonstrate simple initialization 
// of HashMap
import java.util.*;
public class GFG {
    public static void main(String args[])
    {
        HashMap<Integer, String> hm = new HashMap<Integer, String>();
        hm.put(1, "Ram");
        hm.put(2, "Shyam");
        hm.put(3, "Sita");
        System.out.println("Values " + hm);
    }
}
```

**Output:**

```java
Values {1=Ram, 2=Shyam, 3=Sita}

```

**2。**
HashMap(int initial capacity)用于在默认负载系数为 0.75 的情况下，创建具有指定初始容量的空 HashMap 对象。
`HashMap hs=new HashMap(10);`

```java
// Java program to demonstrate initialization 
// of HashMap with given capacity.
import java.util.*;
public class GFG {
    public static void main(String[] args)
    {
        HashMap<Integer, String> hm = new HashMap<Integer, String>(3);
        hm.put(1, "C");
        hm.put(2, "C++");
        hm.put(3, "Java");
        System.out.println("Values of hm" + hm);
    }
}
```

**Output:**

```java
Values of hm{1=C, 2=C++, 3=Java}

```