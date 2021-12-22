# Java 数组比较()方法与示例

> 原文:[https://www . geesforgeks . org/Java-arrays-compare-method-with-examples/](https://www.geeksforgeeks.org/java-arrays-compare-method-with-examples/)

Java 中的 Arrays compare()方法属于 Arrays 类和 **java.util** 包。此方法按字典顺序比较两个数组。布尔、字节、字符、双精度、浮点、整型、长整型、短整型和对象数组的不同重载有两种不同的版本。该方法根据下面提到的情况返回值。

*   Returns 0 if the array is equal to another array.
*   If the array is less than in dictionary order
*   A value less than 0 is returned if another array in. If the array is lexicographically larger than another array (more characters), a value greater than 0 is returned.

空数组在字典序上小于非空数组，如果两个数组都为空，则认为这两个数组相等，因此在这种情况下将打印 0。

**语法:**

```java
Arrays.compare(array1,array2);
// array1 and array2 are two arrays
```

**参数和返回类型:【compare()方法接受一个数组作为不同数据类型的参数，例如:字符串、整数、浮点、双精度、长等。此方法的返回类型是整数。如果数组按字典顺序排列较大，则返回正值；如果较小，则返回负值；如果相等，则返回 0。**

**异常:**它通常抛出 NullPointerException 和 ClassCastException，这两个异常也有不同的含义。

*   **Nullpointerexception** : Nullpointerexception is a runtime exception, which refers to null and occurs when a variable that does not point to any object is accessed.
*   **Classcastexception:** This kind of exception will occur when we try to convert one class object into another.

如果我们想调用这个方法，首先从 JavaJava 导入“数组”类。util 包只需添加“import java.util.Arrays”命令。然后通过“数组”跟随调用方法。比较(参数 1，参数 2)；"通过这种方式，您可以很容易地调用 compare()方法。

**示例 1:** 我们举个例子，首先导入 java.util.Arrays，创建一个名为 CompareExample 的公共类，然后用元素初始化两个整数数组，使用 compare()方法进行比较，最后打印 compare 方法的结果。

## Java

```java
import java.util.Arrays;

public class CompareExample{
    public static void main(String[] args) 
    {
        //Initialied two integer array
        int[] array1 ={6, 7, 8, 11, 18, 8, 2, 5};        
        int[] array2 ={3, 5, 9, 13, 28, 6, 8, 9};
        //compare both integer array using compare method and finally print result       
        System.out.println("Result is "+ Arrays.compare(array1,array2));

    }
}
```

**输出**

```java
Result is 1
```

因此，期望的输出是 1，因为数组 1 在字典上大于数组 2。

**例 2:** 我们再举一个例子，在这个例子中，我们将取一个不同数据类型的数组，也就是 float，和我们在上面提到的例子中做的一样，首先导入类，创建一个名为“CompareExample”的新类，然后用元素初始化两个 float 类型的数组，然后使用 array 类的 compare 方法进行比较，最后打印我们得到的结果。

## Java

```java
// import Arrays class from java.util package
import java.util.Arrays;

public class CompareExample{

    public static void main(String[] args) 
    {
        // Initialize two float array with element
        float[] floatArray1={5.12f, 8.3f, 9.17f, 2.5f, 8.8f, 5.17f, 4.2f, 7.37f};
        float[] floatArray2={7.12f, 9.3f, 6.17f, 7.5f, 5.8f, 7.17f, 3.2f, 6.37f};

        // compare two float array using compare method and finally print result
        System.out.println("Result is " + Arrays.compare(floatArray1, floatArray2));

    }
}
```

**输出**

```java
Result is -1
```

输出结果为-1，因为浮动数组 1 在字典上小于浮动数组 2。

**例 3:** 我们举个例子。在本文中，我们将初始化一个具有相同数量和大小的数组。然后比较数组 1 和数组 2，最后打印出我们通过比较方法得到的结果。

## Java

```java
import java.util.Arrays;

public class CompareExample {

    public static void main(String[] args)
    {
        // Initialize two integer array with same elements
        int[] array1 = { 1, 2, 3, 4 };
        int[] array2 = { 1, 2, 3, 4 };

        // compare array1 and array2 using compare() method
        // and print the result
        System.out.println(
            "Result is " + Arrays.compare(array1, array2));
    }
}
```

**输出**

```java
Result is 0
```

期望的输出是 0，因为我们得到了两个相同数量和大小的整数数组。

在本文中，我们学习了如何使用 compare()方法。如果数组 1 在字典上大于数组 2，它将返回一个正(-ve)值。如果数组 1 在字典上小于数组 2，它将返回负(-ve)值。如果两个数组在字典上相等或为空，那么它将返回 0。