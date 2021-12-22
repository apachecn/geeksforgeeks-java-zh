# Java 中的图像处理|第 10 集(给图像添加水印)

> 原文:[https://www . geesforgeks . org/image-processing-Java-set-10-水印-image/](https://www.geeksforgeeks.org/image-processing-java-set-10-watermarking-image/)

我们强烈建议将以下帖子作为先决条件。

*   [Java 中的图像处理|集 1(读写)](https://www.geeksforgeeks.org/image-processing-java-set-1-read-write/)
*   [Java 中的图像处理|设置 2(获取和设置像素)](https://www.geeksforgeeks.org/image-processing-java-set-2-get-set-pixels/)

在这个集合中，我们将生成一个水印，并将其应用于输入图像。
为了生成文本并将其应用到图像中，我们将使用 [java.awt.Graphics](https://docs.oracle.com/javase/7/docs/api/java/awt/Graphics.html) 包。使用 [java.awt.Color](https://docs.oracle.com/javase/7/docs/api/java/awt/Color.html) 和 [java.awt.Font](https://docs.oracle.com/javase/7/docs/api/java/awt/Font.html) 类应用文本的字体和颜色。
代码中使用的一些方法:

*   [getGraphics()](https://docs.oracle.com/javase/7/docs/api/java/awt/image/BufferedImage.html#getGraphics())–这个方法在 BufferedImage 类中找到，它从图像文件中返回一个 2DGraphics 对象。
*   [drawImage(Image img，int x，int y，ImageObserver observer)](https://docs.oracle.com/javase/7/docs/api/java/awt/Graphics.html#drawImage(java.awt.Image,%20int,%20int,%20java.awt.Color,%20java.awt.image.ImageObserver))–x，y 位置指定图像左上角的位置。observer 参数通知应用程序对异步加载的图像的更新。观察者参数不经常被直接使用，BufferedImage 类也不需要它，所以它通常为空。
*   [set Font(Font f)](https://docs.oracle.com/javase/7/docs/api/java/awt/Graphics.html#setFont(java.awt.Font))–该方法在 awt 包的 Font 类中找到，构造函数以(FONT_TYPE，FONT_STYLE，FONT_SIZE)为参数。
*   [setColor(Color c)](https://docs.oracle.com/javase/7/docs/api/java/awt/Graphics.html#setColor(java.awt.Color))–该方法在 awt 包的 Color 类中找到，构造函数以(R，G，B，A)为参数。
*   [drawing(String str，int x，int y)](https://docs.oracle.com/javase/7/docs/api/java/awt/Graphics.html#drawString(java.lang.String,%20int,%20int))–Graphics 类中的 Fond 将字符串文本和位置坐标作为 x 和 y 作为参数。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java code for watermarking an image

// For setting color of the watermark text
import java.awt.Color;

// For setting font of the watermark text
import java.awt.Font;

import java.awt.Graphics;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;

import javax.imageio.ImageIO;

public class WaterMark
{
    public static void main(String[] args)
    {
        BufferedImage img = null;
        File f = null;

        // Read image
        try
        {
            f = new File("input.png");
            img = ImageIO.read(f);
        }
        catch(IOException e)
        {
            System.out.println(e);
        }

        // create BufferedImage object of same width and
        // height as of input image
        BufferedImage temp = new BufferedImage(img.getWidth(),
                    img.getHeight(), BufferedImage.TYPE_INT_RGB);

        // Create graphics object and add original
        // image to it
        Graphics graphics = temp.getGraphics();
        graphics.drawImage(img, 0, 0, null);

        // Set font for the watermark text
        graphics.setFont(new Font("Arial", Font.PLAIN, 80));
        graphics.setColor(new Color(255, 0, 0, 40));

        // Setting watermark text
        String watermark = "WaterMark generated";

        // Add the watermark text at (width/5, height/3)
        // location
        graphics.drawString(watermark, img.getWidth()/5,
                                   img.getHeight()/3);

        // releases any system resources that it is using
        graphics.dispose();

        f = new File("output.png");
        try
        {
            ImageIO.write(temp, "png", f);
        }
        catch (IOException e)
        {
            System.out.println(e);
        }
    }
}
```

**注意:**代码不会在联机 ide 上运行，因为它需要驱动器中的映像。
产量:

```java
input.jpg

output.jpg
```

本文由 [**Pratik Agarwal**](https://www.facebook.com/Pratik.Agarwal01) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。