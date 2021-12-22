# 使用 TreeSet 从数组中删除重复条目的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序-从数组中删除重复条目-使用-treeset/](https://www.geeksforgeeks.org/java-program-to-remove-duplicate-entries-from-an-array-using-treeset/)

[树集](https://www.geeksforgeeks.org/treeset-in-java-with-examples/)的特性是主要关注点，它广泛用于删除数据结构中的重复项，如下所示:

*   TreeSet 实现 [SortedSet](https://www.geeksforgeeks.org/sortedset-java-examples/) 界面。所以，重复的值是不允许的，并且将是剩余值。
*   树集中的对象以排序和升序存储。
*   TreeSet 不保留元素的插入顺序，但元素按键排序。
*   如果我们依赖于默认的自然排序顺序，那么插入到树中的对象应该是同类的和可比较的。TreeSet 不允许插入异构对象。如果我们试图添加异构对象，它会在运行时抛出 [classCastException](https://www.geeksforgeeks.org/built-exceptions-java-examples/) 。

**进场:** [加()法](https://www.geeksforgeeks.org/set-add-method-in-java-with-examples/)套

在 Java 中，它在上下文中用于将特定元素添加到集合中。只有当集合中没有指定的元素时，函数才会添加元素，否则，如果集合中已经有元素，函数将返回 False。

**语法:**

```java
boolean add(E element)

Where, E is the type of element maintained
by this Set collection.
```

**程序:**

1.  创建 TreeSet 的对象。
2.  使用 Add()方法将数组元素添加到 TreeSet 中。
3.  打印和显示数组中使用 add(element)方法复制的元素。
4.  从数组中删除重复项后，打印并显示数组中的元素。
5.  使用 size()方法获取 TreeSet 的大小。
6.  使用 [*到数组()*](https://www.geeksforgeeks.org/set-toarray-method-in-java-with-example/) 的转换方法将上述树集转换为数组。
7.  迭代数组元素。
8.  从字符串数组中删除重复条目后，打印并显示上面的字符串数组。

**实施:**

在下面的例子中，我们在稍后检查重复项时将数组的每个元素添加到树集中。最后，把 TreeSet 的所有元素放在 Array 中，把 Array 中所有剩余的空格放“null”，打印数组的元素。

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to remove duplicates entries
// from  an Array using TreeSet

// Importing Arrays and TreeSet class from
// java.util package
import java.util.Arrays;
import java.util.TreeSet;

// Class to remove duplicates
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Input custom entries in an array
        // String type
        // Custom inputs
        String[] input
            = new String[] { "Hello",   "hi",     "Wow",
                             "cute",    "thanks", "hi",
                             "Aww",     "cute",   "baby",
                             "beloved", "Aww" };

        // Converting Array to String and printing it
        System.out.print(
            "Initial String Array(Containing Duplicates) : "
            + (Arrays.toString(input)));

        // Creating an object of TreeSet
        TreeSet<String> dupliCheckr = new TreeSet<String>();

        // Adding array elements in TreeSet

        // For added elements in TreeSet
        for (String element : input) {

            // Displaying duplicate entries
            if (!dupliCheckr.add(element)) {

                // Print and display elements in an array
                // which are duplicated.
                System.out.println(
                    "Duplicate Data entered : " + element);
            }
        }

        // Next line
        System.out.println();

        // Print and display elements in an array
        // after removing duplicates from it.
        System.out.println(
            "TreeSet(After Removing Duplicates) : "
            + dupliCheckr);

        // Next line
        System.out.println();

        // Getting size of TreeSet using size() method
        int length = dupliCheckr.size();

        // Converting above TreeSet to arrays
        // Using toArray() method
        input = dupliCheckr.toArray(input);

        // Iterating over array elements
        for (int i = length; i < input.length; i++)
            input[i] = null;

        // Print and display above string array
        // after removing duplicate entries from it
        System.out.println("Final String Array is : "
                           + Arrays.toString(input));
    }
}
```

**Output**

```java
Initial String Array(Containing Duplicates) : [Hello, hi, Wow, cute, thanks, hi, Aww, cute, baby, beloved, Aww]Duplicate Data entered : hi
Duplicate Data entered : cute
Duplicate Data entered : Aww

TreeSet(After Removing Duplicates) : [Aww, Hello, Wow, baby, beloved, cute, hi, thanks]

Final String Array is : [Aww, Hello, Wow, baby, beloved, cute, hi, thanks, null, null, null]
```