# Java 中的图像处理–创建镜像

> 原文:[https://www . geesforgeks . org/image-processing-in-Java-creating-a-mirror-image/](https://www.geeksforgeeks.org/image-processing-in-java-creating-a-mirror-image/)

**先决条件:**

*   [Java 中的图像处理–读写](https://www.geeksforgeeks.org/image-processing-in-java-read-and-write/)
*   [Java 中的图像处理–获取和设置像素](https://www.geeksforgeeks.org/image-processing-in-java-get-and-set-pixels/)
*   [Java 中的图像处理——彩色图像到灰度图像的转换](https://www.geeksforgeeks.org/image-processing-in-java-colored-image-to-grayscale-image-conversion/)
*   [Java 中的图像处理–彩色图像到负片图像的转换](https://www.geeksforgeeks.org/image-processing-in-java-colored-image-to-negative-image-conversion/)
*   [Java 中的图像处理–彩色到红绿蓝图像转换](https://www.geeksforgeeks.org/image-processing-in-java-colored-to-red-green-blue-image-conversion/)
*   [Java 中的图像处理——彩色图像到棕褐色图像的转换](https://www.geeksforgeeks.org/image-processing-in-java-colored-image-to-sepia-image-conversion/)
*   [Java 中的图像处理–创建随机像素图像](https://www.geeksforgeeks.org/image-processing-in-java-creating-a-random-pixel-image/)

在这个场景中，我们将创建一个镜像。在镜子中看到的物体的图像是它的镜面反射或镜像。在这样的图像中，对象的右侧出现在左侧，反之亦然。因此，镜像被称为横向反转，这种现象被称为横向反转。主要技巧是从左到右获取源像素值，并在结果图像中从右到左设置相同的值。

#### **算法:**

1.  在缓冲区中读取源图像读取给定的图像。
2.  获取给定图像的尺寸。
3.  创建另一个相同尺寸的缓冲尺寸对象来保存镜像。
4.  从源图像中[以从左到右的方式]获取 ARGB(阿尔法、红色、绿色和蓝色)值。
5.  将 ARGB(阿尔法、红色、绿色和蓝色)设置为新创建的图像[以从右向左的方式]。
6.  对图像的每个像素重复步骤 4 和 5。

#### 实施:

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate
// creation of a mirror image

import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
import javax.imageio.ImageIO;

public class MirrorImage {
    public static void main(String args[])
        throws IOException
    {
        // BufferedImage for source image
        BufferedImage simg = null;

        // File object
        File f = null;

        // Read source image file
        try {
            f = new File(
                "C:/Users/hp/Desktop/Image Processing in Java/gfg-logo.png");
            simg = ImageIO.read(f);
        }

        catch (IOException e) {
            System.out.println("Error: " + e);
        }

        // Get source image dimension
        int width = simg.getWidth();
        int height = simg.getHeight();

        // BufferedImage for mirror image
        BufferedImage mimg = new BufferedImage(
            width, height, BufferedImage.TYPE_INT_ARGB);

        // Create mirror image pixel by pixel
        for (int y = 0; y < height; y++) {
            for (int lx = 0, rx = width - 1; lx < width; lx++, rx--) {

                  // lx starts from the left side of the image
                // rx starts from the right side of the
                // image lx is used since we are getting
                // pixel from left side rx is used to set
                // from right side get source pixel value
                int p = simg.getRGB(lx, y);

                // set mirror image pixel value
                mimg.setRGB(rx, y, p);
            }
        }

        // save mirror image
        try {
            f = new File(
                "C:/Users/hp/Desktop/Image Processing in Java/GFG.png");
            ImageIO.write(mimg, "png", f);
        }
        catch (IOException e) {
            System.out.println("Error: " + e);
        }
    }
}
```

#### 输出:

<video class="wp-video-shortcode" id="video-140076-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20211111233223/Image-Processing-In-Java---Set-8-1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20211111233223/Image-Processing-In-Java---Set-8-1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20211111233223/Image-Processing-In-Java---Set-8-1.mp4)</video>

> **注意:**此代码不会在联机 ide 上运行，因为它需要驱动器中的映像。

本文由 **Pratik Agarwal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。