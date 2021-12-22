# Java |使用 cvtColor()将图像转换为灰度图像

> 原文:[https://www . geesforgeks . org/Java-转换-图像-灰度-使用-cvtcolor/](https://www.geeksforgeeks.org/java-converting-image-grayscale-using-cvtcolor/)

要使用 OpenCV 将彩色图像转换为灰度图像，我们将图像读入缓冲区，并将其转换为垫对象。

```java
Syntax:
File input = new File("digital_image_processing.jpg");
BufferedImage image = ImageIO.read(input);

```

使用 Imgproc 类中的方法 cvtColor()将图像从 RGB 转换为灰度格式。

> **语法:**
> Imgproc.cvtColor(源 mat，目的 mat1，Imgproc。COLOR _ RGB2GRAY)；
> **参数:**方法 cvtColor()取源图像矩阵、目的图像矩阵和颜色转换类型三个参数。

```java
// Java program to convert a color image to gray scale
import org.opencv.core.Core;
import org.opencv.core.Mat;
import org.opencv.imgcodecs.Imgcodecs;
import org.opencv.imgproc.Imgproc;

public class GeeksforGeeks {
    public static void main(String args[]) throws Exception
    {

        // To load  OpenCV core library
        System.loadLibrary(Core.NATIVE_LIBRARY_NAME);
        String input = "C:/opencv/GeeksforGeeks.jpg";

        // To Read the image
        Mat source = Imgcodecs.imread(input);

        // Creating the empty destination matrix
        Mat destination = new Mat();

        // Converting the image to gray scale and 
        // saving it in the dst matrix
        Imgproc.cvtColor(source, destination, Imgproc.COLOR_RGB2GRAY);

        // Writing the image
        Imgcodecs.imwrite("C:/opencv/GeeksforGeeks.jpg", destination);
        System.out.println("The image is successfully to Grayscale");
    }
}
```

```java
Input : 

Output :

```