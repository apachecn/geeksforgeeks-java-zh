# 如何用 Java 打印包含自定义类对象的 LinkedHashMap？

> 原文:[https://www . geesforgeks . org/how-print-link edhashmap-包含自定义类对象的 java/](https://www.geeksforgeeks.org/how-to-print-linkedhashmap-containing-custom-class-objects-in-java/)

[链接散列表](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/)就像[散列表](https://www.geeksforgeeks.org/java-util-hashmap-in-java/)一样，有一个额外的特性，保持插入其中的元素的顺序。HashMap 提供了快速插入、搜索和删除的优势，但是它从来没有维护过 LinkedHashMap 提供的插入的轨迹和顺序，在那里元素可以按照它们的插入顺序被访问。

用 Java 打印包含自定义类对象的 LinkedHashMap 有两种方法:

*   使用[系统输出打印](https://www.geeksforgeeks.org/system-out-println-in-java/)
*   使用[条目](https://www.geeksforgeeks.org/map-entry-interface-java-example/)

**方法 1(使用 System.out.println()方法)**

打印 LinkedHashMap 最简单的方法是直接使用 System.out.println 方法，该方法使用 LinkedHashMap 类的 [toString](https://www.geeksforgeeks.org/arrays-tostring-in-java-with-examples/) 方法。从[抽象映射](https://www.geeksforgeeks.org/abstractmap-in-java/)类继承而来的 toString 方法返回映射的所有映射的字符串表示形式，用{ and }括起来，每个键值对用逗号分隔。但是，如果 LinkedHashMap 包含自定义类的对象作为键或值，Object 类的 toString 方法将打印类名，后跟@，后跟不可读的对象哈希代码。下面是实现:

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate how to print LinkedHashMap of
// custom class objects
import java.util.*;

// Custom class
class Triangle {

    private String type;

    // Constructor
    public Triangle(String type) { this.type = type; }
}

public class GFG {

    public static void main(String[] args)
    {

        // New LinkedHashMap of custom class Triangle
        LinkedHashMap<Integer, Triangle> map
            = new LinkedHashMap<Integer, Triangle>();

        // Add elements to LinkedHashMap
        map.put(1, new Triangle("Equilateral triangle"));
        map.put(2, new Triangle("Isosceles triangle"));
        map.put(3, new Triangle("Right angled triangle"));

        // Print map
        System.out.println(map);
    }
}
```

**Output**

```java
{1=Triangle@214c265e, 2=Triangle@448139f0, 3=Triangle@7cca494b}
```

但是我们可以通过在自定义类中重写 toString()方法以人类可读的形式打印它。下面是实现:

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate how to print LinkedHashMap of
// custom class objects
import java.util.*;

// Custom class
class Triangle {

    private String type;

    // Constructor
    public Triangle(String type) { this.type = type; }

    // Override toString method to print human readable
    // information about the object

    public String toString() { return this.type; }
}

public class GFG {

    public static void main(String[] args)
    {

        // New LinkedHashMap of custom class Triangle
        LinkedHashMap<Integer, Triangle> map
            = new LinkedHashMap<Integer, Triangle>();

        // Add elements to LinkedHashMap
        map.put(1, new Triangle("Equilateral triangle"));
        map.put(2, new Triangle("Isosceles triangle"));
        map.put(3, new Triangle("Right angled triangle"));

        // Print map
        System.out.println(map);
    }
}
```

**Output**

```java
{1=Equilateral triangle, 2=Isosceles triangle, 3=Right angled triangle}
```

**方法 2(使用地图。入口)**

我们可以使用 Entry 在 Java 中打印包含自定义类对象的 LinkedHashMap。下面是实现:

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate how to print LinkedHashMap of
// custom class objects
import java.util.*;

// Custom class
class Triangle {

    private String type;

    // Constructor
    public Triangle(String type) { this.type = type; }

    // Override toString method to print human readable
    // information about the object

    public String toString() { return this.type; }
}

public class GFG {

    public static void main(String[] args)
    {

        // New LinkedHashMap of custom class Triangle
        LinkedHashMap<Integer, Triangle> map
            = new LinkedHashMap<Integer, Triangle>();

        // Add elements to LinkedHashMap
        map.put(1, new Triangle("Equilateral triangle"));
        map.put(2, new Triangle("Isosceles triangle"));
        map.put(3, new Triangle("Right angled triangle"));

        // Print map using Entry
        for (Map.Entry<Integer, Triangle> entry :
             map.entrySet()) {
            System.out.println("Key: " + entry.getKey()
                               + ", Value: "
                               + entry.getValue());
        }
    }
}
```

**Output**

```java
Key: 1, Value: Equilateral triangle
Key: 2, Value: Isosceles triangle
Key: 3, Value: Right angled triangle
```