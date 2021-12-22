# Java 中使用 OpenCV 的图像处理|第 13 集(亮度增强)

> 原文:[https://www . geesforgeks . org/image-processing-using-opencv-Java-set-13-增亮/](https://www.geeksforgeeks.org/image-processing-using-opencv-java-set-13-brightness-enhancement/)

在本文中，我们将学习如何使用 OpenCv 库来增强图像的亮度。图像的亮度可以通过将图像的每个像素乘以α值，然后再加上β值来增强。
首先我们需要为 java 设置 OpenCV，我们建议同样使用 eclipse，因为它易于使用和设置。安装请参考这里的

**增亮所需的方法:**

1.  **convertTo(目的地，rtype，alpha，beta)** :此方法驻留在 OpenCv 的 Mat 包中。
    **语法:**

    ```
    sourceImage.convertTo(destination, rtype, alpha, beta);
    parameters:
    destination: is the destination image
    rtype:  is the desired output matrix type
    alpha:  is optional scale factor multiplied 
    to each pixel of source image
    beta:  it is optional beta value added to the scaled values.
    ```

2.  **imread()**–该方法用于将图像读取为由 OpenCV 渲染的 Mat 对象。
    **语法:**

```
Imgcodecs.imread(filename);
parameters:
filename: filename of the image file.If the image is 
in another directory whole path of image must be mentioned.

```

*   **imwrite()** – This method is used to write Mat objects to image file.
    **Syntax:**

    ```
    Imgcodecs.imwrite(filename, mat_img);
    parameters:
    filename: filename of the image file.If the image is 
    in another directory whole path of image must be mentioned.
    mat_img: resultant mat object.

    ```

    ```
    package ocv;

    import org.opencv.core.Core;
    import org.opencv.core.Mat;
    import org.opencv.imgcodecs.Imgcodecs;

    public class Main {
       static int width;
       static int height;
       static double alpha = 1;
       static double beta = 50;

       public static void main( String[] args ) {

          try {

             // For proper execution of native libraries
             // Core.NATIVE_LIBRARY_NAME must be loaded before
                // calling any of the opencv methods
             System.loadLibrary( Core.NATIVE_LIBRARY_NAME );

             // input image
             Mat source =  
              Imgcodecs.imread("E://input.jpg", Imgcodecs.CV_LOAD_IMAGE_COLOR);
             Mat destination = new Mat(source.rows(), source.cols(), source.type());

             // applying brightness enhacement
             source.convertTo(destination, -1, alpha, beta);

             // output image
             Imgcodecs.imwrite("E://output.jpg", destination);

          } catch (Exception e) {
             System.out.println("error: " + e.getMessage());
          }
       }
    }
    ```

    **注意:**该代码在联机 ide 中无法工作，因为它需要硬盘中的映像。

    **Input.jpg**

    ![](img/5703c92ebd7c14ae5e9b5a5c3cb9b9f5.png)

    Alpha = 1，Beta = 50

    **Output.jpg**

    ![](img/bb78cb4f36528d4690e36ca2861104ec.png)

    Alpha = 2，Beta = 50

    **Output.jpg**

    ![](img/c5415fd2f7c6317eaea5996bda9c2d4d.png)

    Alpha = 2，Beta = 25

    **Output.jpg**

    ![](img/dc4836acf8d0b07f12f3a69e3a4aed01.png)

    本文由 **[Pratik Agarwal](https://www.facebook.com/Pratik.Agarwal01)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。