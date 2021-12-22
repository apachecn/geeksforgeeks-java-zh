# Integer.valueOf()与 Integer.parseInt()示例

> 原文:[https://www . geesforgeks . org/integer-value of-vs-integer-par sent-with-examples/](https://www.geeksforgeeks.org/integer-valueof-vs-integer-parseint-with-examples/)

**[integer . parsent()](https://www.geeksforgeeks.org/string-to-integer-in-java-parseint/):**

在对字符串进行操作时，有时我们需要将表示为字符串的数字转换为整数类型。Java 中一般用来将 String 转换为 Integer 的方法是**parsent()**。此方法属于 [java.lang 包中的](https://www.geeksforgeeks.org/java-lang-package-java/)[整数类](https://www.geeksforgeeks.org/java-lang-integer-class-java/)。它以一个有效的字符串作为参数，并将其解析为原语数据类型 int。它只接受字符串作为参数，在传递任何其他数据类型的值时，由于类型不兼容，它会产生错误。

这种方法有两种变体:

**语法:**

```java
public static int parseInt(String s) throws NumberFormatException
```

```java
public static int parseInt(String s, int radix) throws NumberFormatException
```

**示例:**

```java
// Java program to demonstrate working parseInt()

public class GFG {
    public static void main(String args[])
    {
        int decimalExample = Integer.parseInt("20");
        int signedPositiveExample = Integer.parseInt("+20");
        int signedNegativeExample = Integer.parseInt("-20");
        int radixExample = Integer.parseInt("20", 16);
        int stringExample = Integer.parseInt("geeks", 29);

        System.out.println(decimalExample);
        System.out.println(signedPositiveExample);
        System.out.println(signedNegativeExample);
        System.out.println(radixExample);
        System.out.println(stringExample);
    }
}
```

**Output:**

```java
20
20
-20
32
11670324

```

**[integer . value of()](https://www.geeksforgeeks.org/integer-valueof-method-in-java/):**

这个方法是属于 [java.lang 包](https://www.geeksforgeeks.org/java-lang-package-java/)的静态方法，它返回保存传递的参数值的相关整数对象。此方法可以采用整数或字符串作为参数。但是当给定的字符串无效时，它会提供一个错误。这个方法也可以接受一个字符作为参数，但是输出将是它相应的 Unicode 值。此方法将始终缓存-128 到 127(含)范围内的值，并可能缓存此范围之外的其他值。

**语法:**

```java
public static Integer valueOf(int a)
```

```java
public static Integer valueOf(String str)
```

```java
public static Integer valueOf(String str, int base)
```

**示例:**

```java
// Java program to illustrate the
// java.lang.Integer.valueOf(int a)
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        Integer obj = new Integer(10);

        // Returns an Integer instance
        // representing the specified int value
        System.out.println("Output Value = "
                           + obj.valueOf(85));
    }
}
```

**Output:**

```java
Output Value = 85

```

<u>**integer . parsent()和 Integer.valueOf()**</u> 的区别

1.  **Integer.valueOf()返回一个 Integer 对象，而 Integer.parseInt()返回一个基元 Int。**

    ```java
    // Program to show the use
    // of Integer.parseInt() method

    class Test1 {
        public static void main(String args[])
        {
            String s = "77";

            // Primitive int is returned
            int str = Integer.parseInt(s);
            System.out.print(str);

            // Integer object is returned
            int str1 = Integer.valueOf(s);
            System.out.print(str1);
        }
    }
    ```

    **输出:**

    ```java
    7777

    ```

2.  **Both String and integer can be passed a parameter to Integer.valueOf() whereas only a String can be passed as parameter to Integer.parseInt().**

    ```java
    // Program to show that Integer.parseInt()
    // cannot take integer as parameter

    class Test3 {
        public static void main(String args[])
        {
            int val = 99;

            try {

                // It can take int as a parameter
                int str1 = Integer.valueOf(val);
                System.out.print(str1);

                // It cannot take an int as a parameter
                // Hence will throw an exception
                int str = Integer.parseInt(val);
                System.out.print(str);
            }
            catch (Exception e) {
                System.out.print(e);
            }
        }
    }
    ```

    **编译错误:**

    ```java
    prog.java:18: error: incompatible types:
    int cannot be converted to String
                int str = Integer.parseInt(val);
                                           ^
    1 error

    ```

3.  **Integer.valueOf() can take a character as parameter and will return its corresponding unicode value whereas Integer.parseInt() will produce an error on passing a character as parameter.**

    ```java
    // Program to test the method
    // when a character is passed as a parameter

    class Test3 {
        public static void main(String args[])
        {
            char val = 'A';

            try {

                // It can take char as a parameter
                int str1 = Integer.valueOf(val);
                System.out.print(str1);

                // It cannot take char as a parameter
                // Hence will throw an exception
                int str = Integer.parseInt(val);
                System.out.print(str);
            }
            catch (Exception e) {
                System.out.print(e);
            }
        }
    }
    ```

    **编译错误:**

    ```java
    prog.java:18: error: incompatible types:
    char cannot be converted to String
                int str = Integer.parseInt(val);
                                           ^
    1 error

    ```

<u>**差异表**</u>

| Integer.parseInt（） | Integer.valueOf() |
| --- | --- |
| 它只能将字符串作为参数。 | 它可以接受字符串和整数作为参数。 |
| 它返回一个原始的 int 值。 | 它返回一个整数对象。 |
| 当整数作为参数传递时，由于类型不兼容，它会产生错误 | 当一个整数作为参数传递时，它返回一个对应于给定参数的整数对象。 |
| 当字符作为参数传递时，此方法会产生错误(不兼容的类型)。 | 此方法可以将字符作为参数，并将返回相应的 unicode。 |
| 这在性能方面有所落后，因为与生成字符串相比，解析字符串需要花费大量时间。 | 通过缓存经常请求的值，该方法可能会产生显著更好的空间和时间性能。 |
| 如果我们需要原始的 int 数据类型，那么将使用 Integer.parseInt()方法。 | 如果需要包装整数对象，则使用 valueOf()方法。 |