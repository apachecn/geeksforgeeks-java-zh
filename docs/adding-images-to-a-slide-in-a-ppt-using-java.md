# 使用 Java 向 PPT 中的幻灯片添加图像

> 原文:[https://www . geesforgeks . org/add-images-to-a-slide-in-a-PPT-using-Java/](https://www.geeksforgeeks.org/adding-images-to-a-slide-in-a-ppt-using-java/)

在 Java 中，使用 **createPicture()** 方法从[T3】XSLFSlideT5**、**图片可以添加到 PPT 中。现在电脑不明白，图片里有什么，所以在内部，这个方法接受字节数组格式的图像——>(一系列不可理解的随机数、字母、符号等。)像这样，agetrdydc5545#$^nhvgcffsfsfgsdf#@@？.0976*).](https://poi.apache.org/apidocs/4.0/org/apache/poi/xslf/usermodel/XSLFSlide.html)

**空幻灯片的语法**

```
XMLSlideShow ppt = new XMLSlideShow();
```

**创建幻灯片的语法**

```
XSLFSlide slide = ppt.createSlide();
```

下一个任务是读取我们希望插入的图像文件，然后使用 IOUtils.toByteArray() —> IOUtils 类将其转换为字节数组。

**使用 addPicture():** 将图像添加到演示文稿中

*   要添加的图片的字节数组格式(在代码中写成 byte[] photo)
*   静态变量，表示图像的文件格式。

**语法:**

```
int idx = ppt.addPicture(photo, XSLFPictureData.PICTURE_TYPE_PNG);
```

使用 createPicture()将图像插入幻灯片。

```
XSLFPictureShape pic = slide.createPicture(idx);
```

**<u>执行:</u>**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Adding Images to a slide in a PPT using java
import java.io.File;
import java.io.FileInputStream;
import java.io.FileOutputStream;
import java.io.IOException;

import org.apache.poi.util.IOUtils;
import org.apache.poi.xslf.usermodel.XMLSlideShow;
import org.apache.poi.xslf.usermodel.XSLFPictureData;
import org.apache.poi.xslf.usermodel.XSLFPictureShape;
import org.apache.poi.xslf.usermodel.XSLFSlide;

public class InsertingImage {

    public static void main(String args[])
        throws IOException
    {

        XMLSlideShow ppt = new XMLSlideShow();

        XSLFSlide slide = ppt.createSlide();

        File image
            = new File("C://Folder//codingisfun.png");

        byte[] photo = IOUtils.toByteArray(
            new FileInputStream(image));

        int idx = ppt.addPicture(
            photo, XSLFPictureData.PICTURE_TYPE_PNG);

        XSLFPictureShape pic = slide.createPicture(idx);

        // we are creating a file object
        File file = new File("insertingimg.pptx");
        FileOutputStream out = new FileOutputStream(file);

        // saving the changes to the file we created
        ppt.write(out);
        System.out.println("image is inserted");
        out.close();
    }
}
```

**编译和执行命令:**

```
$javac InsertingImage.java
$java InsertingImage
```

**输出:**

```
Reordering of the slides is done.
```

![](img/3ae50671213d82183111a9aed6f01239.png)