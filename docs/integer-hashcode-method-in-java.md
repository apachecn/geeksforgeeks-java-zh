# Java 中的整数 hashCode()方法

> 原文:[https://www . geesforgeks . org/integer-hashcode-method-in-Java/](https://www.geeksforgeeks.org/integer-hashcode-method-in-java/)

java 中 Integer 类的**Java . lang . Integer . hashcode()**方法用于返回特定 Integer 的哈希代码。

**语法:**

```java
public int hashCode()
```

**参数:**该方法不取任何参数。

**返回值:**该方法为*这个*对象返回一个哈希码整数值，等于这个 integer 对象所表示的不复杂的本原整数值。

下面的程序说明了整数类的 hashCode()的使用:
**程序 1:** 当传递整数数据类型时。

```java
// Java program to demonstrate working
// of Java.lang.Integer.hashCode() Method
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {
        // Object s_int created
        Integer s_int = new Integer("223");

        // Returning a hash code value for this object 
        int hashcodevalue = s_int.hashCode();
        System.out.println("Hash code Value for object = " + hashcodevalue);
    }
}
```

**Output:**

```java
Hash code Value for object = 223

```

**程序 2:** 传递字符串数据类型时。
**注意:**这会导致类似*的运行时错误数字格式异常*

```java
// Java program to demonstrate working
// of Java.lang.Integer.hashCode() Method
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {
        // object s_int created
        Integer s_int = new Integer("gfg");

        // Returning a hash code value for this object.
        int hashcodevalue = s_int.hashCode();
        System.out.println("Hash code Value for object = " + hashcodevalue);
    }
}
```

**输出:**

```java
Exception in thread "main" java.lang.NumberFormatException: For input string: "gfg"
    at java.lang.NumberFormatException.forInputString(NumberFormatException.java:65)
    at java.lang.Integer.parseInt(Integer.java:580)
    at java.lang.Integer.(Integer.java:867)
    at Geeks.main(Geeks.java:9)

```