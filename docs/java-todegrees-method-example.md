# Java toDegrees()方法示例

> 原文:[https://www . geeksforgeeks . org/Java-todegrees-method-example/](https://www.geeksforgeeks.org/java-todegrees-method-example/)

java.lang.Math.toDegrees()用于将以弧度度量的角度转换为以度数度量的近似等效角度。

**注**:弧度到度数的转换一般不精确；用户不应该期望 cos(toRadians(90.0))正好等于 0.0。

**语法** :

```
public static double toDegrees(double rad)

Parameter:
rad : This parameter is an angle in radians which
we want to convert in degrees.
Return :
This method returns the measurement of the angle 
rad in degrees.

```

**示例**:展示**Java . lang . math . todegrees()**方法的工作。

```
// Java program to demonstrate working
// of java.lang.Math.toDegrees() method
import java.lang.Math;

class Gfg {

    // driver code
    public static void main(String args[])
    {
        // value of PI in degrees
        double rad = Math.PI;
        System.out.println(Math.toDegrees(rad));

        // value of PI/2 in degrees
        rad = (Math.PI) / 2;
        System.out.println(Math.toDegrees(rad));

        // value of PI/4 in degrees
        rad = (Math.PI) / 4;
        System.out.println(Math.toDegrees(rad));
    }
}
```

输出:

```
180.0
90.0
45.0

```