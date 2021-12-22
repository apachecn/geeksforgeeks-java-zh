# Java 8 中的 Java.util 接口拆分器

> 原文:[https://www . geesforgeks . org/Java-util-interface-spliterator-java8/](https://www.geeksforgeeks.org/java-util-interface-spliterator-java8/)

**先决条件:**[Java 中的迭代器](https://www.geeksforgeeks.org/iterators-in-java/)

像其他迭代器一样，Spliterators 用于遍历源的元素。信号源可以是[集合](https://www.geeksforgeeks.org/collections-in-java-2/)、[输入输出通道](https://docs.oracle.com/javase/7/docs/api/java/nio/channels/Channels.html)或[发生器功能](https://en.wikipedia.org/wiki/Generator_(computer_programming))。

*   除了顺序遍历之外，它还包含在 JDK 8 中，以支持高效的并行遍历(并行编程)。
*   但是，即使不使用并行执行，也可以使用 Spliterator。您可能希望这样做的一个原因是，它将 *hasNext* 和 *next* 操作组合成一个方法。

对于集合，可以通过调用集合接口中的 spliterator()方法来创建 Spliterator 对象。

```
// Here "c" is any Collection object. splitr is of
// type Spliterator interface and refers to "c"
Spliterator splitr = c.spliterator();

```

**拆分器界面定义 8 种方式:**

1.  **int 特性()**:返回这个拆分器及其元素的一组特性。结果来自 ORDED(0x 000000010)、DISTINCT(0x 000000001)、SCORED(0x 00000004)、SIZED(0x00000040)、NONULL(0x 00000100)、INCOMPLETE(0x 0000400)、COMPLETE(0x 00001000)、SUBSIDED(0x 00004000)。

    ```
    Syntax : 
    int characteristics()
    Parameters : 
    NA
    Returns :
    Returns the characteristics of the invoking spliterator,
    encoded into an integer.

    ```

2.  **long estimateSize( )** :返回需要迭代的元素个数的估计值，或者返回 long。MAX_VALUE 如果是无限的、未知的或太贵而无法计算。

    ```
    Syntax : 
    long estimateSize( )
    Parameters : 
    NA
    Returns :
    Estimates the number of elements left to iterate and
    returns the result. Returns Long.MAX_VALUE if the
    count cannot be obtained for any reason.

    ```

3.  **缺省长 getExactSizeIfKnown( )** :如果这个 Spliterator 是 Size，则返回 estimateSize()的便利方法，否则返回-1。

    ```
    Syntax : 
    default long getExactSizeIfKnown( )
    Parameters : 
    NA
    Returns :
    If the invoking spliterator is SIZED, returns the number of
    elements left to iterate. Returns –1 otherwise.

    ```

4.  **默认比较器<？超级测试>获取比较器()**:如果这个拆分器的源被一个比较器排序，返回那个比较器。如果源按自然顺序排序，则返回 null。否则，如果源未排序，将引发 IllegalStateException。

    ```
    Syntax : 
    default Comparator<? super T> getComparator( )
    Parameters : 
    NA
    Returns :
    Returns the comparator used by the invoking spliterator
    or null if natural ordering is used. 
    Throws:
    IllegalStateException - If the sequence is unordered, 
    IllegalStateException is thrown.

    ```

5.  **默认布尔哈斯特徵(int val)** :如果这个拆分器的特徵()包含所有给定的特徵，则返回 true。

    ```
    Syntax : 
    default boolean hasCharacteristics(int val)
    Parameters : 
    characteristics - the characteristics to check for
    Returns :
    Returns true if the invoking spliterator has the
    characteristics passed in val. Returns false otherwise.

    ```

6.  **布尔 tryAdvance(消费者<？超 T >动作)**:如果存在剩余元素，对其执行给定动作，返回 true 否则返回 false。如果此拆分器是有序的，则操作将在遇到顺序中的下一个元素上执行。该操作引发的异常被传递给调用方。

    ```
    Syntax : 
    boolean tryAdvance(Consumer<? super T> action) 
    Parameters : 
    action - The action
    Returns :
    Returns true if there is a next element. Returns false if no
    elements remain.
    Throws :
    NullPointerException - if the specified action is null

    ```

7.  **默认作废 forEachRemaining(消费者<？super T >动作)**:对每个剩余的元素执行给定的动作，在当前线程中按顺序执行，直到所有元素都被处理完或者动作抛出异常。如果此拆分器是有序的，操作将按遇到顺序执行。该操作引发的异常被传递给调用方。

    ```
    Syntax : 
    default void forEachRemaining(Consumer<? super T>action)
    Parameters : 
    action - The action
    Returns :
    NA
    Throws :
    NullPointerException - if the specified action is null

    ```

8.  **Spliterator<T> trySplit( )** : If possible, splits the invoking spliterator, returning a reference to a new spliterator for the partition. Otherwise, returns null. Thus, if successful, the original spliterator iterates over one portion of the sequence and the returned spliterator iterates over the other portion.

    ```
    Syntax : 
    Spliterator<T> trySplit( )
    Parameters : 
    NA
    Returns :
    a Spliterator covering some portion of the elements, 
    or null if this spliterator cannot be split

    ```

    下面的例子演示了拆分器的方法。

    ```
    // Java program to demonstrate
    // methods of Spliterator

    import java.util.ArrayList;
    import java.util.Spliterator;
    import java.util.stream.Stream;

    public class SpliteratorDemo 
    {
        public static void main(String[] args) 
        {
            // Create an array list for doubles.
            ArrayList<Integer> al = new ArrayList<>();

            // Add values to the array list.
            al.add(1);
            al.add(2);
            al.add(-3);
            al.add(-4);
            al.add(5);

            // Obtain a Stream to the array list.
            Stream<Integer> str = al.stream();

            // getting Spliterator object on al
            Spliterator<Integer> splitr1 = str.spliterator();

            // estimateSize method
            System.out.println("estimate size : " + splitr1.estimateSize());

            // getExactSizeIfKnown method
            System.out.println("exact size : " + splitr1.getExactSizeIfKnown());

            // hasCharacteristics and characteristics method
            System.out.println(splitr1.hasCharacteristics(splitr1.characteristics()));

            System.out.println("Content of arraylist :");
            // forEachRemaining method    
            splitr1.forEachRemaining((n) -> System.out.println(n));

            // Obtaining another  Stream to the array list.
            Stream<Integer> str1 = al.stream();
            splitr1 = str1.spliterator();

            // trySplit() method
            Spliterator<Integer> splitr2 = splitr1.trySplit();

            // If splitr1 could be split, use splitr2 first.
            if(splitr2 != null) {
            System.out.println("Output from splitr2: ");
            splitr2.forEachRemaining((n) -> System.out.println(n));
            }

            // Now, use the splitr
            System.out.println("\nOutput from splitr1: ");
            splitr1.forEachRemaining((n) -> System.out.println(n));

        }
    }
    ```

    输出:

    ```
    estimate size : 5
    exact size : 5
    true
    Content of arraylist :
    1
    2
    -3
    -4
    5
    Output from splitr2: 
    1
    2

    Output from splitr1: 
    -3
    -4
    5

    ```

**用于 tryadvance 方法的 Java 程序**

看看 *tryAdvance()* 法。它对下一个元素执行*操作*，然后推进迭代器。如下所示:

```
boolean tryAdvance(Consumer<? super T> action)

```

这里，*动作*指定在迭代中下一个元素上执行的动作，而 Consumer 是一个[功能接口](https://www.geeksforgeeks.org/functional-interfaces-java/)，它将动作应用于对象。这是一个在 *java.util.function* 中声明的通用函数接口。它只有一个抽象方法 *accept( )* ，这里显示的是
:

```
void accept(T objRef)

```

这里 T 是对象引用的类型。

为了实现我们的*动作*，我们必须实现接受方法。为了实现接受方法，这里我们使用[λ表达式](https://www.geeksforgeeks.org/lambda-expressions-java-8/)。这将从下面的例子中变得更加清楚。

**如何对集合使用 Spliterator**:对基本迭代任务使用 Spliterator 相当容易，只需调用 *tryAdvance( )* 直到返回 false 即可。

```
// Java program to demonstrate simple Spliterator
// using tryAdvance method

import java.util.ArrayList;
import java.util.Spliterator;

public class SpliteratorDemo 
{
    public static void main(String[] args) 
    {
        // Create an array list for doubles.
        ArrayList<Integer> al1 = new ArrayList<>();

        // Add values to the array list.
        al1.add(1);
        al1.add(2);
        al1.add(-3);
        al1.add(-4);
        al1.add(5);

        // Use tryAdvance() to display(action) contents of arraylist.

        System.out.print("Contents of arraylist:\n");

        // getting Spliterator object on al1
        Spliterator<Integer> splitr = al1.spliterator();

        // Use tryAdvance() to display(action) contents of arraylist.
        // Notice how lambda expression is used to implement accept method
        // of Consumer interface

        while(splitr.tryAdvance((n) -> System.out.println(n)));

        // Use tryAdvance() for getting absolute values(action) of contents of arraylist.

        // Create new list that contains absolute values.
        ArrayList<Integer> al2 = new ArrayList<>();

        splitr = al1.spliterator();

        // Here our action is to get absolute values
        // Notice how lambda expression is used to implement accept method
        // of Consumer interface
        while(splitr.tryAdvance((n) -> al2.add(Math.abs(n))));

        System.out.print("Absolute values of contents of arraylist:\n");

        // getting Spliterator object on al2
        splitr = al2.spliterator();

        while(splitr.tryAdvance((n) -> System.out.println(n)));

    }
}
```

输出:

```
Contents of arraylist:
1
2
-3
-4
5
Absolute values of contents of arraylist:
1
2
3
4
5

```

请注意，在上面的示例中，tryAdvance()如何将[迭代器](https://www.geeksforgeeks.org/iterators-in-java/)提供的 hasNext()和 Next()的目的合并到一个方法中。这提高了迭代过程的效率。

在某些情况下，您可能希望对每个元素共同执行一些操作，而不是一次执行一个操作。为了处理这种情况，Spliterator 提供了 forEachRemaining()方法，它通常用于涉及[流](https://www.geeksforgeeks.org/stream-in-java/)的情况。此方法对每个未处理的元素应用操作，然后返回。

本文由**高拉夫·米格拉尼**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。