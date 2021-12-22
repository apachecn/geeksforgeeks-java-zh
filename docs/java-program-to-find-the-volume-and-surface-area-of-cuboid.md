# 求长方体体积和表面积的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-find-长方体的体积和表面积/](https://www.geeksforgeeks.org/java-program-to-find-the-volume-and-surface-area-of-cuboid/)

长方体是在三维平面上表示的三维盒状图形。长方体有 6 个长方形面。每个面与另一个面以 90 度相交。 长方体的三个面在同一个顶点相交。 由于由 6 个矩形面组成，所以具有不同尺寸的长、宽、高。给定长方体的尺寸，求长方体的表面积和体积。计算面积和体积的公式如下。

**示例:**

```
Input : 20 15 10
Output : Surface Area = 1300
         Volume = 3000 

Input : 30 5 10
Output : Surface Area = 1000
         Volume = 1500
```

**公式:**

> 体积=长度*宽度*高度
> 
> 长方体表面积= 2(长*宽+宽*高+高*长)

**进场:**

*   给定圆锥体的尺寸，比如长方体的长度 L、高度 H 和宽度 B。
*   计算体积和表面积

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Find the Volume and Surface Area of
// Cuboids

import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // specify L,B and H
        double L = 20, B = 15, H = 10;

        // calculate SurfaceArea
        double SurfaceArea = 2 * (L * B + B * H + H * L);

        // calculate Volume
        double Volume = L * B * H;

        System.out.println(
            "The Surface area of cuboid is : "
            + SurfaceArea);

        System.out.println("The Volume of the cuboid is : "
                           + Volume);
    }
}
```

**Output**

```
The Surface area of cuboid is : 1300.0
The Volume of the cuboid is : 3000.0
```

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        // specify L,B and H
        double L = 30, B = 5, H = 10;

        // calculate SurfaceArea
        double SurfaceArea = 2 * (L * B + B * H + H * L);

        // calculate Volume
        double Volume = L * B * H;

        System.out.println(
            "The Surface area of cuboid is : "
            + SurfaceArea);

        System.out.println("The Volume of the cuboid is : "
                           + Volume);
    }
}
```

**Output**

```
The Surface area of cuboid is : 1000.0
The Volume of the cuboid is : 1500.0
```

**时间复杂度=** O(n)