# 如何在 Java 中迭代任意地图

> 原文:[https://www.geeksforgeeks.org/iterate-map-java/](https://www.geeksforgeeks.org/iterate-map-java/)

在 Java 中，迭代一张[地图](https://www.geeksforgeeks.org/map-interface-java-examples/)一般有五种**方式。在本文中，我们将讨论所有这些，并看看它们的优缺点。
首先，我们**不能**直接使用[迭代器](https://www.geeksforgeeks.org/iterators-in-java/)迭代地图，因为地图不是[集合。](https://www.geeksforgeeks.org/collections-in-java-2/)同样，在进一步深入之前，您必须稍微了解一下[地图。进入< K、V >](https://docs.oracle.com/javase/7/docs/api/java/util/Map.Entry.html) 界面。
由于 Java 中的所有地图都实现了 [Map](https://www.geeksforgeeks.org/map-interface-java-examples/) 接口，因此以下技术将适用于任何地图实现( [HashMap](https://www.geeksforgeeks.org/java-util-hashmap-in-java/) 、 [TreeMap](https://www.geeksforgeeks.org/hashmap-treemap-java/) 、 [LinkedHashMap](https://www.geeksforgeeks.org/linkedhashmap-class-java-examples/) 、 [Hashtable](https://www.geeksforgeeks.org/java-util-hashtable-class-java/) 等)。)**

****1。使用 For-Each 循环迭代 Map . entryset():**
*Map . entryset()*方法返回一个集合视图( *Set < Map。条目< K，V > >* )中包含的映射。所以我们可以使用[映射的 *getKey()* 和 *getValue()* 方法迭代键值对。条目< K，V >](https://docs.oracle.com/javase/7/docs/api/java/util/Map.Entry.html) 。这种方法是最常见的，如果循环中需要映射键和值，应该使用这种方法。下面是演示它的 java 程序。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to demonstrate iteration over
// Map.entrySet() entries using for-each loop

import java.util.Map;
import java.util.HashMap;

class IterationDemo
{
    public static void main(String[] arg)
    {
        Map<String,String> gfg = new HashMap<String,String>();

        // enter name/url pair
        gfg.put("GFG", "geeksforgeeks.org");
        gfg.put("Practice", "practice.geeksforgeeks.org");
        gfg.put("Code", "code.geeksforgeeks.org");
        gfg.put("Quiz", "quiz.geeksforgeeks.org");

        // using for-each loop for iteration over Map.entrySet()
        for (Map.Entry<String,String> entry : gfg.entrySet())
            System.out.println("Key = " + entry.getKey() +
                             ", Value = " + entry.getValue());
    }
}
```

****输出:****

```java
Key = Quiz, Value = quiz.geeksforgeeks.org
Key = Practice, Value = practice.geeksforgeeks.org
Key = GFG, Value = geeksforgeeks.org
Key = Code, Value = code.geeksforgeeks.org
```

****2。使用 keySet()和 values()方法迭代键或值**
*映射. keySet()* 方法返回包含在此映射中的键的集合视图，*映射. values()* 方法返回包含在此映射中的值的集合视图。因此，如果只需要映射中的键或值，可以使用 for-each 循环迭代键集或值。下面是演示它的 java 程序。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to demonstrate iteration over
// Map using keySet() and values() methods

import java.util.Map;
import java.util.HashMap;

class IterationDemo
{
    public static void main(String[] arg)
    {
        Map<String,String> gfg = new HashMap<String,String>();

        // enter name/url pair
        gfg.put("GFG", "geeksforgeeks.org");
        gfg.put("Practice", "practice.geeksforgeeks.org");
        gfg.put("Code", "code.geeksforgeeks.org");
        gfg.put("Quiz", "quiz.geeksforgeeks.org");

        // using keySet() for iteration over keys
        for (String name : gfg.keySet())
            System.out.println("key: " + name);

        // using values() for iteration over values
        for (String url : gfg.values())
            System.out.println("value: " + url);
    }
}
```

****输出:****

```java
key: Quiz
key: Practice
key: GFG
key: Code
value: quiz.geeksforgeeks.org
value: practice.geeksforgeeks.org
value: geeksforgeeks.org
value: code.geeksforgeeks.org
```

****3。使用迭代器在** [**地图上进行迭代。词条< K，V >**](https://docs.oracle.com/javase/7/docs/api/java/util/Map.Entry.html)
这个方法和第一个有些类似。在第一种方法中，我们对地图上的每个循环使用。条目< K，V >，但是这里我们使用[迭代器](https://www.geeksforgeeks.org/iterators-in-java/)。在地图上使用迭代器。条目< K，V >有它自己的优势，即我们可以通过调用*迭代器. remove()* 方法在迭代过程中从地图中移除条目。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to demonstrate iteration over
// Map using keySet() and values() methods

import java.util.Map;
import java.util.HashMap;
import java.util.Iterator;

class IterationDemo
{
    public static void main(String[] arg)
    {
        Map<String,String> gfg = new HashMap<String,String>();

        // enter name/url pair
        gfg.put("GFG", "geeksforgeeks.org");
        gfg.put("Practice", "practice.geeksforgeeks.org");
        gfg.put("Code", "code.geeksforgeeks.org");
        gfg.put("Quiz", "quiz.geeksforgeeks.org");

        // using iterators
        Iterator<Map.Entry<String, String>> itr = gfg.entrySet().iterator();

        while(itr.hasNext())
        {
             Map.Entry<String, String> entry = itr.next();
             System.out.println("Key = " + entry.getKey() +
                                 ", Value = " + entry.getValue());
        }
    }
}
```

****输出:****

```java
Key = Quiz, Value = quiz.geeksforgeeks.org
Key = Practice, Value = practice.geeksforgeeks.org
Key = GFG, Value = geeksforgeeks.org
Key = Code, Value = code.geeksforgeeks.org
```

****4。使用 forEach(action)方法:**
在 Java 8 中，可以使用 *Map.forEach(action)* 方法并使用 [lambda 表达式](https://www.geeksforgeeks.org/lambda-expressions-java-8/)来迭代地图。这项技术既干净又快速。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java code illustrating iteration
// over map using forEach(action) method

import java.util.Map;
import java.util.HashMap;

class IterationDemo
{
    public static void main(String[] arg)
    {
        Map<String,String> gfg = new HashMap<String,String>();

        // enter name/url pair
        gfg.put("GFG", "geeksforgeeks.org");
        gfg.put("Practice", "practice.geeksforgeeks.org");
        gfg.put("Code", "code.geeksforgeeks.org");
        gfg.put("Quiz", "quiz.geeksforgeeks.org");

        // forEach(action) method to iterate map
        gfg.forEach((k,v) -> System.out.println("Key = "
                + k + ", Value = " + v));

    }
}
```

****输出:****

```java
Key = Quiz, Value = quiz.geeksforgeeks.org
Key = Practice, Value = practice.geeksforgeeks.org
Key = GFG, Value = geeksforgeeks.org
Key = Code, Value = code.geeksforgeeks.org
```

****5。迭代键并搜索值(效率低下)**
这里我们首先循环键(使用 *Map.keySet()* 方法)，然后为每个键搜索值(使用 *Map.get(键)*方法)。这种方法在实践中并不使用，因为它非常慢且效率低下，因为通过键获取值可能很耗时。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java program to demonstrate iteration
// over keys and searching for values

import java.util.Map;
import java.util.HashMap;

class IterationDemo
{
    public static void main(String[] arg)
    {
        Map<String,String> gfg = new HashMap<String,String>();

        // enter name/url pair
        gfg.put("GFG", "geeksforgeeks.org");
        gfg.put("Practice", "practice.geeksforgeeks.org");
        gfg.put("Code", "code.geeksforgeeks.org");
        gfg.put("Quiz", "quiz.geeksforgeeks.org");

        // looping over keys
        for (String name : gfg.keySet())
        {
            // search  for value
            String url = gfg.get(name);
            System.out.println("Key = " + name + ", Value = " + url);
        }
    }
}
```

****输出:****

```java
Key = Quiz, Value = quiz.geeksforgeeks.org
Key = Practice, Value = practice.geeksforgeeks.org
Key = GFG, Value = geeksforgeeks.org
Key = Code, Value = code.geeksforgeeks.org
```

**参考文献:[斯塔科沃弗洛](https://stackoverflow.com/questions/46898/how-to-efficiently-iterate-over-each-entry-in-a-map)
本文由**高拉夫·米格拉尼和阿布舍克·维尔马**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。**