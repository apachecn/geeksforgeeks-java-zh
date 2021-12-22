# 爪哇郎。Java 中的 Long.reverse()方法，示例

> 原文:[https://www . geesforgeks . org/Java-lang-long-reverse-method-Java-examples/](https://www.geeksforgeeks.org/java-lang-long-reverse-method-java-examples/)

**java . lang . long . reverse()**是 Java 中的一个内置函数，它返回通过反转指定长值的二进制补码表示中的位的顺序而获得的值。

**语法:**

```java
public static long reverse(long num) 
Parameter :
num - the number passed
Returns : 
the value obtained by reversing the order of the bits in the 
two's complement binary representation of the specified long value.
```

示例:

```java
Input : 254 
Output : 9151314442816847872

Input : 8
Output : 1152921504606846976

```

下面的程序说明了 java.lang.Long.reverse()函数:

**程序 1 :**

```java
// Java program that demonstrates the
// Long.reverse() function

// include lang package
import java.lang.*;

public class GFG {

public static void main(String[] args)
    {

        long l = 8;

        System.out.println("The number after reversing bit= "
                           + Long.reverse(l));

        l = 254;
        System.out.println("The number after reversing bit= "
                           + Long.reverse(l));
    }
}
```

输出:

```java
The number after reversing bit= 1152921504606846976
The number after reversing bit= 9151314442816847872

```

**程序 2 :** 当一个负数通过时

```java
// Java program that demonstrates the
// Long.reverse() function
// negative number

// include lang package
import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        long l = -8;

        System.out.println("The number after reversing bit= "
                           + Long.reverse(l));

        l = -254;
        System.out.println("The number after reversing bit= "
                           + Long.reverse(l));
    }
}
```

输出:

```java
The number after reversing bit= 2305843009213693951
The number after reversing bit= 4683743612465315839

```

**程序 3 :** 当一个十进制数通过时

```java
// Java program that demonstrates the
// Long.reverse() function
// decimal number

// include lang package
import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        System.out.println("The number after reversing bit= "
                           + Long.reverse(11.34));
    }
}
```

输出:

```java
prog.java:16: error: incompatible types: possible lossy conversion from double to long
                           + Long.reverse(11.34));

```

**程序 4** :当一个字符串数字被传递时

```java
// Java program that demonstrates the
// Long.reverse() function
// string number

// include lang package
import java.lang.*;

public class GFG {

    public static void main(String[] args)
    {

        System.out.println("The number after reversing bit= "
                           + Long.reverse("12"));
    }
}
```

输出:

```java
prog.java:16: error: incompatible types: String cannot be converted to long
                           + Long.reverse("12"));

```