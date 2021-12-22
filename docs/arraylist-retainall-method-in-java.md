# Java 中的 ArrayList retainAll()方法

> 原文:[https://www . geesforgeks . org/ArrayList-retailnall-method-in-Java/](https://www.geeksforgeeks.org/arraylist-retainall-method-in-java/)

[**数组列表**](https://www.geeksforgeeks.org/arraylist-in-java/) 的**retainnal()**方法用于移除指定集合中未包含的所有数组列表元素，或者保留当前数组列表实例中所有匹配元素，这些元素匹配作为参数传递给该方法的集合列表中的所有元素。
**语法:**

```java
public boolean retainAll(Collection C)
```

**参数:***C*是包含要保留在列表中的元素的集合。
**返回值:**如果调用 else 导致列表发生变化，则该方法返回布尔值 true，否则返回 false。
**例外:**

1.  ClassCastException:如果此数组列表元素的类与传递的集合不兼容。这是可选的。
2.  NullPointerException:如果列表包含空元素，并且传递的集合不允许空元素，或者如果指定的集合为空。这也是可选的。

下面的程序用来说明 Java . util . ArrayList . retainnal()方法:
**程序 1:** 将 ArrayList 集合作为参数传递给方法。

```java
// Java code to illustrate retainAll() method
import java.util.ArrayList;
public class GFG {
    public static void main(String[] args)
    {
        // Creating an empty array list
        ArrayList<String> bags = new ArrayList<String>();

        // Add values in the bags list.
        bags.add("pen");
        bags.add("pencil");
        bags.add("paper");

        // Creating another array list
        ArrayList<String> boxes = new ArrayList<String>();

        // Add values in the boxes list.
        boxes.add("pen");
        boxes.add("paper");
        boxes.add("books");
        boxes.add("rubber");

        // Before Applying method print both lists
        System.out.println("Bags Contains :" + bags);
        System.out.println("Boxes Contains :" + boxes);

        // Apply retainAll() method to boxes passing bags as parameter
        boxes.retainAll(bags);

        // Displaying both the lists after operation
        System.out.println("\nAfter Applying retainAll()"+
        " method to Boxes\n");
        System.out.println("Bags Contains :" + bags);
        System.out.println("Boxes Contains :" + boxes);
    }
}
```

**Output:**

```java
Bags Contains :[pen, pencil, paper]
Boxes Contains :[pen, paper, books, rubber]

After Applying retainAll() method to Boxes

Bags Contains :[pen, pencil, paper]
Boxes Contains :[pen, paper]

```