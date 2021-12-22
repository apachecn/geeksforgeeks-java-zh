# Java 中的 Collections.nCopies()

> 原文:[https://www.geeksforgeeks.org/collections-ncopies-java/](https://www.geeksforgeeks.org/collections-ncopies-java/)

**Collections.nCopies()** 的作用是返回一个包含给定对象的 n 个副本的不可变列表。如果我们想用给定对象的 n 个副本创建一个列表，这个函数会有所帮助。新分配的数据对象很小，即它包含对数据对象的单一引用。

**语法:**

```
public static <T> List<T> nCopies(int number, T object)

where, number is the number of copies
of object and object represents the 
element which will appear number times
in the returned list. T represents generic type. 

```

**异常:**如果*号*的值小于 0，该函数将抛出 **IllegalArgumentException** 。

**例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java code to show implementation
// of Collections.nCopies()
import java.util.*;

class GFG {

    // Driver code
    public static void main(String[] args)
    {

        // creating a list where first argument
        // represents the number of copies and
        // the second argument represents the
        // element to be copied for 'number' times
        // This will create 4 copies of the objects.
        List list = Collections.nCopies(4, "GeeksforGeeks");

        // Displaying the list returned
        System.out.println("The list returned is :");
        Iterator itr = list.iterator();
        while (itr.hasNext()) {
            System.out.print(itr.next() + " ");
        }
        System.out.println("\n");

        List list1 = Collections.nCopies(3, "GeeksQuiz");

        // Displaying the list returned
        System.out.println("The list returned is :");
        Iterator itr1 = list1.iterator();  
        while (itr1.hasNext()) {
            System.out.print(itr1.next() + " ");
        }
        System.out.print("\n");
    }
}
```

Output :

```
The list returned is :
GeeksforGeeks GeeksforGeeks GeeksforGeeks GeeksforGeeks 

The list returned is :
GeeksQuiz GeeksQuiz GeeksQuiz  

```