# Java 中的整数 rotateRight()方法

> 原文:[https://www . geesforgeks . org/integer-rotateright-method-in-Java/](https://www.geeksforgeeks.org/integer-rotateright-method-in-java/)

移位用于编程，在每种编程语言中至少有一种变体。Java 只有一个逻辑右移运算符(> >)。位移位是一种按位运算。对二进制值的所有位进行移位，这将位向右移动一定数量的位置。如果值为 0100；(即。4)右移，变成 0010；(即。2)它再次向右移动，变成 0001；或者 1。
Java . lang . integer . rotateright()是通过将指定 int 值 *a* 的二进制补码二进制表示向右旋转指定位数来返回我们得到的值的方法。位向右移动，即向低阶移动。

**语法:**

```
public static int rotateRight(*int a, int shifts*)
```

**参数:**该方法取两个参数:

*   *a* :这是整数类型，指的是要进行运算的值。
*   *移位*:这也是整数类型，指的是旋转的距离。

**return:**rotateRight()方法返回通过将指定 int 值的二进制补码二进制表示向右旋转指定位数而获得的值。

下面的程序说明了 Java.lang.Integer.rotateRight()方法:
**程序 1:** 为正数。

```
// Java program to illustrate the
// Java.lang.Integer.rotateRight() method
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {
        int a = 64;
        int shifts = 0;
        while (shifts < 3)
        // It will return the value obtained by rotating left
        {
            a = Integer.rotateRight(a, 2);
            System.out.println(a);
            shifts++;
        }
    }
}
```

**Output:**

```
16
4
1

```

**程序 2:** 为负数。

```
// Java program to illustrate the
// Java.lang.Integer.rotateRight() method
import java.lang.*;

public class Geeks {

    public static void main(String[] args)
    {

        int a = -165;
        int shifts = 0;
        while (shifts < 3)
        // It will return the value obtained by rotating left
        {
            a = Integer.rotateRight(a, 2);
            System.out.println(a);
            shifts++;
        }
    }
}
```

**Output:**

```
-42
-1073741835
1879048189

```