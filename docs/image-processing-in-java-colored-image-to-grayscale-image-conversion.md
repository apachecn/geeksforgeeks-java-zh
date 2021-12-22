# Java 中的图像处理——彩色图像到灰度图像的转换

> 原文:[https://www . geesforgeks . org/image-processing-in-Java-colored-image-to-grade-image-conversion/](https://www.geeksforgeeks.org/image-processing-in-java-colored-image-to-grayscale-image-conversion/)

**先决条件:**

*   [Java 中的图像处理–读写](https://www.geeksforgeeks.org/image-processing-in-java-read-and-write/)
*   [Java 中的图像处理–获取和设置像素](https://www.geeksforgeeks.org/image-processing-in-java-get-and-set-pixels/)

在本文中，我们将把彩色图像转换成灰度图像。

**RGB 颜色模型–**RGB 颜色模型是一种添加混合模型，其中红色、绿色和蓝色光以各种方式添加在一起，以再现广泛的颜色。

**灰度图像–**灰度图像是一种黑白或灰色单色图像，仅由灰色阴影组成。对比度从最弱的黑色到最强的白色不等。

通常，灰度图像对每个像素使用 8 位表示。通过使用 8 位，我们可以表示从 0 到 255 的值。因此，8 位表示的灰度图像将是一个矩阵，其值可以是 0 到 255 之间的任何值。0 表示黑色像素，255 表示白色像素，在两者之间会出现从黑色到白色的不同色调。

> **注意:**在灰度图像中，图像的 Alpha 分量将与原始图像相同，但 RGB 将发生变化，即所有三个 RGB 分量对于每个像素都具有相同的值。

#### **算法:**

1.  获取像素的 RGB 值。
2.  求 RGB 的平均值，即 Avg = (R+G+B)/3
3.  用步骤 2 中计算的平均值(平均值)替换像素的 R、G 和 B 值。
4.  对图像的每个像素重复步骤 1 至步骤 3。

#### **实施:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// colored to grayscale conversion

import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
import javax.imageio.ImageIO;

public class Grayscale {
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

        // get image's width and height
        int width = img.getWidth();
        int height = img.getHeight();

        // convert to grayscale
        for (int y = 0; y < height; y++) {
            for (int x = 0; x < width; x++) {

                // Here (x,y)denotes the coordinate of image
                // for modifying the pixel value.
                int p = img.getRGB(x, y);

                int a = (p >> 24) & 0xff;
                int r = (p >> 16) & 0xff;
                int g = (p >> 8) & 0xff;
                int b = p & 0xff;

                // calculate average
                int avg = (r + g + b) / 3;

                // replace RGB value with avg
                p = (a << 24) | (avg << 16) | (avg << 8)
                    | avg;

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

<video class="wp-video-shortcode" id="video-139698-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20211109160725/Image-Processing-In-Java---Set-3-1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20211109160725/Image-Processing-In-Java---Set-3-1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20211109160725/Image-Processing-In-Java---Set-3-1.mp4)</video>

> **注意:**此代码不会在联机 IDE 上运行，因为它需要磁盘上的映像。

本文由 **Pratik Agarwal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。