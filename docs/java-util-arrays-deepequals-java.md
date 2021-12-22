# Java 中的 Java.util.Arrays.deepEquals()

> 原文:[https://www . geesforgeks . org/Java-util-arrays-deep equals-Java/](https://www.geeksforgeeks.org/java-util-arrays-deepequals-java/)

Arrays.deepEquals()用于检查两个一维或多维数组的数组是否相等。它可以比较两个嵌套数组(即多维数组)，而不考虑其维度。

*   如果两个数组引用都为空，或者如果它们引用的数组包含相同数量的元素，并且两个数组中所有对应的元素对都是深度相等的，则这两个数组引用被认为是深度相等的。
*   Two possibly null elements e1 and e2 are deeply equal if any of the following conditions hold:
    *   e1 和 e2 都是对象引用类型的数组
    *   e1 和 e2 是相同基元类型的数组，Arrays.equals(e1，e2)的适当重载将返回 true。
    *   e1 == e2
    *   e1.equals(e2)将返回 true。

    请注意，该定义允许任何深度的空元素。

*   是[数组类](https://www.geeksforgeeks.org/array-class-in-java/)的一种方法

**语法:**

```java
public static boolean deepEquals(Object[] o1, Object[] o2)

o1 = First Array to test for Equality
o2 = Second Array to test for Equality

Returns true if two array are equal

```

```java
// Java program to demonstrate working of deepEquals.
import java.util.Arrays;
public class GFG {
public static void main(String[] args)
    {
        int a1[][] = { { 10, 20 },
                       { 40, 50 },
                       { 60, 70 } };

        int a2[][] = { { 30, 20 },
                       { 10, 0 },
                       { 60, 80 } };

        int a3[][] = { { 10, 20 },
                       { 40, 50 },
                       { 60, 70 } };
        System.out.println("Check if a1 is equal to a2 : "
                           + Arrays.deepEquals(a1, a2));

        System.out.println("Check if a2 is equal to a3 : "
                           + Arrays.deepEquals(a2, a3));

        System.out.println("Check if a1 is equal to a3 : "
                           + Arrays.deepEquals(a1, a3));
    }
}
```

输出:

```java
Check if a1 is equal to a2 : false
Check if a2 is equal to a3 : false
Check if a1 is equal to a3 : true

```

**我们甚至可以用 deepEquals()来测试用户定义类的 Object 数组的相等性。参考下面的例子**
我们应该覆盖[等于](https://www.geeksforgeeks.org/overriding-equals-method-in-java/)的方法来定义用户定义类中不同参数的相等性。

```java
// Java program to demonstrate working of deepEquals
// for arrays of user defined obj.
import java.util.Arrays;
public class GFG {
public static class Employee {

        int Eid;
        String Ename;

    public Employee(int Eid, String Ename)
        {
            this.Eid = Eid;
            this.Ename = Ename;
        }

        // Overriding the equals()
    public boolean equals(Object obj)
        {

            // type casting obj to Employee
            Employee s = (Employee)obj;
            return (this.Eid == s.Eid && this.Ename.equals(s.Ename));
        }
    } public static void main(String args[])
    {
        // Creating an array of objects of user defined class.
        Employee e1[][] = { { new Employee(10, "Geek1"),
                              new Employee(11, "Geek2") },
                            { new Employee(12, "Geek3"),
                              new Employee(13, "Geek4") } };

        Employee e2[][] = { { new Employee(10, "Geek1"),
                              new Employee(11, "Geek2") },
                            { new Employee(12, "Geek3"),
                              new Employee(13, "Geek4") } };

        Employee e3[][] = { { new Employee(12, "Geek2"),
                              new Employee(25, "Geek4") },
                            { new Employee(15, "Geek3"),
                              new Employee(30, "Geek1") } };

        System.out.println("Check if e1 is equal to e2 : "
                           + Arrays.deepEquals(e1, e2));

        System.out.println("Check if e2 is equal to e3 : "
                           + Arrays.deepEquals(e2, e3));

        System.out.println("Check if a1 is equal to a3 : "
                           + Arrays.deepEquals(e1, e3));
    }
}
```

输出:

```java
Check if e1 is equal to e2 : true
Check if e2 is equal to e3 : false
Check if a1 is equal to a3 : false

```

**Equals() vs deepEquals()**

虽然 [Arrays.equals()](https://www.geeksforgeeks.org/java-util-arrays-equals-java-examples/) 在一维数组上工作正常，但是它不能检查多维数组的相等性。
而 Arrays.deepEquals()对所有数组都有效，与维度无关。

**参考:**
[https://docs . Oracle . com/javase/8/docs/API/Java/util/arrays . html # deepEquals-Java . lang . object:A-Java . lang . object:A-](https://docs.oracle.com/javase/8/docs/api/java/util/Arrays.html#deepEquals-java.lang.Object:A-java.lang.Object:A-)

本文由 **Sumit Ghosh** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。