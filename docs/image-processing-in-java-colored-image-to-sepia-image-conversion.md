# Java 中的图像处理——彩色图像到棕褐色图像的转换

> 原文:[https://www . geesforgeks . org/image-processing-in-Java-colored-image-to-sepia-image-conversion/](https://www.geeksforgeeks.org/image-processing-in-java-colored-image-to-sepia-image-conversion/)

**先决条件:**

*   [Java 中的图像处理–读写](https://www.geeksforgeeks.org/image-processing-in-java-read-and-write/)
*   [Java 中的图像处理–获取和设置像素](https://www.geeksforgeeks.org/image-processing-in-java-get-and-set-pixels/)
*   [Java 中的图像处理——彩色图像到灰度图像的转换](https://www.geeksforgeeks.org/image-processing-in-java-colored-image-to-grayscale-image-conversion/)
*   [Java 中的图像处理–彩色图像到负片图像的转换](https://www.geeksforgeeks.org/image-processing-in-java-colored-image-to-negative-image-conversion/)
*   [Java 中的图像处理–彩色到红绿蓝图像转换](https://www.geeksforgeeks.org/image-processing-in-java-colored-to-red-green-blue-image-conversion/)

在这一集里，我们将把彩色图像转换成棕褐色图像。在棕褐色图像中，图像的 alpha 分量将与原始图像相同(因为 Alpha 分量表示透明度)。尽管如此，RGB 还是会改变，这将通过以下公式来计算。

```
newRed = 0.393*R + 0.769*G + 0.189*B
newGreen = 0.349*R + 0.686*G + 0.168*B
newBlue = 0.272*R + 0.534*G + 0.131*B
```

如果这些输出值中的任何一个大于 255，只需将其设置为 255。这些特定值是微软推荐的棕褐色调的值。

#### **算法:**

1.  获取像素的 RGB 值。
2.  使用上述公式计算新红色、新绿色、新蓝色(取整数值)
3.  按照以下条件设置像素的新 RGB 值:
    *   如果新红> 255，那么 R = 255，否则 R =新红
    *   如果新绿> 255，那么 G = 255，否则 G =新绿
    *   如果新值> 255，则 B = 255，否则 B =新值
4.  用我们为像素计算的新值替换 R、G 和 B 的值。
5.  对图像的每个像素重复步骤 1 至步骤 4。

#### **实施:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// colored to sepia conversion

import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
import javax.imageio.ImageIO;

public class Sepia {
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

        // get width and height of the image
        int width = img.getWidth();
        int height = img.getHeight();

        // convert to sepia
        for (int y = 0; y < height; y++) {
            for (int x = 0; x < width; x++) {
                int p = img.getRGB(x, y);

                int a = (p >> 24) & 0xff;
                int R = (p >> 16) & 0xff;
                int G = (p >> 8) & 0xff;
                int B = p & 0xff;

                // calculate newRed, newGreen, newBlue
                int newRed = (int)(0.393 * R + 0.769 * G
                                   + 0.189 * B);
                int newGreen = (int)(0.349 * R + 0.686 * G
                                     + 0.168 * B);
                int newBlue = (int)(0.272 * R + 0.534 * G
                                    + 0.131 * B);

                // check condition
                if (newRed > 255)
                    R = 255;
                else
                    R = newRed;

                if (newGreen > 255)
                    G = 255;
                else
                    G = newGreen;

                if (newBlue > 255)
                    B = 255;
                else
                    B = newBlue;

                // set new RGB value
                p = (a << 24) | (R << 16) | (G << 8) | B;

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

#### 输出:

<video class="wp-video-shortcode" id="video-139846-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20211110113546/Image-Processing-In-Java---Set-6-1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20211110113546/Image-Processing-In-Java---Set-6-1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20211110113546/Image-Processing-In-Java---Set-6-1.mp4)</video>

> **注意**:这个代码不会在联机 IDE 上运行，因为它需要磁盘上的映像。

本文由 **Pratik Agarwal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。