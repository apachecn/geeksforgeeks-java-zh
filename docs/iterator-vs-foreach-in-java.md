# 迭代器 vs Java 中的 Foreach

> 原文:[https://www.geeksforgeeks.org/iterator-vs-foreach-in-java/](https://www.geeksforgeeks.org/iterator-vs-foreach-in-java/)

**后台:**
[**迭代器**](http://geeksquiz.com/how-to-use-iterator-in-java/) 是集合框架提供的一个接口，用于遍历集合以及对集合中的项目进行顺序访问。

```

   // Iterating over collection 'c' using iterator
   for (Iterator i = c.iterator(); i.hasNext(); ) 
       System.out.println(i.next());
```

[**对于每个**](https://www.geeksforgeeks.org/for-each-loop-in-java/) 循环，用于遍历集合中的项目。

```
   // Iterating over collection 'c' using **for-each** 
   for (Element e: c)
       System.out.println(e);
```

我们将每个 for 循环中使用的“:”理解为“in”。所以循环读为“对于元素中的每个元素 e”，这里的元素是存储元素类型项的集合。

**注意:**在使用 lambda 表达式的 Java 8 中，我们可以简单地用
替换每个循环

```
elements.forEach (e -> System.out.println(e) );
```

**两次遍历的区别**
在 for-每个循环中，我们不能修改集合，它会抛出一个[ConcurrentModificationException](https://docs.oracle.com/javase/7/docs/api/java/util/ConcurrentModificationException.html)另一方面用迭代器我们可以修改集合。

修改集合只是意味着移除元素或更改存储在集合中的项的内容。这是因为 for-每个循环隐式地创建一个迭代器，但是它不向用户公开，因此我们不能修改集合中的项目。

**什么时候使用哪个遍历？**

*   如果我们必须修改集合，我们可以使用迭代器。

*   使用嵌套循环时，最好使用 for-each 循环，为了更好地理解，请考虑下面的代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate working of nested iterators
// may not work as expected and throw exception.
import java.util.*;

public class Main
{
    public static void main(String args[])
    {
        // Create a link list which stores integer elements
        List<Integer> l = new LinkedList<Integer>();

        // Now add elements to the Link List
        l.add(2);
        l.add(3);
        l.add(4);

        // Make another Link List which stores integer elements
        List<Integer> s=new LinkedList<Integer>();
        s.add(7);
        s.add(8);
        s.add(9);

        // Iterator to iterate over a Link List
        for (Iterator<Integer> itr1=l.iterator(); itr1.hasNext(); )
        {
            for (Iterator<Integer> itr2=s.iterator(); itr2.hasNext(); )
            {
                if (itr1.next() < itr2.next())
                {
                    System.out.println(itr1.next());
                }
            }
        }
    }
}
```

输出:

```
Exception in thread "main" java.util.NoSuchElementException

    at java.util.LinkedList$ListItr.next(LinkedList.java:888)

    at Main.main(Main.java:29)
```

上面的代码抛出了 Java . util . nosuchelementexception .

在上面的代码中，我们一次又一次地为 itr1(即列表 l)调用 next()方法。现在我们正在推进迭代器，甚至没有检查它在集合中是否还有剩余的元素(在内部循环中)，因此我们推进迭代器的数量超过了集合中的元素数量，这导致了 NoSuchElementException。

for-each 循环是为嵌套循环量身定制的。用下面的代码替换迭代器代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate working of nested for-each
import java.util.*;
public class Main
{
    public static void main(String args[])
    {
        // Create a link list which stores integer elements
        List<Integer> l=new LinkedList<Integer>();

        // Now add elements to the Link List
        l.add(2);
        l.add(3);
        l.add(4);

        // Make another Link List which stores integer elements
        List<Integer> s=new LinkedList<Integer>();
        s.add(2);
        s.add(4);
        s.add(5);
        s.add(6);

        // Iterator to iterate over a Link List
        for (int a:l)
        {
            for (int b:s)
            {
                if (a<b)
                    System.out.print(a + " ");
            }
        }
    }
}
```

**输出:**

```
2 2 2 3 3 3 4 4
```

**业绩分析**

使用 for-each 循环或迭代器遍历集合会得到相同的性能。这里，我们所说的性能是指这两次遍历的时间复杂度。

如果您使用旧样式的 C 进行循环迭代，那么我们可能会大大增加时间复杂度。
//这里 l 是 List，可以是 ArrayList /LinkedList，n 是 List 的大小

```
for (i=0;i<n;i++)
   System.out.println(l.get(i));
```

这里，如果列表 l 是一个数组列表，那么我们可以在 O(1)时间内访问它，因为它被分配了连续的内存块(就像一个数组一样)，即随机访问是可能的。但是如果集合是 LinkedList，那么随机访问是不可能的，因为它没有被分配连续的内存块，所以为了访问一个元素，我们将不得不遍历链接列表，直到您到达所需的索引，因此在最坏的情况下访问一个元素所花费的时间将是 O(n)。

**对于没有随机访问的集合，迭代器和 for-each 循环比简单的 for 循环更快，而在允许随机访问的集合中，for-each 循环/for 循环/迭代器的性能没有变化。**

**相关文章:**
[Java 中的迭代器](https://www.geeksforgeeks.org/iterators-in-java/)
[从 Java 中的集合中检索元素(For-each、Iterator、list Iterator&EnumerationIterator)](https://www.geeksforgeeks.org/retrieving-elements-from-collection-for-each-iterator-listiterator-enumerationiterator/)
**参考文献:**
[https://docs . Oracle . com/javase/8/docs/technotes/guides/language/foreach . html](https://docs.oracle.com/javase/8/docs/technotes/guides/language/foreach.html)
T15】https://docs . Oracle . com/javase/7/docs/docs

本文由 **Chirag Agarwal** 供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论