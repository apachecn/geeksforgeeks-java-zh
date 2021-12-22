# 用 Java 清空数组列表的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-empty-an-ArrayList-in-Java/](https://www.geeksforgeeks.org/java-program-to-empty-an-arraylist-in-java/)

ArrayList 类是一个可调整大小的数组，存在于“java.util 包”中。在 Java 中，内置数组和数组列表的区别在于，数组的大小不能修改(即，如果您想在数组中添加/添加或删除元素，您必须创建一个新的数组。但是，可以在数组列表中添加/添加或删除元素，而不需要创建新的数组。

**接近:**

1.  采用 [*清()*](https://www.geeksforgeeks.org/list-clear-method-in-java-with-examples/) 法。
2.  使用 [*removeAll()*](https://www.geeksforgeeks.org/arraylist-removeall-method-in-java-with-examples/) 方法。

**方法 1:** 使用 clear()方法作为 Java 中 ArrayList 的 clear()方法，用于移除 ArrayList 中的所有元素。该调用返回后，数组列表将完全为空。

**语法:**

```
public void clear() ;
```

**参数:**清除功能不取参数

**返回值:**此方法不返回值。

**例外** : NA

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program  to empty an ArrayList in Java

// Illustrating clear function
import java.util.ArrayList;

public class GFG {

    // Main driver method
    public static void main(String[] arg)
    {

        // Create an empty array list
        // with an initial capacity of 4
        ArrayList<String> numbers
            = new ArrayList<String>(4);

        // Use add() method to add elements
        // in numbers ArrayList
        numbers.add("10");
        numbers.add("20");
        numbers.add("30");
        numbers.add("40");

        // Printing numbers ArrayList
        System.out.println("Numbers ArrayList : "
                           + numbers);

        // Finding size of numbers ArrayList
        int numbers_size = numbers.size();

        // Display message
        System.out.println("Numbers ArrayList consists of: "
                           + numbers_size + " elements");

        // Display Message to between changes made in
        // ArrayList

        // System.out.println("Performing clear operation by
        // using clear function");

        // Using clear function
        numbers.clear();

        int numbers_size_new = numbers.size();

        // Printing new ArrayList
        System.out.println(
            "Finally Numbers ArrayList consists of: "
            + numbers_size_new + " elements");
    }
}
```

**Output**

```
Numbers ArrayList : [10, 20, 30, 40]
Numbers ArrayList consists of 4 elements
Performing clear operation by using clear function
Finally Numbers ArrayList consists of 0 elements
```

**方法 2:** 使用 [*removeAll()*](https://www.geeksforgeeks.org/arraylist-removeall-method-in-java-with-examples/) 方法作为 ArrayList 类的此方法，用于从该列表中移除指定集合中包含的所有元素。

**语法:**

```
public boolean removeAll(Collection c) ;
```

**参数:**该方法将集合 c 作为包含要从该列表中移除的元素的参数。

**返回值:**如果该列表因调用而改变，则该方法返回真。

**异常:**如果此列表包含空元素，并且指定的集合不允许空元素(可选)，或者指定的集合为空，则此方法抛出 [*空指针异常*](https://www.geeksforgeeks.org/null-pointer-exception-in-java/) 。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program  to empty an ArrayList in Java
// Java code to illustrate removeAll function

// Importing ArrayList library
import java.util.ArrayList;

public class GFG {

    // Main driver method
    public static void main(String[] arg)
    {

        // Create an empty array list
        // with an initial capacity of 4
        ArrayList<String> numbers
            = new ArrayList<String>(4);

        // Using add() method to add elements in numbers
        // ArrayList
        numbers.add("10");
        numbers.add("20");
        numbers.add("30");
        numbers.add("40");

        // Printing numbers ArrayList
        System.out.println("Numbers ArrayList : "
                           + numbers);

        // Finding size of numbers ArrayList
        int numbers_size = numbers.size();

        // Display message
        System.out.println("Numbers ArrayList consists of "
                           + numbers_size + " elements");

        // Display Message
        System.out.println(
            "Performing clear operation by using clear function");

        // Using removeAll function
        numbers.removeAll(numbers);

        // Displaying final ArrayList count of elements
        int numbers_size_new = numbers.size();
        System.out.println(
            "Finally Numbers ArrayList consists of "
            + numbers_size_new + " elements");
    }
}
```

**Output**

```
Numbers ArrayList : [10, 20, 30, 40]
Numbers ArrayList consists of 4 elements
Performing clear operation by using clear function
Finally Numbers ArrayList consists of 0 elements
```