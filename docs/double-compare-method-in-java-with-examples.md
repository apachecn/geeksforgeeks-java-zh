# Java 中的双比较()方法，示例

> 原文:[https://www . geesforgeks . org/double-compare-in-method-in-Java-with-examples/](https://www.geeksforgeeks.org/double-compare-method-in-java-with-examples/)

[](https://www.geeksforgeeks.org/java-lang-double-class-in-java/)**的 **compare()** 方法是 Java 中的一个内置方法，用于比较两个指定的双精度值。返回的整数值的符号与函数调用返回的整数的符号相同。**

****语法:****

```java
public static int compare(double d1, double d2)
```

****参数:**该函数接受两个参数:**

*   ****d1** :要比较的第一个双数值。**
*   ****d2** :要比较的第二个双数值。**

****返回值:**函数返回值如下:**

*   ****0:** 如果 d1 在数值上等于 d2。**
*   ****负值:**如果 d1 数值小于 d2。**
*   ****正值:**如果 d1 在数值上大于 d2。**

**下面的程序说明了 Double.compare()函数的使用:**

****程序 1:** 当两个整数相同时**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java Program to illustrate
// the Double.compare() method

import java.lang.Double;

public class GFG {
    public static void main(String[] args)
    {

        // Get the two double values
        // to be compared
        Double d1 = 1023d;
        Double d2 = 1023d;

        // function call to compare two double values
        if (Double.compare(d1, d2) == 0) {

            System.out.println("d1=d2");
        }
        else if (Double.compare(d1, d2) < 0) {

            System.out.println("d1<d2");
        }
        else {

            System.out.println("d1>d2");
        }
    }
}
```

****Output:** 

```java
d1=d2
```** 

****程序 2 :** 当 d1 < d2**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java Program to illustrate
// the Double.compare() method

import java.lang.Double;

public class GFG {
    public static void main(String[] args)
    {

        // Get the two double values
        // to be compared
        Double d1 = 10d;
        Double d2 = 1023d;

        // function call to compare two double values
        if (Double.compare(d1, d2) == 0) {

            System.out.println("d1=d2");
        }
        else if (Double.compare(d1, d2) < 0) {

            System.out.println("d1<d2");
        }
        else {

            System.out.println("d1>d2");
        }
    }
}
```

****Output:** 

```java
d1
```** 

****程序 3 :** 当 d1 > d2**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
// Java Program to illustrate
// the Double.compare() method

import java.lang.Double;

public class GFG {
    public static void main(String[] args)
    {

        // Get the two double values
        // to be compared
        Double d1 = 1023d;
        Double d2 = 10d;

        // function call to compare two double values
        if (Double.compare(d1, d2) == 0) {

            System.out.println("d1=d2");
        }
        else if (Double.compare(d1, d2) < 0) {

            System.out.println("d1<d2");
        }
        else {

            System.out.println("d1>d2");
        }
    }
}
```

****Output:** 

```java
d1>d2
```** 

****参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/lang/double . html # compare(double，%20double)](https://docs.oracle.com/javase/7/docs/api/java/lang/Double.html#compare(double, %20double))**