# 通过使用 Java 中 TreeSet 上的排序逻辑从集合中获取最高和最低值元素

> 原文:[https://www . geeksforgeeks . org/通过使用 java 中的树集合上的排序逻辑从集合中获取最高值和最低值元素/](https://www.geeksforgeeks.org/getting-highest-and-lowest-value-element-from-a-set-by-using-sorting-logic-on-treeset-in-java/)

[Java 中的 TreeSet](https://www.geeksforgeeks.org/treeset-in-java-with-examples/) 实现了 Set Interface，使用红黑树存储值。我们使用 TreeSet 进行排序，因为默认情况下 TreeSet 中的元素以升序存储。一旦创建了树集，我们就可以从树集的最后一个元素获得最高元素值，从树集的第一个元素获得第一个元素值。我们必须首先传递[比较器](https://www.geeksforgeeks.org/comparator-interface-java/)对象和树集合声明。现在，我们可以简单地通过创建一个树集并添加元素，然后根据某个属性对元素进行排序，最后通过树集上的 [last()](https://www.geeksforgeeks.org/treeset-last-method-in-java/) 和 [first()](https://www.geeksforgeeks.org/sortedset-first-method-in-java/) 函数获得最高的元素。为了实现排序，我们必须覆盖[比较](https://www.geeksforgeeks.org/how-compare-method-works-in-java/)方法。树集声明将遵循下面给出的语法:

**语法**

```
TreeSet<Comparator> name = new TreeSet<Comparator>(new ComparatorClass());
```

**参数**

*   **名称:**创建的树集的名称
*   **比较器:**比较器 Objec **t**
*   **比较类():**用于实现排序函数(比较方法)的类

**返回:**我们可以添加值的树集

例如，我们想要创建一个包含某个组的名称和年龄的树集，我们想要找到年龄和价值最高、年龄和价值最低的人

**例 1:**

```
Input :
Name - "Ramesh" Age - 20
Name - "Suresh" Age - 48
Name - "Ankit" Age - 14
Name - "Madhav" Age - 78

Output :
Highest Age Person: Name : Madhav-- Age : 78
Lowest Age Person: Name : Ankit-- Age : 14
```

**例 2:**

```
Input :
Name - "Ramesh" Age - 20
Name - "Suresh" Age - 20
Name - "Ankit" Age - 78
Name - "Madhav" Age - 78

Output :
Highest Age Person: Name : Ankit-- Age : 78
Lowest Age Person: Name : Suresh-- Age : 14
```

**解释**

例如 1 所有的年龄都是不同的，所以最高和最低是根据年龄值来确定的。

例如，两个最高年龄值相同，因此树集中最后()的人名被赋予最高值，即“A”< ‘M’ so Ankit has the highest age whereas if the lowest age values are the same name at first() of treeset is given lowest value i.e  ‘S’ >“R”，因此苏雷什的年龄最低。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Getting Highest and Lowest Value 
// Element From a Set by Using Sorting 
// Logic on TreeSet in Java

import java.util.*;
import java.io.*;
import java.util.Comparator;
import java.util.TreeSet;

// Implement sorting class using comparator to sort
class sorting implements Comparator<ages> {

    // Override the Compare Method
    @Override
    public int compare(ages age1, ages age2) {
        if (age1.value() > age2.value()) {
            return 1;
        } else {
            return -1;
        }
    }
}

// Implement ages for getting name and age
class ages {
    private String name;
    private int age;

    public ages(String name, int a) {
        this.name = name;
        this.age = a;
    }

    public String Name() {
        return name;
    }

    public void NewName(String name) {
        this.name = name;
    }

    public int value() {
        return age;
    }

    public void NewAge(int age) {
        this.age = age;
    }

    // Convert to string output
    public String toString() {
        return "Name: " + this.name + "-- age: " + this.age;
    }
}

public class GFG {
    public static void main(String[] args) {
        // Create a TreeSet with Comporator Object
        TreeSet<ages> agetree = new TreeSet<ages>(new sorting());

        // Add elements in TreeSet
        agetree.add(new ages("Ramesh", 20));
        agetree.add(new ages("Suresh", 20));
        agetree.add(new ages("Ankit", 78));
        agetree.add(new ages("Madhav", 78));

        // Output Highest Value Element
        System.out.println("Highest Age Person: " + agetree.last());

        // Output Lowest Value Element
        System.out.println("Lowest Age Person: " + agetree.first());
    }
}
```

**Output**

```
Highest Age Person: Name: Ankit-- age: 78
Lowest Age Person: Name: Suresh-- age: 20
```