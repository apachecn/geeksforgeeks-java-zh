# Java 中的图像处理–彩色图像到负片图像的转换

> 原文:[https://www . geesforgeks . org/image-processing-in-Java-colored-image-to-negative-image-conversion/](https://www.geeksforgeeks.org/image-processing-in-java-colored-image-to-negative-image-conversion/)

**先决条件:**

*   [Java 中的图像处理–读写](https://www.geeksforgeeks.org/image-processing-in-java-read-and-write/)
*   [Java 中的图像处理–获取和设置像素](https://www.geeksforgeeks.org/image-processing-in-java-get-and-set-pixels/)
*   [Java 中的图像处理——彩色图像到灰度图像的转换](https://www.geeksforgeeks.org/image-processing-in-java-colored-image-to-grayscale-image-conversion/)

在这一集里，我们将把彩色图像转换成负片图像。

**彩色图像(RGB 颜色模型)–**RGB 颜色模型是一种添加混合模型，其中红色、绿色和蓝色光以各种方式添加在一起，以再现各种颜色。

**负像–**负像是**完全反转，其中亮区呈现暗，反之亦然**。此外，负彩色图像还会发生颜色反转，红色区域显示为青色，绿色区域显示为洋红色，蓝色区域显示为黄色，反之亦然。

图像负片是通过从最大强度值中减去每个像素而产生的**。例如，在 8 位灰度图像中，最大强度值为 255，因此从 255 中减去每个像素以产生输出图像。**

> **注意**:在负片图像中，图像的 Alpha 分量将与原始图像相同，但是 RGB 将会改变，即所有三个 RGB 分量的值都是 255-原始分量值。

#### **算法:**

1.  获取像素的 RGB 值。
2.  计算新的 RGB 值，如下所示:
    *   R = 255–R
    *   G = 255–G
    *   B = 255–B
3.  用步骤 2 中计算的值替换像素的 R、G 和 B 值。
4.  对图像的每个像素重复步骤 1 至步骤 3。

#### **实施:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// colored to negative conversion

import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
import javax.imageio.ImageIO;

public class Negative {
    public static void main(String args[])
        throws IOException
    {
        BufferedImage img = null;
        File f = null;

        // read image
        try {
            f = new File(
                "C:/Users/hp/Desktop/Image Processing in Java/gfg-logo.png");
            img = ImageIO.read(f);
        }
        catch (IOException e) {
            System.out.println(e);
        }

        // Get image width and height
        int width = img.getWidth();
        int height = img.getHeight();

        // Convert to negative
        for (int y = 0; y < height; y++) {
            for (int x = 0; x < width; x++) {
                int p = img.getRGB(x, y);
                int a = (p >> 24) & 0xff;
                int r = (p >> 16) & 0xff;
                int g = (p >> 8) & 0xff;
                int b = p & 0xff;

                // subtract RGB from 255
                r = 255 - r;
                g = 255 - g;
                b = 255 - b;

                // set new RGB value
                p = (a << 24) | (r << 16) | (g << 8) | b;
                img.setRGB(x, y, p);
            }
        }

        // write image
        try {
            f = new File(
                "C:/Users/hp/Desktop/Image Processing in Java/GFG.png");
            ImageIO.write(img, "png", f);
        }
        catch (IOException e) {
            System.out.println(e);
        }
    }
}
```

#### 输出–

<video class="wp-video-shortcode" id="video-139715-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20211109162233/Image-Processing-In-Java---Set-4-1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20211109162233/Image-Processing-In-Java---Set-4-1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20211109162233/Image-Processing-In-Java---Set-4-1.mp4)</video>

> **注意:**此代码不会在联机 IDE 上运行，因为它需要磁盘上的映像。

本文由 **Pratik Agarwal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。