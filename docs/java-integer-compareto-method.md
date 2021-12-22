# Java Integer compareTo()方法

> 原文:[https://www . geesforgeks . org/Java-integer-compare to-method/](https://www.geeksforgeeks.org/java-integer-compareto-method/)

java.lang 包的 Integer 类的 **compareTo()** 方法对两个 Integer 对象进行数值比较，如果这个 Integer 等于参数 Integer，则返回值 0；如果该整数在数值上小于参数整数，则该值小于 0；如果此整数在数字上大于参数整数(有符号比较)，则为大于 0 的值。

**语法:**

```
public int compareTo(Integer anotherInt)
Parameter :
anotherInt- : the Integer to be compared.
Return :
- This method returns the value 0 if this Integer is 
equal to the argument Integer; 
- a value less than 0 if this Integer is 
numerically less than the argument Integer; 
- and a value greater than 0 if this Integer is
numerically greater than the argument Integer
(signed comparison).

```

**示例:**展示**Java . lang . integer . compare To()**方法的工作。

```
// Java program to demonstrate working
// of java.lang.Integer.compareTo() method
import java.lang.Integer;

class Gfg {

    // driver code
    public static void main(String args[])
    {
        Integer a = new Integer(10);
        Integer b = new Integer(20);

        // as 10 less than 20, Output will be a value less than zero
        System.out.println(a.compareTo(b));

        Integer x = new Integer(30);
        Integer y = new Integer(30);

        // as 30 equals 30, Output will be zero
        System.out.println(x.compareTo(y));

        Integer w = new Integer(15);
        Integer z = new Integer(8);

        // as 15 is greater than 8, Output will be a value greater than zero
        System.out.println(w.compareTo(z));
    }
}
```

**输出:**

```
-1
0
1

```