# Java 中的 ArrayList 和 LinkedList remove()方法，示例

> 原文:[https://www . geesforgeks . org/ArrayList-linked list-remove-methods-Java-examples/](https://www.geeksforgeeks.org/arraylist-linkedlist-remove-methods-java-examples/)

[Java 中的 List 接口](https://www.geeksforgeeks.org/list-interface-java-examples/)(由 [ArrayList](https://www.geeksforgeeks.org/arraylist-in-java/) 和 [LinkedList](https://www.geeksforgeeks.org/linked-list-in-java/) 实现)提供了两个版本的 remove 方法。
**布尔移除(Object obj) :**
它接受要移除的对象。如果找到并移除元素，则返回 true。如果要移除的元素不存在，则返回 false。

*   如果指定元素存在，则从给定列表中移除该元素的第一个匹配项。如果元素不存在，则给定的列表不会改变。
*   移除后，它会将后续元素(如果有)向左移动，并将它们的索引减少 1。

它抛出以下异常
class castexception–如果指定元素的类型与此集合不兼容
(可选)。
NullPointRexception–如果指定的元素为空，并且该集合不允许
空元素(可选)。
不支持操作例外–如果此集合不支持删除操作

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// A Java program to demonstrate working of list remove
// when Object to be removed is passed.
import java.util.*;

public class GFG
{
    public static void main(String[] args)
    {
        // Demonstrating remove on ArrayList
        List<String>  myAlist = new ArrayList<String>();
        myAlist.add("Geeks");
        myAlist.add("Practice");
        myAlist.add("Quiz");
        System.out.println("Original ArrayList : " + myAlist);
        myAlist.remove("Quiz");
        System.out.println("Modified ArrayList : " + myAlist);

        // Demonstrating remove on LinkedList
        List<String>  myLlist = new LinkedList<String>();
        myLlist.add("Geeks");
        myLlist.add("Practice");
        myLlist.add("Quiz");
        System.out.println("Original LinkedList : " + myLlist);
        myLlist.remove("Quiz");
        System.out.println("Modified LinkedList : " + myLlist);
    }
}
```

**Output**

```java
Original ArrayList : [Geeks, Practice, Quiz]
Modified ArrayList : [Geeks, Practice]
Original LinkedList : [Geeks, Practice, Quiz]
Modified LinkedList : [Geeks, Practice]
```

**对象移除(int index) :**
它移除给定索引处的元素。它返回被移除的对象。

*   移除后，它会将后续元素(如果有)向左移动，并将它们的索引减少 1。
*   如果列表中包含 int 类型，则在传递 int 时调用该方法(详见[本](https://www.geeksforgeeks.org/remove-element-arraylist-java/)

如果索引超出界限，它将引发 IndexOutOfBoundsException，

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// A Java program to demonstrate working of list remove
// when index is passed.
import java.util.*;

public class GFG
{
    public static void main(String[] args)
    {
        // Demonstrating remove on ArrayList
        List<String> myAlist = new ArrayList<String>();
        myAlist.add("Geeks");
        myAlist.add("Practice");
        myAlist.add("Quiz");
        System.out.println("Original ArrayList : " + myAlist);
        myAlist.remove("Quiz");
        System.out.println("Modified ArrayList : " + myAlist);

        // Demonstrating remove on LinkedList
        List<String> myLlist = new LinkedList<String>();
        myLlist.add("Geeks");
        myLlist.add("Practice");
        myLlist.add("Quiz");
        System.out.println("Original LinkedList : " + myLlist);
        myLlist.remove(2);
        System.out.println("Modified LinkedList : " + myLlist);
    }
}
```

**Output**

```java
Original ArrayList : [Geeks, Practice, Quiz]
Modified ArrayList : [Geeks, Practice]
Original LinkedList : [Geeks, Practice, Quiz]
Modified LinkedList : [Geeks, Practice]
```

**要点:**

*   请注意，由于数组的大小是固定的，因此没有直接的方法来移除数组中的元素。所以没有像 add()，remove()，delete()这样的方法。但是在像数组列表和哈希集这样的集合中，我们有这些方法。因此，当我们需要这些方法时，最好要么将数组转换为数组列表，要么首先使用数组列表。
*   迭代元素时不建议使用 list 接口的 remove()。这可能会导致[并发修改异常](https://docs.oracle.com/javase/7/docs/api/java/util/ConcurrentModificationException.html)(有关此异常的示例程序，请参考)。迭代元素时，建议使用 [Iterator.remove()](https://www.geeksforgeeks.org/iterators-in-java/) 方法。详见[本](https://www.geeksforgeeks.org/remove-element-arraylist-java/)。

本文由**莫希特·古普塔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。