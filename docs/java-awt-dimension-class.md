# Java AWT |维度类

> 原文:[https://www.geeksforgeeks.org/java-awt-dimension-class/](https://www.geeksforgeeks.org/java-awt-dimension-class/)

维度类是 Java AWT 的一部分。它以整数和双精度形式包含组件的高度和宽度。Dimension 类的用途是 Java AWT 和 Swing 的很多函数都返回维度对象。

**维度类的构造函数**

1.  **Dimension()** :它将创建一个高度和宽度设置为零的新对象。
2.  **尺寸(尺寸 d)** :它将创建一个与指定对象具有相同高度和宽度的新对象。
3.  **尺寸(int w，int h)** :会创建一个指定高度和宽度的新对象。

**维度类的方法**

<figure class="table">

| 方法 | 说明 |
| --- | --- |
| 等于(对象 0) | 检查两个尺寸对象是否相等。 |
| 得到海特 （） | 返回尺寸对象的高度 |
| getWidth（） | 返回尺寸对象的宽度 |
| getSize() | 返回维度对象的大小。 |
| hashCode() | 返回维度的 hashcode。 |
| setSize(维 d) | 将对象的大小设置为指定的尺寸 |
| 设置大小(双倍宽度，双倍高度) | 将高度和宽度设置为指定的双精度值 |
| 设置大小(整数宽度，整数高度) | 将高度和宽度设置为指定的整数值 |

</figure>

**以下程序说明了维度类**:

*   显示维度类(整数精度)功能的程序。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to show the functions
// of dimension class(Integer precision)
import java.awt.*;
class dimen {

    // Main Method
    public static void main(String args[])
    {

        // create dimension
        Dimension d = new Dimension();
        Dimension d1 = new Dimension(20, 30);
        Dimension d2 = new Dimension(d1);

        // set height and width of dimension d
        d.setSize(30, 30);

        // equating dimensions
        System.out.println("Dimension d and d1 " +
                    "are equal = " + d.equals(d1));

        System.out.println("Dimension d and d1 " +
                "are equal = " + d1.equals(d2));

        // print hashcode
        System.out.println("Hashcode of Dimension " +
                            "d = " + d.hashCode());

        // display dimension
        display(d, "Dimension d");
        display(d1, "Dimension d1");
        display(d2, "Dimension d2");
    }

    // display dimension
    public static void display(Dimension d, String s)
    {
        System.out.println(s +" Height = " + d.getHeight() +
                                " Width= " + d.getWidth());
    }
}
```

**Output**

```java
Dimension d and d1 are equal = false
Dimension d and d1 are equal = true
Hashcode of Dimension d = 1860
Dimension d Height = 30.0 Width= 30.0
Dimension d1 Height = 30.0 Width= 20.0
Dimension d2 Height = 30.0 Width= 20.0
```

**Output:** 

```java
Dimension d and d1 are equal = false
Dimension d and d1 are equal = true
Hashcode of Dimension d = 1860
Dimesnion d Height = 30.0 Width= 30.0
Dimesnion d1 Height = 30.0 Width= 20.0
Dimesnion d2 Height = 30.0 Width= 20.0
```

*   显示尺寸类(双精度)功能的程序。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to show the functions
// of dimension class(Double precision)
import java.awt.*;

class dimen {

    // Main Method
    public static void main(String args[])
    {

        // create dimension
        Dimension d = new Dimension();
        Dimension d1 = new Dimension(20, 30);
        Dimension d2 = new Dimension(d1);

        // set height and width of dimension d
        d.setSize(30.3, 30.45);

        // equating dimensions
        System.out.println("Dimension d and d1" +
                "are equal = " + d.equals(d1));

        System.out.println("Dimension d and d1" +
                "are equal = " + d1.equals(d2));

        // print hashcode
        System.out.println("Hashcode of Dimension d = "
                                    + d.hashCode());

        // display dimension
        System.out.println("See the values are rounded" +
                        "off to ceiling in dimension d");
        display(d, "Dimension d");
        display(d1, "Dimension d1");
        display(d2, "Dimension d2");
    }

    // display dimension
    public static void display(Dimension d, String s)
    {
        System.out.println(s + " Height = " + d.getHeight()
                            + " Width = " + d.getWidth());
    }
}
```

**Output**

```java
Dimension d and d1are equal = false
Dimension d and d1are equal = true
Hashcode of Dimension d = 1984
See the values are roundedoff to ceiling in dimension d
Dimension d Height = 31.0 Width = 31.0
Dimension d1 Height = 30.0 Width = 20.0
Dimension d2 Height = 30.0 Width = 20.0
```

**Output:** 

```java
Dimension d and d1are equal = false
Dimension d and d1are equal = true
Hashcode of Dimension d = 1984
See the values are roundedoff to ceiling in dimension d
Dimesnion d Height = 31.0 Width = 31.0
Dimesnion d1 Height = 30.0 Width = 20.0
Dimesnion d2 Height = 30.0 Width = 20.0
```

**参考:**[https://docs . Oracle . com/javase/7/docs/API/Java/awt/dimension . html](https://docs.oracle.com/javase/7/docs/api/java/awt/Dimension.html)