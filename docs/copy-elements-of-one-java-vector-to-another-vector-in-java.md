# 在 Java 中将一个 Java 向量的元素复制到另一个向量中

> 原文:[https://www . geesforgeks . org/copy-elements-of-one-Java-vector-to-另一个-vector-in-java/](https://www.geeksforgeeks.org/copy-elements-of-one-java-vector-to-another-vector-in-java/)

[**【矢量】**](https://www.geeksforgeeks.org/java-util-vector-class-java/) 类似于数组，但也是可生长的，或者我们可以说不需要固定的大小。以前向量是遗留类的一部分，但现在它是集合的一部分。它还实现了一个列表接口，所以我们也可以在向量上使用列表接口的任何方法。

**语法:**

```java
*Vector<Integer> gfg=new Vector<>();*
```

**将一个向量的元素复制到另一个向量的方法:**

1.  传入构造函数
2.  使用 add()方法逐个添加

**方法 1:通过构造器**

*   在这种方法中，我们将简单地把一个向量传递给另一个向量的构造函数。
*   通过使用这种方法，如果我们改变第一个向量的值，那么它不会改变第二个向量的值。
*   这是复制向量值的最简单方法。

在下面的程序中，我们将，

*   首先，创建一个整数向量，并使用 add()方法向其中添加元素。
*   之后，我们将把第一个向量传递给第二个向量的构造函数。
*   现在，我们将更改一个值向量，并将检查另一个向量，以验证更改一个向量值是否不会影响另一个向量。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program for copying one Vector to another
// by passing in the constructor

import java.io.*;
import java.util.Vector;

class GFG {
    public static void main (String[] args) {

    // creation of Vector of Integers
    Vector<Integer> gfg=new Vector<>();

    // adding elements to  first Vector
    gfg.add(11);
    gfg.add(22);
    gfg.add(24);
    gfg.add(39);

    // passing in the constructor
    Vector<Integer> gfg2=new Vector<>(gfg);

    //Iterating over  second Vector
    System.out.println("-----Iterating over the second Vector----");

    for(Integer value: gfg2){
    System.out.println(value);
    }

    // here we changed the third element to 23
    // we changed in the second vector and you can
    // here we will not see the same change in the first
    gfg2.set(2,23);

    System.out.println("third element of first vector ="+gfg.get(2));
    System.out.println("third element of second vector ="+gfg2.get(2)); 

    }
}
```

**Output**

```java
-----Iterating over the second Vector----
11
22
24
39
third element of first vector =24
third element of second vector =23
```

**方法二:使用** [**逐一添加()**](https://www.geeksforgeeks.org/vector-add-method-in-java/) **方法**

*   在这种方法中，我们将迭代 Vector 的每个元素，并将该元素添加到第二个 Vector 中。
*   这里，如果你改变第一个向量元素，那么它不会改变第二个向量的元素。
*   这不是最好的方法，但它是一个简单的迭代过程。

在下面的程序中，我们将首先创建一个整数向量，并向其中添加元素，然后我们将对该向量进行迭代，并将每次迭代中的元素添加到另一个向量中。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program for  copying one Vector to another
// by adding elements one by one using add() method

import java.io.*;
import java.util.Vector;

class GFG {
    public static void main (String[] args) {

    // creation of Vector of Integers
    Vector<Integer> gfg=new Vector<>();

    // adding elements to  first Vector
    gfg.add(50);
    gfg.add(24);
    gfg.add(95);
    gfg.add(31);

    Vector<Integer> gfg2=new Vector<>();

    // adding element to the second Vector
    // by iterating over one by one
    for(Integer value: gfg){
    gfg2.add(value);
    }

    // Iterating over  second Vector
    System.out.println("-----Iterating over the second Vector----");

    for(Integer value :gfg2)
    {
      System.out.println(value);
    }

    // here we changed the third element to 23
    // we changed in second Vector
    // here we will not see the same change in the first
    gfg2.set(2,23);

    System.out.println("third element of first Vector ="+gfg.get(2));
    System.out.println("third element of second Vector ="+gfg2.get(2)); 

    }
}
```

**Output**

```java
-----Iterating over the second Vector----
50
24
95
31
third element of first Vector =95
third element of second Vector =23
```