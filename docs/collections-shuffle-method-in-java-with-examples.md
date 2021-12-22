# Java 中的 Collections.shuffle()方法，示例

> 原文:[https://www . geesforgeks . org/collections-shuffle-in-Java-method-with-examples/](https://www.geeksforgeeks.org/collections-shuffle-method-in-java-with-examples/)

Collections 类的 shuffle()方法正如类名所示，存在于名为 ***java.util*** 的实用程序包中，用于对列表中的元素进行 shuffle。

有两种方式**可以在我们的程序中实现，如下所示:**

1.  使用预定义的随机性来源
2.  使用用户提供的随机性来源

**方式 1:** 使用预定义的随机性来源对给定列表进行洗牌。

**语法:**

```
public static void shuffle(List mylist)
```

**抛出异常:** [**如果给定列表或其列表迭代器不支持 set 操作，则抛出 UnsupportedOperationException**](https://www.geeksforgeeks.org/how-to-solve-java-list-unsupportedoperationexception/)。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// working of shuffle() method
// of Collections class

// Importing utility classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {
        // Creating an empty ArrayList of string type
        ArrayList<String> mylist = new ArrayList<String>();

        // Adding custom input elements to list object
        mylist.add("code");
        mylist.add("quiz");
        mylist.add("geeksforgeeks");
        mylist.add("quiz");
        mylist.add("practice");
        mylist.add("qa");

        // Printing list before shuffling
        System.out.println("Original List : \n" + mylist);

        // Shuffling the list
        Collections.shuffle(mylist);

        // Printing list after shuffling
        System.out.println("\nShuffled List : \n" + mylist);
    }
}
```

**Output**

```
Original List : 

Shuffled List : 

```

**方式 2:** 利用用户提供的随机性来源对给定列表进行洗牌。

这里提供了一个附加参数，上面指定的“*rndm”*是随机打乱列表的来源。

**语法:**

```
public static void shuffle(List mylist, Random rndm)
```

**参数:**这里取两个参数列为

*   目录
*   随机性来源

**异常:** *不支持操作异常*如果指定的列表或其列表迭代器不支持设置操作。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to demonstrate working of shuffle()
// with user provided source of randomness

// Importing required utility classes
import java.util.*;

// Main class
public class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Creating an empty ArrayList of string type
        ArrayList<String> mylist = new ArrayList<String>();

        // Adding custom input elements to above created
        // object
        mylist.add("code");
        mylist.add("quiz");
        mylist.add("geeksforgeeks");
        mylist.add("quiz");
        mylist.add("practice");
        mylist.add("qa");

        // Print and display the elements of List on console
        System.out.println("Original List : \n" + mylist);

        // Shuffling the given list
        // using Random() method
        Collections.shuffle(mylist, new Random());

        // Print the updated list on console
        System.out.println(
            "\nShuffled List with Random() : \n" + mylist);

        // Shuffling list by using Random(3)
        Collections.shuffle(mylist, new Random(3));

        // Print the updated list on console
        System.out.println(
            "\nShuffled List with Random(3) : \n" + mylist);

        // Again shuffling list by using Random(3)
        Collections.shuffle(mylist, new Random(5));

        System.out.println(
            "\nShuffled List with Random(5) : \n" + mylist);
    }
}
```

**Output**

```
Original List : 

Shuffled List with Random() : 
[quiz, practice, quiz, geeksforgeeks, qa, code]

Shuffled List with Random(3) : 

Shuffled List with Random(5) : 
[geeksforgeeks, qa, quiz, code, practice, quiz]
```

但是，在实施此方法之前，请务必记住以下所列的某些要点:如下所列****如下所列**【T8:******

*   ********内功:**此方法随机置换列表中的随机元素。******
*   ******运行时间:**以线性时间运行。****
*   ******对元素的访问:**

    *   它向后遍历列表，从最后一个元素到第二个元素，重复地将随机选择的元素交换到它的“当前位置”。
    *   此后，从列表中从第一个元素到当前位置(包括当前位置)的部分随机选择元素。**** 

> ******注意:**如果提供的列表没有实现 RandomAccess 接口，比如 LinkedList，并且很大，那么它首先将列表复制到一个数组中，然后对数组副本进行洗牌，最后将数组复制回列表中。这确保了时间保持线性。****

****本文由**莫希特·古普塔**供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。****