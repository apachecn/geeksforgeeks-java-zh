# Java 中 Character.getDirectionality()方法，带示例

> 原文:[https://www . geesforgeks . org/character-get directionality-method-in-Java-with-examples/](https://www.geeksforgeeks.org/character-getdirectionality-method-in-java-with-examples/)

**java . lang . character . getdirectionality()**是 Java 中的一个内置方法，它返回给定字符的 Unicode 方向性属性。字符方向性用于计算文本的视觉顺序。未定义的字符值的方向性值是方向性 _ 未定义。此方法无法处理补充字符。为了支持包括补充字符在内的所有 Unicode 字符，请在此方法的参数中传递一个整数。

**语法:**

```
public static byte getDirectionality(char ch)
```

**参数:**该功能接受一个参数 ***ch*** ，该参数为必选项。此参数指定请求方向性属性的字符。参数可以是 int 或 char 数据类型。

**返回值:**函数返回表示字符值方向性的字节。

下面的程序说明了上述方法:

**程序 1:**

```
// Java program to demonstrate the
// Character.getDirectionality() method
// when the passed parameter is an integer
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {
        // create 2 int primitives ch1 and
        // ch2 and assign values to them
        int ch1=0x2424, ch2=0x2c61;

        // assign directionality of ch1, ch2 to bp1, bp2
        byte b1 = Character.getDirectionality(ch1);
        byte b2 = Character.getDirectionality(ch2);

        System.out.println("Directionality of first primitive is " + b1);
        System.out.println("Directionality of first primitive is " + b2);
    }
}
```

**输出:**

```
Directionality of first primitive is 13
Directionality of first primitive is 0

```

**程序二:**

```
// Java program to demonstrate the
// Character.getDirectionality() method
// when the passed parameter is a character
import java.lang.*;

public class gfg {

    public static void main(String[] args)
    {
        // create 2 int primitives ch1 and
        // ch2 and assign values to them
        char ch1 = 'M', ch2 = '\u06ff';

        // assign directionality of ch1, ch2 to bp1, bp2
        byte b1 = Character.getDirectionality(ch1);
        byte b2 = Character.getDirectionality(ch2);

        System.out.println("Directionality of first primitive is " + b1);
        System.out.println("Directionality of first primitive is " + b2);
    }
}
```

**输出:**

```
Directionality of first primitive is 0
Directionality of first primitive is 2

```

**参考**:[https://docs . Oracle . com/javase/7/docs/API/Java/lang/character . html # getDirectionality(char)](https://docs.oracle.com/javase/7/docs/api/java/lang/Character.html#getDirectionality(char))