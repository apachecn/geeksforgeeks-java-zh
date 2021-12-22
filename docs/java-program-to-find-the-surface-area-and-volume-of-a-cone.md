# 计算圆锥体表面积和体积的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-find-a-cone 的表面积和体积/](https://www.geeksforgeeks.org/java-program-to-find-the-surface-area-and-volume-of-a-cone/)

给定圆锥体的尺寸，求圆锥体的表面积和体积。计算面积和体积的公式如下。

**圆锥**

圆锥体是三维几何形状。它由一个圆形的底部和一个弯曲的侧面(侧面)组成，末端称为顶点或顶点。

![height, radius and slant height of a cone](img/0916e60474cd25d71c8be39db24ba24f.png)

> 圆锥的表面积=圆锥的面积+圆的面积=π* r * s+π* r^2
> 
> 圆锥的体积= 1/3(π* r * r * h)

其中 r 为圆形底面的半径，h 为高度(底面到顶点的垂直距离)T2 sT4】为圆锥体的倾斜高度。

可以使用[毕达哥拉斯公式](https://www.geeksforgeeks.org/pythagoras-theorem-and-its-converse-triangles-class-10-maths/) sqrt(r * r + h * h)计算倾斜高度

```
Input : 
radius = 5
slant_height = 13
height = 12
Output :
Volume Of Cone = 314.159
Surface Area Of Cone = 282.743

Input :
radius = 6
slant_height = 10
height = 8
Output : 
Volume Of Cone = 301.593
Surface Area Of Cone = 301.593
```

**进场:**

*   给定圆锥的尺寸，比如圆锥的半径和高度
*   求 S = sqrt(R * R + H * H)
*   应用以上公式

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Find the Surface Area and Volume of a
// Cone

import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // specify radius and height of cone
        double R = 6, H = 8;

        // calculate slant height S
        double S = Math.sqrt(R * R + H * H);

        // calculate surface area of cone
        double SurfaceArea
            = (Math.PI * R * R) + (Math.PI * R * S);

        // calculate volume of cone
        double Volume = (Math.PI * R * R * H) / 3;

        System.out.println("Surface area of cone is : "
                           + SurfaceArea);

        System.out.println("Volume of cone is : " + Volume);
    }
}
```

**Output**

```
Surface area of cone is : 301.59289474462014
Volume of cone is : 301.59289474462014

```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Find the Surface Area and Volume of a
// Cone

import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // specify radius and height of cone
        double R = 3.42, H = 12;

        // calculate slant height S
        double S = Math.sqrt(R * R + H * H);

        // calculate surface area of cone
        double SurfaceArea
            = (Math.PI * R * R) + (Math.PI * R * S);

        // calculate volume of cone
        double Volume = (Math.PI * R * R * H) / 3;

        System.out.println("Surface area of cone is : "
                           + SurfaceArea);

        System.out.println("Volume of cone is : " + Volume);
    }
}
```

**Output**

```
Surface area of cone is : 170.81027853689216
Volume of cone is : 146.98129725379061

```

**时间复杂度=** O(1)