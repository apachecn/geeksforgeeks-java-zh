# Java 中的图像处理–彩色到红绿蓝图像转换

> 原文:[https://www . geeksforgeeks . org/image-processing-in-Java-colored-to-red-green-blue-image-conversion/](https://www.geeksforgeeks.org/image-processing-in-java-colored-to-red-green-blue-image-conversion/)

**先决条件:**

*   [Java 中的图像处理–读写](https://www.geeksforgeeks.org/image-processing-in-java-read-and-write/)
*   [Java 中的图像处理–获取和设置像素](https://www.geeksforgeeks.org/image-processing-in-java-get-and-set-pixels/)
*   [Java 中的图像处理——彩色图像到灰度图像的转换](https://www.geeksforgeeks.org/image-processing-in-java-colored-image-to-grayscale-image-conversion/)
*   [Java 中的图像处理–彩色图像到负片图像的转换](https://www.geeksforgeeks.org/image-processing-in-java-colored-image-to-negative-image-conversion/)

在这一集里，我们将把彩色图像转换成具有红色效果、绿色效果或蓝色效果的图像。

**彩色图像–**彩色图像或 RGB 颜色模型是一种添加混合模型，其中红色、绿色和蓝色光以各种方式添加在一起，以再现广泛的颜色。

基本思想是获取每个坐标的像素值，然后保持所需的合成颜色像素值相同，并将其他两个设置为零。

### **转换为红色图像**

#### **算法:**

1.  获取像素的 RGB 值。
2.  按如下方式设置 RGB 值:
    *   接待员:没有变化
    *   高:设置为 0
    *   乙:设置为 0
3.  用步骤 2 中计算的值替换像素的 R、G 和 B 值。
4.  对图像的每个像素重复步骤 1 至步骤 3。

#### **实施:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate colored
// to red colored image conversion

import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
import javax.imageio.ImageIO;

public class RedImage {
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

        // get width and height
        int width = img.getWidth();
        int height = img.getHeight();

        // convert to red image
        for (int y = 0; y < height; y++) {
            for (int x = 0; x < width; x++) {
                int p = img.getRGB(x, y);

                int a = (p >> 24) & 0xff;
                int r = (p >> 16) & 0xff;

                // set new RGB keeping the r
                // value same as in original image
                // and setting g and b as 0.
                p = (a << 24) | (r << 16) | (0 << 8) | 0;

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

<video class="wp-video-shortcode" id="video-139823-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20211110112428/Image-Processing-In-Java---Set-5-1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20211110112428/Image-Processing-In-Java---Set-5-1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20211110112428/Image-Processing-In-Java---Set-5-1.mp4)</video>

> **注意:**此代码不会在联机 IDE 上运行，因为它需要磁盘上的映像。

### **转换为绿色图像**

#### 算法

1.  获取像素的 RGB 值。
2.  按如下方式设置 RGB 值:
    *   r:设置为 0
    *   高:没有变化
    *   乙:设置为 0
3.  用步骤 2 中计算的值替换像素的 R、G 和 B 值。
4.  对图像的每个像素重复步骤 1 至步骤 3。

#### **实施:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate colored
// to green coloured image conversion

import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
import javax.imageio.ImageIO;

public class GreenImage {
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

        // get width and height
        int width = img.getWidth();
        int height = img.getHeight();

        // convert to green image
        for (int y = 0; y < height; y++) {
            for (int x = 0; x < width; x++) {
                int p = img.getRGB(x, y);

                int a = (p >> 24) & 0xff;
                int g = (p >> 8) & 0xff;

                // set new RGB
                // keeping the g value same as in original
                // image and setting r and b as 0.
                p = (a << 24) | (0 << 16) | (g << 8) | 0;

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

<video class="wp-video-shortcode" id="video-139823-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20211110112505/Image-Processing-In-Java---Set-5B-1.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20211110112505/Image-Processing-In-Java---Set-5B-1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20211110112505/Image-Processing-In-Java---Set-5B-1.mp4)</video>

> **注意:**此代码不会在联机 IDE 上运行，因为它需要磁盘上的映像。

### **转换为蓝色图像**

#### **算法**

1.  获取像素的 RGB 值。
2.  按如下方式设置 RGB 值:
    *   r:设置为 0
    *   高:设置为 0
    *   乙:没有变化
3.  用步骤 2 中计算的值替换像素的 R、G 和 B 值。
4.  对图像的每个像素重复步骤 1 至步骤 3。

#### **实施**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate colored
// to blue coloured image conversion

import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
import javax.imageio.ImageIO;

public class BlueImage {
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

        // get width and height
        int width = img.getWidth();
        int height = img.getHeight();

        // convert to blue image
        for (int y = 0; y < height; y++) {
            for (int x = 0; x < width; x++) {
                int p = img.getRGB(x, y);

                int a = (p >> 24) & 0xff;
                int b = p & 0xff;

                // set new RGB
                // keeping the b value same as in original
                // image and setting r and g as 0.
                p = (a << 24) | (0 << 16) | (0 << 8) | b;

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

<video class="wp-video-shortcode" id="video-139823-3" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20211110112621/Image-Processing-In-Java---Set-5C-1.mp4?_=3">[https://media.geeksforgeeks.org/wp-content/uploads/20211110112621/Image-Processing-In-Java---Set-5C-1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20211110112621/Image-Processing-In-Java---Set-5C-1.mp4)</video>

> **注意:**此代码不会在联机 IDE 上运行，因为它需要磁盘上的映像。

本文由 **Pratik Agarwal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。