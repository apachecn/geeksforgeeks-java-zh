# Java 中的 Double.compareTo()方法，带示例

> 原文:[https://www . geeksforgeeks . org/double-compare to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/double-compareto-method-in-java-with-examples/)

**java . lang . Double . compare to()**是 Java 中的一个内置方法，用于对两个 Double 对象进行数值比较。如果该对象等于参数对象，则该方法返回 0；如果该对象的数值小于参数对象，则该方法返回小于 0 的值；如果该对象的数值大于参数对象，则该方法返回大于 0 的值。

**语法:**

```
public int compareTo(Object obj)

```

**参数:**该方法接受一个参数。
*obj*——被比较的对象。

**返回值:**函数可以返回三个值:

*   *等于 0:* 对象等于自变量对象
*   *小于 0:* 对象小于自变量对象
*   *大于 0:* 对象大于自变量对象

下面的程序说明了 java.lang.Double.compareTo()方法的工作原理:

**程序 1:** 当两个对象不同时。

```
// Java program to demonstrate
// of java.lang.Double.compareTo() method
import java.lang.Math;

class Gfg1 {

    // Driver code
    public static void main(String args[])
    {

        // When two objects are different
        Double obj1 = new Double(124);
        Double obj2 = new Double(167);
        int compareValue = obj1.compareTo(obj2);

        if (compareValue == 0)
            System.out.println("object1 and object2 are equal");
        else if (compareValue < 0)
            System.out.println("object1 is less than object2");
        else
            System.out.println("object1 is greater than object2");
    }
}
```

**Output:**

```
object1 is less than object2

```

**程序 2:** 不传递参数时。

```
// Java program to demonstrate
// of java.lang.Double.compareTo() method
import java.lang.Math;

class Gfg1 {

    // Driver code
    public static void main(String args[])
    {
        // When no argument is passed
        Double obj1 = new Double(124);
        Double obj2 = new Double(167);

        int compareValue = obj1.compareTo();

        if (compareValue == 0)
            System.out.println("object1 and object2 are equal");
        else if (compareValue < 0)
            System.out.println("object1 is less than object2");
        else
            System.out.println("object1 is greater than object2");
    }
}
```

**输出:**

```
prog.java:14: error: method compareTo in class Double 
cannot be applied to given types;
        int compareValue = obj1.compareTo();
                               ^
  required: Double
  found: no arguments
  reason: actual and formal argument lists differ in length
1 error

```

**程序 3:** 当对象以外的任何东西作为参数传递时。

```
// Java program to demonstrate
// of java.lang.Double.compareTo() method
import java.lang.Math;

class Gfg1 {

    // Driver code
    public static void main(String args[])
    {

        // When anything other than object
        // argument is passed
        Double obj1 = new Double(124);

        int compareValue = obj1.compareTo("gfg");

        if (compareValue == 0)
            System.out.println("object1 and object2 are equal");
        else if (compareValue < 0)
            System.out.println("object1 is less than object2");
        else
            System.out.println("object1 is greater than object2");
    }
}
```

输出:

```
prog.java:15: error: incompatible types: String cannot be converted to Double
        int compareValue = obj1.compareTo("gfg");
                                          ^
Note: Some messages have been simplified; recompile with 
-Xdiags:verbose to get full output
1 error

```