# Java 中的图像处理|第 9 集(人脸检测)

> 原文:[https://www . geesforgeks . org/image-processing-Java-set-9-人脸检测/](https://www.geeksforgeeks.org/image-processing-java-set-9-face-detection/)

在[关于图像处理的入门集](https://www.geeksforgeeks.org/image-processing-java-set-1-read-write/)中，使用了 Java 的 BufferedImage 类来处理图像，BufferedImage 类的应用仅限于某些操作，即我们可以修改给定输入图像的 R、G、B 值，生成修改后的图像。对于复杂的图像处理，如人脸/物体检测，我们将在本文中使用 OpenCV 库。

首先我们需要为 Java 设置 OpenCV，我们推荐使用 [eclipse](http://docs.opencv.org/2.4/doc/tutorials/introduction/java_eclipse/java_eclipse.html) 进行同样的设置，因为它很容易使用和设置。

现在让我们了解一些人脸检测所需的方法。

1.  [**【级联分类器()**](https://en.wikipedia.org/wiki/Cascading_classifiers) :这个类用来加载训练好的级联人脸集合，我们将使用它来检测任何输入图像的人脸。
2.  **imcodecs . imread()/imcodecs . imwrite():**这些方法用于将图像作为 Mat 对象读写，这些对象由 OpenCV 渲染。
3.  **Imgproc.rectangle() :** 用于生成勾勒检测到的人脸的矩形框，它采用四个参数——input _ image、top_left_point、bottom_right_point、color_of_border。

```
// Java program to demonstrate face detection
package ocv;

import org.opencv.core.Core;
import org.opencv.core.Mat;
import org.opencv.core.MatOfRect;
import org.opencv.core.Point;
import org.opencv.core.Rect;
import org.opencv.core.Scalar;
import org.opencv.imgcodecs.Imgcodecs;
import org.opencv.imgproc.Imgproc;
import org.opencv.objdetect.CascadeClassifier;

public class FaceDetector
{
    public static void main(String[] args)
    {

        // For proper execution of native libraries
        // Core.NATIVE_LIBRARY_NAME must be loaded before
        // calling any of the opencv methods
        System.loadLibrary(Core.NATIVE_LIBRARY_NAME);

        // Face detector creation by loading source cascade xml file
        // using CascadeClassifier.
        // the file can be downloade from
        // https://github.com/opencv/opencv/blob/master/data/haarcascades/
        // haarcascade_frontalface_alt.xml
        // and must be placed in same directory of the source java file
        CascadeClassifier faceDetector = new CascadeClassifier();
        faceDetector.load("haarcascade_frontalface_alt.xml");

        // Input image
        Mat image = Imgcodecs.imread("E:\\input.jpg");

        // Detecting faces
        MatOfRect faceDetections = new MatOfRect();
        faceDetector.detectMultiScale(image, faceDetections);

        // Creating a rectangular box showing faces detected
        for (Rect rect : faceDetections.toArray())
        {
            Imgproc.rectangle(image, new Point(rect.x, rect.y),
             new Point(rect.x + rect.width, rect.y + rect.height),
                                           new Scalar(0, 255, 0));
        }

        // Saving the output image
        String filename = "Ouput.jpg";
        Imgcodecs.imwrite("E:\\"+filename, image);
    }
}
```

输出:

```

    Input.jpg                                         Output.jpg
![input](img/8c9610e01de7e20833acbe07eeac4375.png)                        ![ouput](img/855d7e84bfb0b7b46b5cb0995cf67f4a.png)

```

**代码说明:**

1.  它加载本机 OpenCV 库以使用 Java API。将创建一个 CascadeClassifier 实例，并向其传递从中加载分类器的文件的名称。
2.  接下来，在分类器上使用检测多尺度方法，将其传递给给给定的图像和纹理对象。
3.  MatOfRect 负责在处理后进行人脸检测。
4.  重复该过程以进行所有的面部检测，并用矩形标记图像，最后图像被保存为 output.png 文件。

程序的输出如下所示。这是我检测人脸前后的照片。
本文由 **[普拉蒂克·阿加瓦尔](https://www.facebook.com/Pratik.Agarwal01)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。