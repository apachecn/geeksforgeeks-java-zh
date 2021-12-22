# Java 中使用 OpenCV 的图像处理|第 15 集(锐度增强)

> 原文:[https://www . geesforgeks . org/image-processing-using-opencv-in-Java-set-14-锐度增强/](https://www.geeksforgeeks.org/image-processing-using-opencv-in-java-set-14-sharpness-enhancement/)

在本文中，我们将学习如何使用 OpenCv 库增强图像的清晰度。
为了增强清晰度，我们将使用[高斯滤波器](https://en.wikipedia.org/wiki/Gaussian_filter)。高斯滤波器降低了图像中的噪声，使其看起来更好(或更高的分辨率)。

首先，我们需要为 java 设置 OpenCV，我们建议同样使用 eclipse，因为它易于使用和设置。安装参考[http://docs . opencv . org/2.4/doc/教程/简介/Java _ eclipse/Java _ eclipse . html](http://docs.opencv.org/2.4/doc/tutorials/introduction/java_eclipse/java_eclipse.html)

锐度增强所需的方法。

1.  GaussianBlur(源，目标，新大小(0，0)，SigMax)–该方法驻留在 OpenCv 的 Imgproc 包中。
    **语法:**

```
Imgproc.GaussianBlur(source, destination, new Size(0, 0), sigmaX)
parameters:
*source* - source image
*destination* - destination image
*new Size(0, 0)* - Gaussian kernel size
*sigmaX* - Gaussian kernel standard deviation in X direction

```

*   addWeighted(InputArray src1，alpha，src2，beta，gamma，OutputArray dst) -这个方法驻留在 OpenCv 的 Core 包中。**语法:**

    ```
    Core.addWeighted(InputArray src1, alpha, src2, beta, gamma, OutputArray dst)
    parameters:
    *src1* - first input array
    *alpha* - weight of the first array elements
    *src2* - second input array of the same size and channel number as src1
    *beta* - weight of the second array elements
    *gamma* - scalar added to each sum
    *dst* - output array that has the same size and number of channels as the input arrays

    ```

    *   **imread()** -该方法用于将图像读取为由 OpenCV 渲染的 Mat 对象。
    **语法:**

    ```
    Imgcodecs.imread(filename);
    parameters:
    filename: filename of the image file.If the image is 
    in another directory whole path of image must be mentioned.

    ```

    *   **imwrite()** - This method is used to write Mat objects to image file.
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
    import org.opencv.core.Size;
    import org.opencv.imgcodecs.Imgcodecs;
    import org.opencv.imgproc.Imgproc;

    public class Main {
       public static void main( String[] args )
       {
          try{
             // For proper execution of native libraries
             // Core.NATIVE_LIBRARY_NAME must be loaded before
                // calling any of the opencv methods
             System.loadLibrary( Core.NATIVE_LIBRARY_NAME );

             // Input image
             Mat source =
             Imgcodecs.imread("E://input.jpg", Imgcodecs.CV_LOAD_IMAGE_COLOR);
             Mat destination = new Mat(source.rows(), source.cols(), source.type());

             // filtering
             Imgproc.GaussianBlur(source, destination, new Size(0, 0), 10);
             Core.addWeighted(source, 1.5, destination, -0.5, 0, destination);

             // writing output image
             Imgcodecs.imwrite("E://output.jpg", destination);
          }catch (Exception e) {
          }
       }
    }
    ```

    **注意:**该代码在联机 ide 中无法工作，因为它需要硬盘中的映像。

    输出:

    ```

    **input.jpg**

    **output.jpg**

    Try to notice minor improvement in resolution

    ```

    本文由 **[Pratik Agarwal](https://www.facebook.com/Pratik.Agarwal01)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](http://www.write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

    如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。