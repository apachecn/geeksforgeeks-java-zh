# Java 中的图像处理–读写

> 原文:[https://www . geesforgeks . org/image-processing-in-Java-read-and-write/](https://www.geeksforgeeks.org/image-processing-in-java-read-and-write/)

Java 为 Java 中的图像实现了一种特殊类型的对象，称为 **BufferedImage** 。可以从几种不同的图像类型(即 BMP、HEIC 等)中读取 BufferedImage。).并非所有这些都由 ImageIO 本身支持，但是有插件来扩展 ImageIO 和其他库，如 Apache Imaging 和 JDeli。

在 Java 本身中，各种图像类型的所有复杂性都是隐藏的，我们只在 BufferedImage 上工作。Java 提供了对图像像素和颜色信息的直接访问，并允许转换和图像处理。

### **执行读写操作所需的类**:

**1。java.io.File:** 要读写图像文件，必须导入 File 类。这个类通常表示文件和目录路径名。

**2。java.io.IOException:** 为了处理错误，我们使用了 IOException 类。

**3。Java . awt . image . BufferedImage:**为了保存图像，我们创建了 BufferedImage 对象；我们使用 BufferedImage 类。该对象用于在内存中存储图像。

**4。****javax . imageio . ImageIO:**要执行映像读写操作，我们将导入 ImageIO 类。这个类有读写图像的静态方法。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java program to demonstrate read and write of image

import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
import javax.imageio.ImageIO;

public class MyImage {
    public static void main(String args[])
        throws IOException
    {
        // width of the image
        int width = 963;

        // height of the image
        int height = 640;

        // For storing image in RAM
        BufferedImage image = null;

        // READ IMAGE
        try {
            File input_file = new File(
                "C:/Users/hp/Desktop/Image Processing in Java/gfg-logo.png");

            // image file path create an object of
            // BufferedImage type and pass as parameter the
            // width,  height and image int
            // type. TYPE_INT_ARGB means that we are
            // representing the Alpha , Red, Green and Blue
            // component of the image pixel using 8 bit
            // integer value.

            image = new BufferedImage(
                width, height, BufferedImage.TYPE_INT_ARGB);

            // Reading input file
            image = ImageIO.read(input_file);

            System.out.println("Reading complete.");
        }
        catch (IOException e) {
            System.out.println("Error: " + e);
        }

        // WRITE IMAGE
        try {
            // Output file path
            File output_file = new File(
                "C:/Users/hp/Desktop/Image Processing in Java/gfg.png");

            // Writing to file taking type and path as
            ImageIO.write(image, "png", output_file);

            System.out.println("Writing complete.");
        }
        catch (IOException e) {
            System.out.println("Error: " + e);
        }
    } // main() ends here
} // class ends here
```

#### 输出–

<video class="wp-video-shortcode" id="video-139577-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20211109160033/Image-Processing-In-Java---Set-1-1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20211109160033/Image-Processing-In-Java---Set-1-1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20211109160033/Image-Processing-In-Java---Set-1-1.mp4)</video>

> **注意:**此代码不会在联机 IDE 上运行，因为它需要磁盘上的映像。

本文由 **Pratik Agarwal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。