# 用示例在 Java 中编写 add()方法

> 原文:[https://www . geesforgeks . org/composite name-add-method-in-Java-with-examples/](https://www.geeksforgeeks.org/compositename-add-method-in-java-with-examples/)

一个 **javax.naming.CompositeName 类**的 **add()** 方法用于将组件添加到 CompositeName 对象中。
有两种不同的添加方法。

**1。add(int，String)** :此方法用于在指定位置添加单个组件 **posn** 作为参数在此复合名称中传递。出现在新组件的 posn 处或之后的这个复合名称对象的其他组件被上移一个位置以容纳新组件。

**语法:**

```
public Name add(int posn, String comp)
       throws InvalidNameException
```

**参数:**该方法接受:

*   **posn** 是添加新组件的索引，并且
*   **comp** 是要添加到复合名称对象中的新组件。

**返回值:**这个方法返回的是一个更新的复合名称，而不是一个新的。返回值不能为空。

**异常:**如果 posn 在指定范围之外并且 InvalidNameException 如果在指定位置添加 comp 将违反复合名称的语法，则此方法将引发**arrayindextofboundsexception**。

下面的程序说明了 CompositeName.add()方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// CompositeName.add()

import java.util.Properties;
import javax.naming.CompositeName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {

        // create composite name object
        CompositeName CompositeName1
            = new CompositeName(
                "1/2/3/4/5/6/7");

        // apply add() to add new component at posn 0
        CompositeName newCompositeName
            = (CompositeName)
                  CompositeName1.add(0, "000");

        // print value
        System.out.println(
            "Updated CompositeName Object: "
            + newCompositeName);
    }
}
```

**Output:**

```
Updated CompositeName Object: 000/1/2/3/4/5/6/7
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// CompositeName.add() method

import java.util.Properties;
import javax.naming.CompositeName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {

        // create composite name object
        CompositeName CompositeName1
            = new CompositeName(
                "c/e/d/v/a/b/z/y/x/f");

        // apply add() to add new component at posn 9
        CompositeName newCompositeName
            = (CompositeName)
                  CompositeName1.add(9, "zzzzz");

        // print value
        System.out.println(
            "Updated CompositeName Object: "
            + newCompositeName);
    }
}
```

**Output:**

```
Updated CompositeName Object: c/e/d/v/a/b/z/y/x/zzzzz/f
```

**2。add(String)** :此方法用于在此复合名称的末尾添加单个组件。

**语法:**

```
public Name add(String comp)
       throws InvalidNameException
```

**参数:**此方法接受 **comp** ，这是要添加到复合名称对象末尾的新组件。

**返回值:**这个方法返回的是一个更新的复合名称，而不是一个新的。返回值不能为空。

**异常:**如果在名称末尾添加 comp 会违反复合名称的语法，此方法将引发 **InvalidNameException** 。

下面的程序说明了 CompositeName.add()方法:

**程序 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// CompositeName.add()

import java.util.Properties;
import javax.naming.CompositeName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {

        // create composite name object
        CompositeName CompositeName1
            = new CompositeName(
                "a/b/c/d/e/f/g/h/i/j");

        // apply add() to add new component at end
        CompositeName newCompositeName
            = (CompositeName)
                  CompositeName1.add("k");

        // print value
        System.out.println(
            "Updated CompositeName Object: "
            + newCompositeName);
    }
}
```

**Output:**

```
Updated CompositeName Object: a/b/c/d/e/f/g/h/i/j/k
```

**程序 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// CompositeName.add() method

import java.util.Properties;
import javax.naming.CompositeName;
import javax.naming.InvalidNameException;

public class GFG {
    public static void main(String[] args)
        throws InvalidNameException
    {

        // create composite name object
        CompositeName CompositeName1
            = new CompositeName(
                "c/e/d/v/a/b/z/y/x/f");

        // apply add() to add new component at end
        CompositeName newCompositeName
            = (CompositeName)
                  CompositeName1.add("ppp");

        // print value
        System.out.println(
            "Updated CompositeName Object: "
            + newCompositeName);
    }
}
```

**Output:**

```
Updated CompositeName Object: c/e/d/v/a/b/z/y/x/f/ppp
```

**参考文献:**
[https://docs . Oracle . com/javase/10/docs/API/javax/naming/composite name . html # add(int，Java . lang . string)](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompositeName.html#add(int, java.lang.String))
[https://docs . Oracle . com/javase/10/docs/API/javax/naming/composite name . html # add(Java . lang . string)](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompositeName.html#add(java.lang.String))