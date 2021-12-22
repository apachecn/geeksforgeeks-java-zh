# Java 中的 BigInteger compareTo()方法

> 原文:[https://www . geesforgeks . org/big integer-compare to-method-in-Java/](https://www.geeksforgeeks.org/biginteger-compareto-method-in-java/)

**Java . math . BigInteger . compare to(BigInteger 值)**方法将此 BigInteger 与作为参数传递的 BigInteger 进行比较。

**语法:**

```
public int compareTo(BigInteger val)
```

**参数:**该方法接受单个强制参数**值**，它是要与大整数对象进行比较的大整数。

**返回:**该方法返回以下内容:

*   **0** :如果这个 BigInteger 的值等于作为参数传递的 BigInteger 对象的值。
*   **1** :如果这个 BigInteger 的值大于作为参数传递的 BigInteger 对象的值。
*   **-1** :如果这个 BigInteger 的值小于作为参数传递的 BigInteger 对象的值。

**示例:**

```
Input: BigInteger1=2345, BigInteger2=7456
Output: -1
Explanation: BigInteger1.compareTo(BigInteger2)=-1.

Input: BigInteger1=9834, BigInteger2=7456
Output: 1
Explanation: BigInteger1.compareTo(BigInteger2)=1.

```

**示例 1:下面的程序说明了当两个 BigInteger 相等时 big integer 类的 compareTo()方法**

```
// Java program to demonstrate 
// compareTo() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {
        // Creating 2 BigInteger objects
        BigInteger b1, b2;

        b1 = new BigInteger("321456");
        b2 = new BigInteger("321456");

        // apply compareTo() method
        int comparevalue = b1.compareTo(b2);

        // print result
        if (comparevalue == 0) {

            System.out.println("BigInteger1 "
                               + b1 + " and BigInteger2 "
                               + b2 + " are equal");
        }
        else if (comparevalue == 1) {

            System.out.println("BigInteger1 " + b1 + " 
                is greater than BigInteger2 " + b2);
        }
        else {

            System.out.println("BigInteger1 " + b1 + " 
                is lesser than BigInteger2 " + b2);
        }
    }
}
```

**Output:**

```
BigInteger1 321456 and BigInteger2 321456 are equal

```

**例 2:当大整数 1 大于大整数 2 时**

```
// Java program to demonstrate 
// compareTo() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {
        // Creating 2 BigInteger objects
        BigInteger b1, b2;

        b1 = new BigInteger("654321");
        b2 = new BigInteger("321456");

        // apply compareTo() method
        int comparevalue = b1.compareTo(b2);

        // print result
        if (comparevalue == 0) {

            System.out.println("BigInteger1 " + b1 + " 
                and BigInteger2 " + b2 + " are equal");
        }
        else if (comparevalue == 1) {

            System.out.println("BigInteger1 " + b1 + "
                is greater than BigInteger2 " + b2);
        }
        else {

            System.out.println("BigInteger1 " + b1 + " 
                is lesser than BigInteger2 " + b2);
        }
    }
}
```

**Output:**

```
BigInteger1 654321 is greater than BigInteger2 321456

```

**例 3:当大整数 1 小于大整数 2 时**

```
// Java program to demonstrate 
// compareTo() method of BigInteger

import java.math.BigInteger;

public class GFG {

    public static void main(String[] args)
    {
        // Creating 2 BigInteger objects
        BigInteger b1, b2;

        b1 = new BigInteger("321456");
        b2 = new BigInteger("564321");

        // apply compareTo() method
        int comparevalue = b1.compareTo(b2);

        // print result
        if (comparevalue == 0) {

            System.out.println("BigInteger1 " + b1 + " 
                 and BigInteger2 " + b2 + " are equal");
        }
        else if (comparevalue == 1) {

            System.out.println("BigInteger1 " + b1 + " 
                  is greater than BigInteger2 " + b2);
        }
        else {

            System.out.println("BigInteger1 " + b1 + "
                 is lesser than BigInteger2 " + b2);
        }
    }
}
```

**Output:**

```
BigInteger1 321456 is lesser than BigInteger2 564321

```

**参考:**T2[大整数比较()文档](https://docs.oracle.com/javase/7/docs/api/java/math/BigInteger.html#compareTo(java.math.BigInteger))