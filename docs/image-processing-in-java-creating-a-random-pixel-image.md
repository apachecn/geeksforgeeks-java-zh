# Java 中的图像处理–创建随机像素图像

> 原文:[https://www . geesforgeks . org/image-processing-in-Java-creating-a-random-pixel-image/](https://www.geeksforgeeks.org/image-processing-in-java-creating-a-random-pixel-image/)

**先决条件:**

*   [Java 中的图像处理–读写](https://www.geeksforgeeks.org/image-processing-in-java-read-and-write/)
*   [Java 中的图像处理–获取和设置像素](https://www.geeksforgeeks.org/image-processing-in-java-get-and-set-pixels/)
*   [Java 中的图像处理——彩色图像到灰度图像的转换](https://www.geeksforgeeks.org/image-processing-in-java-colored-image-to-grayscale-image-conversion/)
*   [Java 中的图像处理–彩色图像到负片图像的转换](https://www.geeksforgeeks.org/image-processing-in-java-colored-image-to-negative-image-conversion/)
*   [Java 中的图像处理–彩色到红绿蓝图像转换](https://www.geeksforgeeks.org/image-processing-in-java-colored-to-red-green-blue-image-conversion/)
*   [Java 中的图像处理——彩色图像到棕褐色图像的转换](https://www.geeksforgeeks.org/image-processing-in-java-colored-image-to-sepia-image-conversion/)

在本文中，我们将创建一个随机像素图像。为了创建随机像素图像，我们不需要任何输入图像。我们可以创建一个图像文件，并设置其随机生成的像素值。

A **随机图像**是随机选择像素的图像，因此它们可以从所需的调色板中选择任何颜色(通常为 1600 万种颜色)。生成的图像看起来像多色噪声背景。

#### **算法:**

1.  设置新图像文件的尺寸。
2.  创建一个 BufferedImage 对象来保存图像。该对象用于在内存中存储图像。
3.  为 alpha、红色、绿色和蓝色分量生成随机数值。
4.  设置随机生成的 ARGB(阿尔法、红色、绿色和蓝色)值。
5.  对图像的每个像素重复步骤 3 和 4。

#### **实施:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate 
// creation of random pixel image

import java.io.File;
import java.io.IOException;
import java.awt.image.BufferedImage;
import javax.imageio.ImageIO;

public class RandomImage
{
    public static void main(String args[])throws IOException
    {
        // Image file dimensions
        int width = 640, height = 320;

        // Create buffered image object
        BufferedImage img = null;
        img = new BufferedImage(width, height, BufferedImage.TYPE_INT_ARGB);

        // file object
        File f = null;

        // create random values pixel by pixel
        for (int y = 0; y < height; y++)
        {
            for (int x = 0; x < width; x++)
            {
                  // generating values less than 256
                int a = (int)(Math.random()*256);
                int r = (int)(Math.random()*256);
                int g = (int)(Math.random()*256); 
                int b = (int)(Math.random()*256); 

                  //pixel
                int p = (a<<24) | (r<<16) | (g<<8) | b; 

                img.setRGB(x, y, p);
            }
        }

        // write image
        try
        {
            f = new File("C:/Users/hp/Desktop/Image Processing in Java/gfg-logo.png");
            ImageIO.write(img, "png", f);
        }
        catch(IOException e)
        {
            System.out.println("Error: " + e);
        }
    }
}
```

#### 输出:

<video class="wp-video-shortcode" id="video-140072-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20211111201231/Image-Processing-In-Java---Set-7-1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20211111201231/Image-Processing-In-Java---Set-7-1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20211111201231/Image-Processing-In-Java---Set-7-1.mp4)</video>

> **注意:**代码不会在联机 ide 上运行，因为它将映像写入驱动器。

本文由 **Pratik Agarwal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。