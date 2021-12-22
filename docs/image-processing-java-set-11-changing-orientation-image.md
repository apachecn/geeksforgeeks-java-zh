# Java 中的图像处理|第 11 集(改变图像方向)

> 原文:[https://www . geesforgeks . org/image-processing-Java-set-11-changing-orientation-image/](https://www.geeksforgeeks.org/image-processing-java-set-11-changing-orientation-image/)

在本文中，我们将使用 opencv 来改变任何输入图像的方向，通过使用 OpenCV 库的 CORE.flip()方法。

主要思想是输入缓冲图像对象将被转换成垫子对象，然后将创建新的垫子对象，其中原始垫子对象值在方向修改后被放置。

为了实现上述结果，我们将需要一些 OpenCV 方法:

*   **[【GetRaster()](https://docs.oracle.com/javase/7/docs/api/java/awt/image/BufferedImage.html#getRaster())**–该方法返回一个可写栅格，该栅格又用于从输入图像中获取原始数据。
*   **[put(int row，int column，byte[] data)](http://docs.opencv.org/java/2.4.2/org/opencv/core/Mat.html#put(int, int, double...)) / [get(int row，int column，byte[]data)](http://docs.opencv.org/java/2.4.2/org/opencv/core/Mat.html#get(int, int, byte[]))**–用于将原始数据读取/写入 mat 对象。
*   **[翻转(mat mat1，mat mat2，int flip_value)](http://docs.opencv.org/java/2.4.2/org/opencv/core/Core.html#flip(org.opencv.core.Mat, org.opencv.core.Mat, int))**–mat 1 和 mat2 对应于输入和输出 mat 对象，flip_value 决定方向类型，flip _ value 可以是 0(沿 x 轴翻转)、1(沿 y 轴翻转)、-1(沿两个轴翻转)。

```
// Java program to illustrate orientation modification of image
import java.awt.image.BufferedImage;
import java.awt.image.DataBufferByte;
import java.io.File;
import java.io.IOException;
import javax.imageio.ImageIO;
import org.opencv.core.Core;
import org.opencv.core.CvType;
import org.opencv.core.Mat;

public class OrientingImage
{
  public static void main( String[] args ) throws IOException
  {
    // loads methods of the opencv library
    System.loadLibrary( Core.NATIVE_LIBRARY_NAME );

    // input buffered image object
    File input = new File("E:\\test.jpg");
    BufferedImage image = ImageIO.read(input);

    // converting buffered image object to mat object
    byte[] data = ((DataBufferByte) image.getRaster().getDataBuffer()).getData();
    Mat mat = new Mat(image.getHeight(),image.getWidth(),CvType.CV_8UC3);
    mat.put(0, 0, data);

    // creating a new mat object and putting the modified input mat object by using flip()
    Mat newMat = new Mat(image.getHeight(),image.getWidth(),CvType.CV_8UC3);
    Core.flip(mat, newMat, -1);  //flipping the image about both axis

    // converting the newly created mat object to buffered image object
    byte[] newData = new byte[newMat.rows()*newMat.cols()*(int)(newMat.elemSize())];
    newMat.get(0, 0, newData);
    BufferedImage image1 = new BufferedImage(newMat.cols(), newMat.rows(), 5);
    image1.getRaster().setDataElements(0,0,newMat.cols(),newMat.rows(),newData);

    File output = new File("E:\\result.jpg");
    ImageIO.write(image1, "jpg", output);
  }
}
```

输出:

```

test.jpg
![test](img/7b5664b34bd5d2465f58d76a038f0bce.png)

result.jpg
![result](img/e3889232b7accaa370567fd8729adcd6.png)

```

本文由 **[Pratik Agarwal](https://www.facebook.com/Pratik.Agarwal01)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。