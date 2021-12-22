# 在 Java 中将一个数组列表的元素复制到另一个数组列表中

> 原文:[https://www . geesforgeks . org/copy-elements-of-one-ArrayList-to-other-ArrayList-in-Java/](https://www.geeksforgeeks.org/copy-elements-of-one-arraylist-to-another-arraylist-in-java/)

它是列表接口的实现类。它允许复制对象/元素，并保持插入顺序。您可以通过数组列表的索引来获取数组列表中的元素，现在您需要将它传递给 get(index)方法。您可以使用 add()方法将元素添加到 ArrayList 中。

**数组列表初始化语法:**

```
ArrayList<Integer> gfg=new ArrayList<>();
```

**将一个数组列表的元素复制到另一个数组列表**

有两种方法:首先，您实际上只需要将一个数组列表的引用传递给另一个，在这种情况下，如果您更改了一个数组列表的值或元素，那么您可以在其他数组列表中看到相同的更改。第二种方法是您将创建实际的副本，这意味着如果您在一个数组列表元素中进行更改，它将不会反映在另一个数组列表元素中。

**方法 1:使用赋值运算符(=)**

在这种方法中，我们将简单地将第一个数组列表引用分配给第二个，但是这里有一个重要的方面需要注意，我们没有创建新的对象，我们只是将第二个数组列表指向第一个。因此，如果您在第一个数组列表中进行更改，它也会反映在第二个数组列表中，因为您使用的是同一个对象。我们也可以改变一个数组列表的一个值，并且可以在另一个中寻找相同的值，不管它是否被改变。

**语法:**

```
ArrayList<Integer> gfg=new ArrayList<>();
ArrayList<Integer> gfg2=gfg;
```

下面是上述问题陈述的实现。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program for copying one ArrayList to another

import java.io.*;
import java.util.ArrayList;

class GFG {
    public static void main(String[] args)
    {
        // creation of ArrayList of Integers
        ArrayList<Integer> gfg = new ArrayList<>();

        // adding elements to  first ArrayList
        gfg.add(10);
        gfg.add(21);
        gfg.add(22);
        gfg.add(35);

        // Assigning the first reference to second
        ArrayList<Integer> gfg2 = gfg;

        // Iterating over  second ArrayList
        System.out.println(
            "-----Iterating over the second ArrayList----");
        for (Integer value : gfg2) {
            System.out.println(value);
        }

        // here we changed the third element to 23
        // we changed in second list and you can
        // see the same change in the first Arraylist
        gfg2.set(2, 23);

        System.out.println("third element of first list ="
                           + gfg.get(2));
        System.out.println("third element of second list ="
                           + gfg2.get(2));
    }
}
```

**Output**

```
-----Iterating over the second ArrayList----
10
21
22
35
third element of first list =23
third element of second list =23

```

**进场 2:通过施工方**

在这种方法中，我们将简单地在第二个数组列表的构造函数中传递第一个数组列表。通过使用这种方法，如果我们更改一个数组列表元素/值，它将不会影响另一个，所以这是我们实际创建副本的方法。我们也可以改变一个数组列表的一个值，并且可以在另一个中寻找相同的值，不管它是否被改变。

**语法:**

```
ArrayList<Integer> gfg=new ArrayList<>();
ArrayList<Integer> gfg2=new ArrayList<>(gfg);
```

以下是上述问题陈述的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program for  copying one ArrayList to another

import java.io.*;
import java.util.ArrayList;

class GFG {
    public static void main(String[] args)
    {
        // creation of ArrayList of Integers
        ArrayList<Integer> gfg = new ArrayList<>();

        // adding elements to  first ArrayList
        gfg.add(10);
        gfg.add(21);
        gfg.add(22);
        gfg.add(35);

        // passing in the constructor
        ArrayList<Integer> gfg2 = new ArrayList<>(gfg);

        // Iterating over  second ArrayList
        System.out.println(
            "-----Iterating over the second ArrayList----");
        for (Integer value : gfg2) {
            System.out.println(value);
        }

        // here we changed the third element to 23
        // we changed in second list and you can
        // here we will not see the same change in the first
        gfg2.set(2, 23);

        System.out.println("third element of first list ="
                           + gfg.get(2));
        System.out.println("third element of second list ="
                           + gfg2.get(2));
    }
}
```

**Output**

```
-----Iterating over the second ArrayList----
10
21
22
35
third element of first list =22
third element of second list =23

```

**方法三:使用 add()方法逐一添加**

在这种方法中，我们将遍历第一个数组列表的每个元素，并将该元素添加到第二个数组列表中。这里如果你改变第一个数组列表元素，它不会改变第二个数组列表的元素。我们也可以改变一个数组列表的一个值，并且可以在另一个中寻找相同的值，不管它是否被改变。

**语法:**

```
ArrayList<Integer> gfg=new ArrayList<>();
ArrayList<Integer> gfg2=new ArrayList<>();
for(Integer val: gfg){
gfg2.add(val);
}
```

以下是上述问题陈述的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program for  copying one ArrayList to another

import java.io.*;
import java.util.ArrayList;

class GFG {
    public static void main(String[] args)
    {
        // creation of ArrayList of Integers
        ArrayList<Integer> gfg = new ArrayList<>();

        // adding elements to  first ArrayList
        gfg.add(10);
        gfg.add(21);
        gfg.add(22);
        gfg.add(35);

        ArrayList<Integer> gfg2 = new ArrayList<>();

        // adding element to the second ArrayList
        // by iterating over one by one
        for (Integer value : gfg) {
            gfg2.add(value);
        }

        // Iterating over  second ArrayList
        System.out.println(
            "-----Iterating over the second ArrayList----");

        for (Integer value : gfg2) {
            System.out.println(value);
        }

        // here we changed the third element to 23
        // we changed in second list
        // here we will not see the same change in the first
        gfg2.set(2, 23);

        System.out.println("third element of first list ="
                           + gfg.get(2));
        System.out.println("third element of second list ="
                           + gfg2.get(2));
    }
}
```

**Output**

```
-----Iterating over the second ArrayList----
10
21
22
35
third element of first list =22
third element of second list =23

```