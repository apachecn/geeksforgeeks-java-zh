# 如何在 Java 中比较两个数组？

> 原文:[https://www.geeksforgeeks.org/compare-two-arrays-java/](https://www.geeksforgeeks.org/compare-two-arrays-java/)

预测后续 Java 程序的输出。

```
class Test
{
    public static void main (String[] args) 
    {
        int arr1[] = {1, 2, 3};
        int arr2[] = {1, 2, 3};
        if (arr1 == arr2) // Same as arr1.equals(arr2)
            System.out.println("Same");
        else
            System.out.println("Not same");
    }
}
```

输出:

```
Not Same
```

在 Java 中，[数组是第一类对象](https://www.geeksforgeeks.org/g-fact-65/)。在上面的程序中，arr1 和 arr2 是对两个不同对象的两个引用。因此，当我们比较 arr1 和 arr2 时，会比较两个参考变量，因此我们得到的输出为“不相同”(更多示例参见[本](https://www.geeksforgeeks.org/final-arrays-in-java/))。

**如何比较数组内容？**
一个简单的方法是运行一个循环，逐个比较元素。Java 提供了一个直接的方法 *Arrays.equals()* 来比较两个数组。实际上，对于不同的基元类型(int、char，..一个用于对象类型(它是 Java 中所有类的基础)。

```
// we need to import java.util.Arrays to use Arrays.equals().
import java.util.Arrays;
class Test
{
    public static void main (String[] args) 
    {
        int arr1[] = {1, 2, 3};
        int arr2[] = {1, 2, 3};
        if (Arrays.equals(arr1, arr2))
            System.out.println("Same");
        else
            System.out.println("Not same");
    }
}
```

输出:

```
Same
```

**如何深度比较数组内容？**
如上所述，Arrays.equals()工作正常，可以比较数组内容。现在的问题是，如果数组内部包含数组或者引用不同对象但具有相同值的其他引用，该怎么办。例如，请参见以下程序。

```
import java.util.Arrays;
class Test
{
    public static void main (String[] args) 
    {
        // inarr1 and inarr2 have same values
        int inarr1[] = {1, 2, 3};
        int inarr2[] = {1, 2, 3};   
        Object[] arr1 = {inarr1};  // arr1 contains only one element
        Object[] arr2 = {inarr2};  // arr2 also contains only one element
        if (Arrays.equals(arr1, arr2))
            System.out.println("Same");
        else
            System.out.println("Not same");
    }
}
```

输出:

```
Not Same
```

所以 *Arrays.equals()* 是不能做深度比较的。Java 为这个 Arrays.deepEquals()提供了另一种方法，可以进行深度比较。

```
import java.util.Arrays;
class Test
{
    public static void main (String[] args) 
    {
        int inarr1[] = {1, 2, 3};
        int inarr2[] = {1, 2, 3}; 
        Object[] arr1 = {inarr1};  // arr1 contains only one element
        Object[] arr2 = {inarr2};  // arr2 also contains only one element
        if (Arrays.deepEquals(arr1, arr2))
            System.out.println("Same");
        else
            System.out.println("Not same");
    }
}
```

输出:

```
Same
```

【Arrays.deepEquals()是如何工作的？
它使用两个对象可能有的任何自定义 equals()方法来比较这两个对象(如果它们实现了一个 equals()方法而不是 Object.equals())。如果没有，这个方法将继续逐字段递归地比较对象。当遇到每个字段时，它将尝试使用派生的 equals()如果它存在的话，否则它将继续进一步递归。
这个方法在这样一个循环 Object 图上工作:A- > B- > C- > A .它有循环检测，所以任意两个对象都可以比较，永远不会进入一个无休止的循环(来源:[https://code.google.com/p/deep-equals/](https://code.google.com/p/deep-equals/))。

**练习:**预测以下程序的输出

```
import java.util.Arrays;
class Test
{
   public static void main (String[] args) 
   {
      int inarr1[] = {1, 2, 3};
      int inarr2[] = {1, 2, 3}; 
      Object[] arr1 = {inarr1};  // arr1 contains only one element
      Object[] arr2 = {inarr2};  // arr2 also contains only one element
      Object[] outarr1 = {arr1}; // outarr1 contains only one element
      Object[] outarr2 = {arr2}; // outarr2 also contains only one element        
      if (Arrays.deepEquals(outarr1, outarr2))
          System.out.println("Same");
      else
          System.out.println("Not same");
    }
}
```

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论