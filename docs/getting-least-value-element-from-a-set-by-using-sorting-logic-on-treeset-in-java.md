# 在 Java 中使用树集合上的排序逻辑从集合中获取最小值元素

> 原文:[https://www . geeksforgeeks . org/通过使用 java 中的树集合上的排序逻辑从集合中获取最小值元素/](https://www.geeksforgeeks.org/getting-least-value-element-from-a-set-by-using-sorting-logic-on-treeset-in-java/)

为了获得用户定义对象的值元素，需要在 TreeSet 中实现排序逻辑。现在，为了在用户定义的对象上实现排序逻辑，需要通过 TreeSet 构造函数调用传递 Comparator 对象。此外，比较器实现将保存排序逻辑。为此，需要覆盖 [*【比较()】*](https://www.geeksforgeeks.org/how-compare-method-works-in-java/) 方法，以便在用户定义的对象上提供排序逻辑。最后，使用 [*优先()*](https://www.geeksforgeeks.org/treeset-first-method-in-java/) 方法提取出最少的元素。

**插图:**

```java
Input : Set: ["A"=36678 , "B"=456456 ,"C"=76434 ,"D"=4564]
Output: Least value => element: D, value: 4564

Input : Set: ["x"=1, "y"=2 ,"z"=3]
Output: Set: Least value =>element: x, value: 1
```

**接近**

获取最小值元素 TreeSet

1.  使用比较器对用户定义类的对象进行排序。
2.  实现覆盖 compare()方法的排序功能，以便按值对 TreeSet 进行排序。
3.  排序后，TreeSet 的第一个对象将是值最小的元素。

**实施:**

**示例**

## Java

```java
// Java program to find out the least value element
// in a TreeSet

// Importing java input output libraries
// Importing Comparator and TreeSet class
// from java.util package
import java.io.*;
import java.util.Comparator;
import java.util.TreeSet;

// Two auxiliary classes are required
// Class1- Sorting logic class invoking comparator
// Class2- Element class
// Class3 - Main class(Implementation class)

// Class1- Sorting logic where
// comparator holds the sorting logic
class MySort implements Comparator<Element> {

    @Override
    // Overriding
    // To provide the sorting logic to below created TreeSet
    // in main() method  using compare() method
    public int compare(Element e1, Element e2)
    {
        // Condition check
        // Comparing values of element
        if (e1.getvalue() > e2.getvalue()) {

            // If condition holds true
            return 1;
        }
        else {

            // If condition is false
            return -1;
        }
    }
}

// Class- 2
// key for TreeSet --> Name
class Element {

    // Member variables of this class
    private String name;
    private int value;

    // Constructor of this class
    public Element(String n, int s)
    {
        // Referring to same object
        // using this keyword
        this.name = n;
        this.value = s;
    }

    // key--> Name
    // Using name as a key for TreeSet
    public String getname() { return name; }

    // Return value for the given key(name)
    public int getvalue() { return value; }

    // Format in which output is returned
    public String toString()
    {
        return "element: " + this.name
            + ", value: " + this.value;
    }
}

// Main Class- Implementing sorting functionality
class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Implementing sorting functionality with TreeSet
        // by implementing Comparator and
        // calling (MySort) from TreeSet constructor

        // Creating an object of Treeset
        // where object type is Element
        TreeSet<Element> Tree
            = new TreeSet<Element>(new MySort());

        // Adding elements to adobe object of TreeSet
        // Custom inputs
        Tree.add(new Element("A", 36778));
        Tree.add(new Element("B", 456456));
        Tree.add(new Element("C", 76433));
        Tree.add(new Element("D", 4564));

        // Printing first element of above created TreeSet
        // which will be least value among all elements
        System.out.println("Least value =>" + Tree.first());
    }
}
```

**输出**

```java
Least value =>element: D, value: 4564
```