# 介于==和之间的差值。Java 中的 equals()方法

> 原文:[https://www . geeksforgeeks . org/difference-and-equals-method-in-Java/](https://www.geeksforgeeks.org/difference-between-and-equals-method-in-java/)

在 Java 中，equals()方法和==运算符都用于比较两个对象。==是运算符，equals()是方法。但是==运算符比较堆中对象的引用或内存位置，不管它们是否指向同一个位置。

每当我们使用运算符 new 创建一个对象时，它都会为该对象创建一个新的内存位置。因此，我们使用==运算符来检查两个对象的内存位置或地址是否相同。

一般来说，Java 中的 equals()和" == "运算符都是用来比较对象来检查相等性的，但是这里有两者之间的一些区别:

1.  The main difference between. The equals () method and the = = operator are one method and the other operator.
2.  We can use the = = operator for reference comparison ( **address comparison** ) and. The equals () method is used for **content comparison** . Simply put, = = Check whether two objects point to the same memory location. Equals () calculates the comparison of values in objects.
3.  If a class does not have [to override the equals method](https://www.geeksforgeeks.org/overriding-equals-method-in-java/) , then by default, it uses the equals(Object o) method of the nearest parent class that has already overridden the method. See [Why do you want to override the equals (object) and hashCode () methods?](https://www.geeksforgeeks.org/override-equalsobject-hashcode-method/) Detailed.

## Java

```
// Java program to understand 
// the concept of == operator

public class Test {
    public static void main(String[] args)
    {
        String s1 = "HELLO";
        String s2 = "HELLO";
        String s3 =  new String("HELLO");

        System.out.println(s1 == s2); // true
        System.out.println(s1 == s3); // false
        System.out.println(s1.equals(s2)); // true
        System.out.println(s1.equals(s3)); // true
    }
}
```

**输出**

```
true
false
true
true
```