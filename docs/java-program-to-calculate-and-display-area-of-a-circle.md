# 计算和显示圆面积的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-计算和显示圆面积的程序/](https://www.geeksforgeeks.org/java-program-to-calculate-and-display-area-of-a-circle/)

给定圆的半径，编写一个 java 程序来计算和显示圆的面积。(取∏=3.142)

**例**T0】

我们知道要计算圆的面积，圆的半径必须是已知的，所以如果圆的半径是已知的，那么圆的面积可以用公式计算:

> **面积= 3.142*(半径)*(半径)**

下面是计算圆面积的 Java 程序:-

## Java

```
// Java program to calculate the area of the
public class GFG {
    public static void main(String[] args)
    {
        int radius;
        double pi = 3.142, area;
        radius = 5;
        // calculating the area of the circle
        area = pi * radius * radius;
        // printing the area of the circle
        System.out.println("Area of circle is :" + area);
    }
}
```

**输出**

```
Area of circle is :78.55

```