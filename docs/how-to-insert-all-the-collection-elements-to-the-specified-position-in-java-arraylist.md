# 如何将所有集合元素插入到 Java ArrayList 中的指定位置？

> 原文:[https://www . geesforgeks . org/如何将所有集合元素插入到指定的 java 数组列表位置/](https://www.geeksforgeeks.org/how-to-insert-all-the-collection-elements-to-the-specified-position-in-java-arraylist/)

可以使用 **java.util.ArrayList** 类中的 [Collection.addAll()](https://www.geeksforgeeks.org/collections-addall-method-in-java-with-examples/) 方法将元素插入到 ArrayList 中的集合元素指定位置。如果索引处存在任何元素，则该元素及其所有右侧元素都将移到右侧。这个方法接受两个参数第一个参数是我们要插入元素的索引，第二个参数是另一个集合的对象。如果成功插入元素，此方法返回布尔值 true，否则返回 false。

**addAll(集合 c) :** 这个方法将指定集合中的所有元素追加到这个列表的末尾，按照它们被指定集合的迭代器返回的顺序。如果在操作过程中修改了指定的集合，则此操作的行为是未定义的(意味着如果指定的集合是此列表，并且此列表是非空的，则此调用的行为是未定义的)。

**语法:**

> 公共布尔 addAll(int i，Collection c)；

**异常:**如果元素包含一个或多个空值，并且 c 不允许空元素，或者如果 c 或元素为空，则该方法抛出**空指针异常**

**异常:**这里有两种可能的异常。

1.  [索引超出边界异常](https://www.geeksforgeeks.org/understanding-array-indexoutofbounds-exception-in-java/):如果索引超出范围，则显示索引超出边界异常。
2.  [空指针异常](https://www.geeksforgeeks.org/null-pointer-exception-in-java/):如果指定的集合为空，则显示空指针异常。

**代码:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to insert Collection element at
// specified index

// Importing ArrayList class and Vector class
// of java.utill package
import java.util.ArrayList;
import java.util.Vector;

public class GFG {

  // Main driver method
    public static void main(String[] args)
    {

        // Create an ArrayList
        ArrayList<String> ArrList = new ArrayList<String>();

        // Adding elements in above ArrayList created
      // Custom inputs
        ArrList.add("Computer");
        ArrList.add("Science");
        ArrList.add("Portal");
        ArrList.add("GeeksforGeeks");

        // Display message
        System.out.print("The ArrayList is : ");

        // Display original ArrayList
        System.out.println(ArrList);

        // Creating a vector for elements
        Vector<String> vector = new Vector<String>();

        // Insert elements in vector
      // Custom inputs
        vector.add("x");
        vector.add("y");
        vector.add("z");

        // Note: Chosen index where added may vary as per
        // req Add vector element in arrayList at 1 index
        ArrList.addAll(1, vector);

        // Display arrayList after insert elements
        // at specific indexchosen above
        System.out.println(
            "List after addition of element at specific index : ");

        // Display List after adding element at specific
        // index
        System.out.println(ArrList);
    }
}
```

**Output**

```
The ArrayList is : [Computer, Science, Portal, GeeksforGeeks]
List after addition of element at specific index : 
[Computer, x, y, z, Science, Portal, GeeksforGeeks]

```

**Output**

```
The ArrayList is : [Computer, Science, Portal, GeeksforGeeks]
List after addition of element at specifc index : 
[Computer, x, y, z, Science, Portal, GeeksforGeeks]
```