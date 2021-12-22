# Java 中的抽象集合等于()方法，示例

> 原文:[https://www . geesforgeks . org/abstract set-equals-method-in-Java-with-examples/](https://www.geeksforgeeks.org/abstractset-equals-method-in-java-with-examples/)

**[Java AbstractSet](https://www.geeksforgeeks.org/abstractset-class-in-java-with-examples/)** 中的 **AbstractSet.equals()** 方法用于检查两个集合之间的相等性。它验证作为参数传递的一个集合的元素是否等于这个集合的元素。

**语法:**

```java
AbstractSet1.equals(*AbstractSet2*)
```

**参数:**该方法接受一个抽象集类型的参数*抽象集 2* ，并引用要与该抽象集进行等式检查的集。

**返回值:**如果两个对象集相等，则方法返回真，否则返回假。

下面的程序说明了 AbstractSet.equals()方法的工作原理:

**程序 1:**

```java
// Java code to illustrate the equals() method
import java.util.*;

public class Abstract_Set_Demo {
    public static void main(String[] args)
    {

        // Creating an empty AbstractSet
        AbstractSet<String>
            abstract_set1 = new HashSet<String>();
        AbstractSet<String>
            abstract_set2 = new HashSet<String>();

        // Adding elements to set
        abstract_set1.add("Geeks");
        abstract_set1.add("4");
        abstract_set1.add("Geeks");
        abstract_set1.add("Welcomes");
        abstract_set1.add("You");

        // Adding elements to set
        abstract_set2.add("Geeks");
        abstract_set2.add("4");
        abstract_set2.add("Geeks");
        abstract_set2.add("Welcomes");
        abstract_set2.add("You");

        // Displaying the first HashSet
        System.out.println("First Set: "
                           + abstract_set1);

        // Displaying the second HashSet
        System.out.println("Second Set: "
                           + abstract_set2);

        // Displaying the equality
        System.out.println("Equality: "
                           + abstract_set1
                                 .equals(abstract_set2));
    }
}
```

**Output:**

```java
First Set: [4, Geeks, You, Welcomes]
Second Set: [4, Geeks, You, Welcomes]
Equality: true

```

**程序 2:**

```java
// Java code to illustrate the equals() method
import java.util.*;

public class Abstract_Set_Demo {
    public static void main(String[] args)
    {

        // Creating an empty AbstractSet
        AbstractSet<String>
            abstract_set1 = new HashSet<String>();
        AbstractSet<String>
            abstract_set2 = new HashSet<String>();

        // Adding elements to set
        abstract_set1.add("Geeks");
        abstract_set1.add("4");
        abstract_set1.add("Geeks");
        abstract_set1.add("Welcomes");
        abstract_set1.add("You");

        // Adding elements to set
        abstract_set2.add("Geeks");
        abstract_set2.add("4");
        abstract_set2.add("Geeks");
        abstract_set2.add("Welcomes");
        abstract_set2.add("U");

        // Displaying the first HashSet
        System.out.println("First Set: "
                           + abstract_set1);

        // Displaying the second HashSet
        System.out.println("Second Set: "
                           + abstract_set2);

        // Displaying the equality
        System.out.println("Equality: "
                           + abstract_set1
                                 .equals(abstract_set2));
    }
}
```

**Output:**

```java
First Set: [4, Geeks, You, Welcomes]
Second Set: [4, U, Geeks, Welcomes]
Equality: false

```