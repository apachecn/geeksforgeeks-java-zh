# 使用 Java 在 PDF 中插入图像

> 原文:[https://www . geesforgeks . org/insert-images-in-a-pdf-using-Java/](https://www.geeksforgeeks.org/inserting-images-in-a-pdf-using-java/)

使用 Java 在 PDF 中插入图像可以通过使用名为 iText 的库来完成。iText 是一个 Java 库，最初是由 Bruno Lowagie 创建的，它允许创建 PDF、读取 PDF 和操作它们。

所需的库:

*   iText
*   日志库

直接从[这里](https://github.com/itext/itext7/releases/download/7.1.13/iText7-Core-7.1.13-only-jars.zip)下载 iText jar 文件&直接从[这里](https://repo1.maven.org/maven2/org/slf4j/slf4j-jdk14/1.7.2/slf4j-jdk14-1.7.2.jar)下载 slf4j jar 文件。要使用库，请将 jar 文件添加到系统的类路径中

**进场:**

1.  获取正在运行的 java 程序的当前工作目录，以便在同一位置创建 PDF 文件
2.  创建一个 PdfWriter 对象(来自 itextpdf 库)，将 pdf 文件写入给定的路径
3.  创建一个空的 PdF 文档对象
4.  从磁盘上的图像创建图像对象
5.  向文档添加图像

**实施:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.io.*;

// importing itext library packages
import com.itextpdf.io.image.*;
import com.itextpdf.kernel.pdf.*;
import com.itextpdf.layout.Document;
import com.itextpdf.layout.element.Image;

public class InsertImagePDF {
    public static void main(String[] args)
        throws IOException
    {
        String currDir = System.getProperty("user.dir");

        // Getting path of current working directory
        // to create the pdf file in the same directory of
        // the running java program
        String pdfPath = currDir + "/InsertImage.pdf";

        // Creating path for the new pdf file
        PdfWriter writer = new PdfWriter(pdfPath);

        // Creating PdfWriter object to write pdf file to
        // the path
        PdfDocument pdfDoc = new PdfDocument(writer);

        // Creating a PdfDocument object
        Document doc = new Document(pdfDoc);

        // Creating a Document object
        ImageData imageData = ImageDataFactory.create(
            currDir + "/image.jpg");

        // Creating imagedata from image on disk(from given
        // path) using ImageData object
        Image img = new Image(imageData);

        // Creating Image object from the imagedata
        doc.add(img);

        // Adding Image to the empty document
        doc.close();

        // Closing the document
        System.out.println(
            "Image added successfully and PDF file created!");
    }
}
```

**程序执行后:**

![](img/648a7c4be629f0f0487c2f83936b708f.png)