# 在 OpenCV 中复制粘贴图像的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-copy-paste-in-image-open cv/](https://www.geeksforgeeks.org/java-program-to-copy-and-paste-an-image-in-opencv/)

OpenCV 是一个机器学习和开源的计算机视觉软件库，开发它的主要目的是使一个通用的媒介能够在商业企业中增加机器感知的使用，并加速计算机视觉应用的发展，它是企业采用和使用 OpenCV 的一个平稳而容易的过渡，因为它具有作为 BSD 许可产品的优势。

1.  OpenCV 库有 2000 多种高效优化的算法，其中还包含最先进的计算机视觉和经典的机器学习算法。
2.  这些算法主要用于执行各种任务，如人脸识别、物体识别、视频中人类活动的分类、物体三维模型的提取、图像中更高分辨率的提取、从图片数据库中查找相似图像等。
3.  OpenCV 还包含 Java、Python、C++、MATLAB 等各种语言接口，广泛支持 Linux、安卓、Windows、macOS。换句话说，它支持几乎所有流行的现有操作系统，因此在其用户列表中拥有大量受众。

**输入图像:**在本地目录下系统中本地目录下出现的样本图像。下面显示了从中提取图像以解释为多维数组的目录:

> 复制以下示例图像的本地目录:“C:/opencv/gfgarticleimg.png”

![](img/7e75c7d4ae2325130141080deabc34c9.png)

现在，当我们知道什么是 OpenCV 时，让我们尝试构建一个 java 程序，使我们能够用 OpenCV 复制和粘贴图像。

**算法:**

1.  导入 OpenCV 模块，加载核心库。
2.  从本地目录读取图像，并将其存储在 Matrix 对象中。
3.  将图像解释为多维矩阵。
4.  将这种多维结构写入某个不同的本地目录中进行存储，该目录是从提取它的地方指定的。复制了。

**示例:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Copy and Paste an image in OpenCV 

// Importing all input output java classes
import java.io.*;
// Importing OpenCV modules
import org.opencv.imgcodecs.Imgcodecs;
import org.opencv.core.Mat;
import org.opencv.core.Core;

class GFG {

    // Main driver method
    public static void main(String[] args)
    {

        // Loading OpenCV core library
        System.loadLibrary(Core.Native_Library_Name);

        // Read image from file and
        // Store it in a Matrix object
        String f = "C:/opencv/gfgarticleimg.png";

        // Creation of a Matrix object
        Mat m = Imgcodecs.imread(f);

        // Display message
        System.out.println(
            "Your Image has been Loaded.......");

        // Take another file for generating output image
        String f2 = "C:/opencv/gfgarticleimgResaved.png";

        // Write the image
        Imgcodecs.imwrite(f2, m);

        // Display message
        System.out.println(
            "congrats! your image has been saved........");
    }
}
```

**输出:**

> 粘贴以下示例的本地目录:“C:/opencv/gfgarticleimgresaved . png”

![](img/7e75c7d4ae2325130141080deabc34c9.png)