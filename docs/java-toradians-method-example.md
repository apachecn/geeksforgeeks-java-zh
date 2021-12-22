# Java toRadians()方法示例

> 原文:[https://www . geesforgeks . org/Java-tora dians-method-example/](https://www.geeksforgeeks.org/java-toradians-method-example/)

java.lang.Math.toRadians()用于将以度为单位的角度转换为以弧度为单位的近似等效角度。
**注**:度数到弧度的转换一般不精确。

**语法**:

```
public static double toRadians(double deg)

Parameter:
deg : This parameter is an angle in degrees which
we want to convert in radians.
Return :
This method returns the measurement of the angle 
*deg* in radians.
```

**示例**:展示**Java . lang . math . toradians()**方法的工作。

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate working
// of java.lang.Math.toRadians() method
import java.lang.Math;

class Gfg {

    // driver code
    public static void main(String args[])
    {
        // converting PI from degree to radian
        double deg = 180.0;
        System.out.println(Math.toRadians(deg));

        // converting PI/2 from degree to radian
        deg = 90.0;
        System.out.println(Math.toRadians(deg));

        // converting PI/4 from degree to radian
        deg = 45.0;
        System.out.println(Math.toRadians(deg));
    }
}
```

**输出:**

```
3.141592653589793
1.5707963267948966
0.7853981633974483
```