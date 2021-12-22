# 如何从 Java 树图中删除第一个条目或最后一个条目？

> 原文:[https://www . geesforgeks . org/如何从 java 树图中删除第一个条目或最后一个条目/](https://www.geeksforgeeks.org/how-to-remove-the-first-entry-or-last-entry-from-the-java-treemap/)

[**树形图**](https://www.geeksforgeeks.org/treemap-in-java/) 是[地图](https://www.geeksforgeeks.org/map-interface-java-examples/)界面的实现类。它允许根据关键字对对象进行排序，排序可以是自然排序，也可以使用比较器。插入顺序也不会保留在树形图中。

**语法:**

```
TreeMap<String,Integer> map = new TreeMap<>();
```

在下面的例子中，我们将创建一个树形图，并使用 put()方法在其中插入记录。当树图根据关键字对记录进行排序时，您可以看到输出是按从 a 到 z 的关键字排序的。为了迭代树图，我们使用关键字 Set()方法迭代树图的所有关键字，该方法给出了树图的所有关键字。

实施:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to remove the first entry
// or last entry from TreeMap
import java.io.*;
import java.util.TreeMap;
import java.util.Set;

class GFG {

    public static void main(String[] args)
    {

        // treemap with keys as string and
        // values of type integer
        TreeMap<String, Integer> gfg = new TreeMap<>();

        // adding values to treemap
        gfg.put("interviews", 97);
        gfg.put("fang", 86);
        gfg.put("competitive programming", 95);
        gfg.put("dsa", 99);
        gfg.put("java", 99);
        gfg.put("c++", 99);

        // iterating over the treemap
        for (String key : gfg.keySet()) {
            System.out.println(key + "," + gfg.get(key));
        }
    }
}
```

**Output**

```
c++,99
competitive programming,95
dsa,99
fang,86
interviews,97
java,99
```

**从树形图**中删除第一个和最后一个条目:

**1。使用 pollFirstEntry()和 pollLastEntry()方法:**

TreeMap 有两种方法可以删除第一个和最后一个条目。 [pollFirstEntry()](https://www.geeksforgeeks.org/java-util-treemap-pollfirstentry-polllastentry-java/) 删除第一个条目和最后一个条目，我们使用[pollFirstEntry()](https://www.geeksforgeeks.org/java-util-treemap-pollfirstentry-polllastentry-java/)。

**语法:**

```
mapObject.pollFirstEntry();
mapObject.pollLastEntry();
```

**返回类型:**两种方法的返回类型都是从地图中移除的条目对象。

首先，我们将创建一个树形图，并使用 put()方法在其中添加记录，然后打印每个循环使用的所有记录。对于打印，我们将使用我们可以使用 keySet()方法获得的所有密钥。现在我们将在 TreeMap 上使用 pollFirstEntry()和 pollLastEntry()来移除第一个和最后一个条目。删除第一个和最后一个条目后，我们将再次使用 for 循环遍历树图。

实施:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program remove the first entry
// or last entry from the TreeMap
import java.io.*;
import java.util.TreeMap;
import java.util.Set;

class GFG {
    public static void main(String[] args)
    {

        // treemap with keys as string and values of type
        // integer
        TreeMap<String, Integer> gfg = new TreeMap<>();

        // adding values to tree map
        gfg.put("Interviews", 97);
        gfg.put("fang", 86);
        gfg.put("competitive programming", 95);
        gfg.put("dsa", 99);
        gfg.put("java", 99);
        gfg.put("c++", 99);

        System.out.println(
            "-------before removing first and last entry-------");

        // iterating over the treemap in java
        for (String key : gfg.keySet()) {
            System.out.println(key + "," + gfg.get(key));
        }

        // removing and printing first entry
        System.out.println(
            "----printing the first removed entry----");

        System.out.println(gfg.pollFirstEntry());

        // removing and printing last entry
        System.out.println(
            "----printing the last removed entry");

        System.out.println(gfg.pollLastEntry());

        System.out.println(
            "-------after removing first and last entry-------");

        // iterating over the treemap
        for (String key : gfg.keySet()) {
            System.out.println(key + "," + gfg.get(key));
        }
    }
}
```

**Output**

```
-------before removing first and last entry-------
Interviews,97
c++,99
competitive programming,95
dsa,99
fang,86
java,99
----printing the first removed entry----
Interviews=97
----printing the last removed entry
java=99
-------after removing first and last entry-------
c++,99
competitive programming,95
dsa,99
fang,86
```

**2。使用** [**lastKey()和 first key()**](https://www.geeksforgeeks.org/treemap-lastkey-method-in-java/)T6:

**语法:**

```
map.remove(map.lastKey());
map.remove(map.firstKey());
```

**进场:**

首先，我们将创建树形图，并使用 put()方法在其中插入一条记录。现在，我们将打印每个循环使用的所有记录，输出将按照从 a 到 z 的键排序顺序。要删除第一个条目和最后一个条目，我们将使用 remove(key)方法。在 remove 方法中，我们需要将键作为参数传递。现在，如果我们以某种方式获得第一个和最后一个密钥，我们将能够删除第一个和最后一个条目。treemap 给了我们两个这样的方法，它们可以给我们第一个和最后一个键，即 firstKey()和 last key()，在获取这些键之后，我们将在 remove()方法中传递这些键，然后再次打印 TreeMap 中的值，用于每个循环。

实施:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to remove the first entry
// or last entry from the TreeMap
import java.io.*;
import java.util.TreeMap;
import java.util.Set;

class GFG {
    public static void main(String[] args)
    {

        // treemap with keys as string and values of type
        // integer
        TreeMap<String, Integer> gfg = new TreeMap<>();

        gfg.put("Interviews", 97);
        gfg.put("fang", 86);
        gfg.put("competitive programming", 95);
        gfg.put("dsa", 99);
        gfg.put("java", 99);
        gfg.put("c++", 99);

        // iterating over the treemap in java
        System.out.println(
            "-------before removing first and last entry-------");

        for (String key : gfg.keySet()) {
            System.out.println(key + "," + gfg.get(key));
        }

        // removing first entry through firstKey()
        gfg.remove(gfg.firstKey());

        // removing last entry through lastKey()
        gfg.remove(gfg.lastKey());

        System.out.println(
            "-------after removing first and last entry-------");

        // iterating over the treemap
        for (String key : gfg.keySet()) {
            System.out.println(key + "," + gfg.get(key));
        }
    }
}
```

**Output**

```
-------before removing first and last entry-------
Interviews,97
c++,99
competitive programming,95
dsa,99
fang,86
java,99
-------after removing first and last entry-------
c++,99
competitive programming,95
dsa,99
fang,86
```

**3。使用流():**

在这里，我们将使用 streams 获取第一个和最后一个密钥，然后对其调用 remove 方法。

**语法:**

```
firsrkey = map.entrySet().stream().findFirst().get()
treemap.remove(firstkey);

lastkey = map.entrySet().stream().skip(map.size()-1).findFirst().get()
treemap.remove(key);
```

**进场:**

在这里，我们将创建一个树形图，并使用 put()方法在其中添加记录，然后为每个循环打印每个记录。现在我们将使用流来获取第一个和最后一个密钥。对于第一个键，我们将使用 keySet()方法获得一组所有的键，然后我们将在其上使用流()，现在为了从流中获得第一个项(一条记录)，我们将在其上使用 findFirst()和 get()来获得第一个键，然后在 remove 方法中传递这个键来移除第一个条目(一条记录)。

对于最后一个键，我们将再次对所有键使用 keySet()，在它之后是 stream()，现在我们将跳过 n-1 个元素，因为如果我们跳过前 n-1 个记录，那么最终我们将到达最后一个记录。为了得到 n(总记录数或树形图的大小)，我们使用 size()方法。

实施:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program remove the first entry
// or last entry from the TreeMap
import java.io.*;
import java.util.TreeMap;
import java.util.Set;

class GFG {
    public static void main(String[] args)
    {

        // treemap with keys as string and values of type
        // integer
        TreeMap<String, Integer> gfg = new TreeMap<>();

        gfg.put("Interviews", 97);
        gfg.put("fang", 86);
        gfg.put("competitive programming", 95);
        gfg.put("dsa", 99);
        gfg.put("java", 99);
        gfg.put("c++", 99);

        // iterating over the treemap in java
        System.out.println(
            "-------before removing first and last entry-------");

        for (String key : gfg.keySet()) {
            System.out.println(key + "," + gfg.get(key));
        }

        // removing first entry through firstKey()
        String firstKey
            = gfg.keySet().stream().findFirst().get();
        gfg.remove(firstKey);

        // removing last entry through lastKey()
        String lastKey = gfg.keySet()
                             .stream()
                             .skip(gfg.size() - 1)
                             .findFirst()
                             .get();
        gfg.remove(lastKey);

        System.out.println(
            "-------after removing first and last entry-------");

        // iterating over the treemap
        for (String key : gfg.keySet()) {
            System.out.println(key + "," + gfg.get(key));
        }
    }
}
```

**Output**

```
-------before removing first and last entry-------
Interviews,97
c++,99
competitive programming,95
dsa,99
fang,86
java,99
-------after removing first and last entry-------
c++,99
competitive programming,95
dsa,99
fang,86
```