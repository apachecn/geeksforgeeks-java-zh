# 如何使用比较器对数组列表进行排序？

> 原文:[https://www . geeksforgeeks . org/如何使用比较器对数组列表进行排序/](https://www.geeksforgeeks.org/how-to-sort-arraylist-using-comparator/)

[比较器](https://www.geeksforgeeks.org/comparator-interface-java/)是一个界面，用于排序重新排列[数组列表](https://www.geeksforgeeks.org/arraylist-in-java/)。比较器用于对用户定义对象的数组列表进行排序。在 java 中，比较器在 [java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)中提供。使用比较器，我们可以根据多个变量对数组列表进行排序。我们可以简单地实现比较器，而不影响原始的用户定义类。要使用比较器对数组列表进行排序，我们需要覆盖比较器接口提供的 compare()方法。重写 compare()方法后，我们需要调用 collections.sort()方法，如下所示。

**语法:**

```java
Collections.sort(list, comparator)
```

**参数:**

*   **列表:**根据比较器排序的列表。
*   **比较器:**比较器类实例

**返回:**它对列表进行排序，不返回任何内容。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Sort ArrayList using Comparator

import java.util.*;

// create the Shop class
class Shop {
    int ProductNo;
    String name;
    int stock;

    // constructor
    Shop(int ProductNo, String name, int stock)
    {
        this.ProductNo = ProductNo;
        this.name = name;
        this.stock = stock;
    }
}

// creates the comparator for comparing stock value
class StockComparator implements Comparator<Shop> {

    // override the compare() method
    public int compare(Shop s1, Shop s2)
    {
        if (s1.stock == s2.stock)
            return 0;
        else if (s1.stock > s2.stock)
            return 1;
        else
            return -1;
    }
}

class GFG {
    public static void main(String[] args)
    {
        // create the ArrayList object
        ArrayList<Shop> s = new ArrayList<Shop>();
        s.add(new Shop(218, "Pen", 520));
        s.add(new Shop(223, "Pencil", 213));
        s.add(new Shop(423, "Books", 101));
        s.add(new Shop(512, "Toy", 59));
        s.add(new Shop(723, "Bottle", 10));

        System.out.println("before sorting");
        for (Shop shop : s) {
            System.out.println(shop.stock + " " + shop.name
                               + " " + shop.ProductNo);
        }
        System.out.println();

        System.out.println(
            "After sorting(sorted by Stock)");

        // call the sort function
        Collections.sort(s, new StockComparator());
        for (Shop shop : s) {
            System.out.println(shop.stock + " " + shop.name
                               + " " + shop.ProductNo);
        }
    }
}
```

**Output**

```java
before sorting
520 Pen 218
213 Pencil 223
101 Books 423
59 Toy 512
10 Bottle 723

After sorting(sorted by Stock)
10 Bottle 723
59 Toy 512
101 Books 423
213 Pencil 223
520 Pen 218

```

在上面的例子中，我们按照可用库存数量对商店分类进行排序。我们也可以根据名称和产品编号进行排序。让我们根据名称对上面的数组列表进行排序。

**例 2**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to Sort ArrayList using Comparator

import java.util.*;

// create the Shop class
class Shop {

    int ProductNo;
    String name;
    int stock;

    // constructor
    Shop(int ProductNo, String name, int stock)
    {
        this.ProductNo = ProductNo;
        this.name = name;
        this.stock = stock;
    }
}

// creates the comparator for comparing name
class NameComparator implements Comparator<Shop> {

    // override the compare() method
    public int compare(Shop s1, Shop s2)
    {
        return s1.name.compareTo(s2.name);
    }
}

class GFG {
    public static void main(String[] args)
    {
        // create the ArrayList object
        ArrayList<Shop> s = new ArrayList<Shop>();
        s.add(new Shop(218, "Pen", 520));
        s.add(new Shop(223, "Pencil", 213));
        s.add(new Shop(423, "Books", 101));
        s.add(new Shop(512, "Toy", 59));
        s.add(new Shop(723, "Bottle", 10));

        System.out.println("before sorting");
        for (Shop shop : s) {
            System.out.println(shop.name + " " + shop.stock
                               + " " + shop.ProductNo);
        }
        System.out.println();

        System.out.println("After sorting(sorted by Name)");

        // call the sort function
        Collections.sort(s, new NameComparator());
        for (Shop shop : s) {
            System.out.println(shop.name + " " + shop.stock
                               + " " + shop.ProductNo);
        }
    }
}
```

**Output**

```java
before sorting
Pen 520 218
Pencil 213 223
Books 101 423
Toy 59 512
Bottle 10 723

After sorting(sorted by Name)
Books 101 423
Bottle 10 723
Pen 520 218
Pencil 213 223
Toy 59 512

```