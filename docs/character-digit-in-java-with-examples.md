# Java 中的 Character.digit()，示例

> 原文:[https://www . geesforgeks . org/character-digit-in-Java-with-examples/](https://www.geeksforgeeks.org/character-digit-in-java-with-examples/)

java.lang.Character.digit()是 java 中的一个内置方法，它以指定的*基数返回字符 *ch* 的数值。*如果基数不在范围*MIN _ RADIX<= RADIX<=“MAX _ RADIX</em”>内，或者如果 ch 的值不是指定基数中的有效数字，则返回-1。如果以下至少一项为真，则字符为有效数字:*

**   The method is true for this character, and the Unicode decimal digit value (or its single character decomposition) of this character is less than the specified cardinality. In this case, the decimal numeric value is returned.*   The character is one of the capital Latin letters' a' to' z', and its code is less than radix+'a'–10\. In this case, return ch -' A '+10.*   Is one of the lowercase Latin letters' a' to' z', and its code is less than radix+'a'–10\. In this case, return ch -' a '+10.*   Is one of the full-width Latin letters A(' uff 21') to Z(' uff 3a'), and its code is less than radix+'\ UFF 21'–10\. In this case, return ch–'\ uff21'+10.*   Is one of the full-width lowercase Latin letters a ('\uFF41') to z ('\uFF5A'), and its code is less than radix+'\ uff41'–10\. In this case, return ch–'\ uff41'+10.*

 ***语法:**

```java
public static int digit(char ch, int radix)

```* 

**参数:**该函数接受两个参数，如下所述:

*   **ch-** 这是指定要转换的字符的强制参数。
*   **基数-** 这是指定基数的强制参数。

**返回值:**该方法返回指定基数的字符所代表的数值。

以下程序演示了上述方法:

**程序 1:**

```java
// Java program to illustrate the
// Character.digit() method

import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {
        // create and assign value
        // to 2 character objects
        char c1 = '3', c2 = '6';

        // assign the numeric value of c1 to in1 using radix
        int in1 = Character.digit(c1, 5);
        System.out.println("Numeric value of " + c1 + " in radix 5 is " + in1);

        // assign the numeric value of c2 to in2 using radix
        int in2 = Character.digit(c2, 15);
        System.out.println("Numeric value of " + c2 + " in radix 15 is " + in2);
    }
}
```

**Output:**

```java
Numeric value of 3 in radix 5 is 3
Numeric value of 6 in radix 15 is 6

```

**程序 2:**

```java
// Java program to illustrate the
// Character.digit() method
// when -1 is returned
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {

        // create and assign value
        // to 2 character objects
        char c1 = 'a', c2 = 'z';

        // assign the numeric value of c1 to in1 using radix
        int in1 = Character.digit(c1, 5);
        System.out.println("Numeric value of " + c1 + " in radix 5 is " + in1);

        // assign the numeric value of c2 to in2 using radix
        int in2 = Character.digit(c2, 15);
        System.out.println("Numeric value of " + c2 + " in radix 15 is " + in2);
    }
}
```

**Output:**

```java
Numeric value of a in radix 5 is -1
Numeric value of z in radix 15 is -1

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/lang/character . html #数字(char，%20int)](https://docs.oracle.com/javase/7/docs/api/java/lang/Character.html#digit(char,%20int))

=>