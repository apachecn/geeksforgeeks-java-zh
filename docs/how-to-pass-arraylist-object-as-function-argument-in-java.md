# 如何在 java 中将 ArrayList 对象作为函数参数传递？

> 原文:[https://www . geesforgeks . org/how-pass-ArrayList-object-as-function-argument-in-Java/](https://www.geeksforgeeks.org/how-to-pass-arraylist-object-as-function-argument-in-java/)

[Java 中的 ArrayList](https://www.geeksforgeeks.org/arraylist-in-java/) 类基本上是一个可调整大小的数组，也就是说，它可以根据我们在其中添加或移除的值动态地增长和收缩大小。它存在于 [java.util 包](https://www.geeksforgeeks.org/java-util-package-java/)中。如果我们想将数组列表作为一个参数传递给一个函数，那么我们可以使用下面提到的语法轻松实现。

**示例:**

```java
ArrayList<Integer> list = new ArrayList<>();
modifyList(list);
public static void modifyList(ArrayList<Integer> list){
       list.add(69);
       list.add(98);
}
```

在上面的代码中，我们创建了一个名为“List”的 ArrayList 对象，然后将它传递给一个名为 modifyList 的函数。我们对此列表所做的更改(即我们添加到列表中的值)将出现在主函数内部的原始列表中。之所以会发生这种情况，是因为 java 中的**对象引用是通过值**传递的，因为[**java 严格地说是通过值**](https://www.geeksforgeeks.org/g-fact-31-java-is-strictly-pass-by-value/) 。

问题陈述的实施:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to pass an
// ArrayList as an argument

import java.util.*;

public class GFG {

    public static void main(String[] args)
    {
        // Creating an ArrayList Object of Integer type
        ArrayList<Integer> list = new ArrayList<>();

        // Inserting some Integer values in ArrayList
        list.add(3);
        list.add(57);
        list.add(7);

        // list after insertions : [3, 57, 7]
        // Displaying the ArrayList
        System.out.print("ArrayList after insertions: ");
        display(list);

        // Passing the ArrayList as an argument for
        // modification The modifications done to the list
        // inside the function will appear inside the
        // original ArrayList inside main()
        modifyList(list);

        // list after modifications : [3, 57, 7, 20, 98]
        // displaying the ArrayList after modifications
        System.out.print("ArrayList after modifications: ");
        display(list);
    }

    // Function to modify the arrayList
    public static void
    modifyList(ArrayList<Integer> parameterList)
    {
        parameterList.add(20);
        parameterList.add(98);
    }

    // Function to display the array List
    public static void display(ArrayList<Integer> list)
    {
        System.out.println(list);
    }
}
```

**Output**

```java
ArrayList after insertions: [3, 57, 7]
ArrayList after modifications: [3, 57, 7, 20, 98]

```

【Java 是如何通过值传递的？

假设我们在主函数中创建的数组列表对象指向地址 1000。当我们将这个对象传递给 modifyList 函数时，地址 1000 被传递给它，对象“parameterList”也开始指向内存中与“List”相同的位置，这就是为什么我们说对象引用在 java 中是通过值传递的。之后，当我们修改“参数列表”时，原来的“列表”也做了同样的修改。这个概念与我们在 C++中将指针变量作为参数传递时发生的情况非常相似。

```java
ArrayList<Integer> list = new ArrayList<>();
callByValue(list);
public static void callByValue(ArrayList<Integer> parameterList){
       parameterList = new ArrayList<>();
       parameterList.add(88);
       parameterList.add(200);
       parameterList.add(89);
}
```

在上面的代码中，当我们将列表传递给 callByValue 函数时，“parameterList”开始指向内存地址，即 1000。但是当我们创建了一个数组列表的新实例，并让“参数列表”指向它时，“参数列表”就开始指向一个新的内存地址(比如说)2000。在此函数中对数组列表所做的更改将不再影响内存地址为 1000 的数组列表。因此，主函数中的“列表”不受影响。

下面是问题陈述的实现:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to pass an
// ArrayList as an argument

import java.util.ArrayList;

public class GFG {

    public static void main(String[] args)
    {

        // Creating an ArrayList Object of Integer type
        ArrayList<Integer> list = new ArrayList<>();
        // Inserting some Integer values in ArrayList
        list.add(3);
        list.add(57);
        list.add(7);

        // list after insertions : [3, 57, 7]

        // Displaying the ArrayList
        System.out.print("ArrayList after insertions: ");
        display(list);

        // The changes made to the ArrayList inside this
        // function will not affect the original ArrayList
        // that we pass to it as we are simply creating the
        // new instance of ArrayList and making our
        // parameterList point to it
        callByValue(list);

        // list after function call : [3, 57, 7]

        // displaying the ArrayList after calling
        // callByValue
        System.out.print(
            "ArrayList after the function call: ");
        display(list);
    }

    public static void
    callByValue(ArrayList<Integer> parameterList)
    {

        // Creating a new instance of ArrayList
        parameterList = new ArrayList<>();

        // Inserting Integer values to the new ArrayList
        // created inside the function
        parameterList.add(88);
        parameterList.add(200);
        parameterList.add(89);

        // Displaying our new ArrayList
        System.out.print(
            "New ArrayList inside the function: ");
        display(parameterList);
    }

    // Function to display the array List
    public static void display(ArrayList<Integer> list)
    {
        System.out.println(list);
    }
}
```

**Output**

```java
ArrayList after insertions: [3, 57, 7]
New ArrayList inside the function: [88, 200, 89]
ArrayList after the function call: [3, 57, 7]

```