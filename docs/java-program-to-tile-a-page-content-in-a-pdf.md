# 在 PDF 中平铺页面内容的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序转平铺-页面-pdf 中的内容/](https://www.geeksforgeeks.org/java-program-to-tile-a-page-content-in-a-pdf/)

为了平铺页面，我们将在这里使用 iText 开源库，因为 **iText** 是一个世界领先的 F/OSS PDF 库。为了在 PDF 中平铺页面内容，我们需要一些类 iText 库。以下是创建切片页面内容时使用的组件。

1.  **属于包**com.itextpdf.text.pdf**的 PdfReader 类，用于读取现有的 PDF 文档。**
2.  **PdfWriter** 类属于包**com.itextpdf.text.pdf，是**用来给文档写内容的。
3.  **属于 com.itextpdf.kernel.pdf 包的 PdfDocument** 类。通过创建这个类，您必须传递一个作者参数或读者参数。
4.  **文档**类属于 package com.itextpdf.layout，是 IText 中的核心类之一。**类用于创建实例。**
5.  **属于包**的矩形类**该类用于设置边框颜色、归档特定颜色、调整文本以适合矩形。**
6.  **属于**包的**类。pdfCanvas 用于将数据写入页面内容。*使用完毕后，调用*方法。这会节省一些内存。**
7.  使用 Close()方法关闭文档，因为这样会节省一些内存。

**程序:**

1.  [在工作区下载 iText 库](https://kb.itextpdf.com/home/it7kb/installation-guidelines/installing-itext-7-pdfocr-for-java-developers)。
2.  创建 Java 项目
3.  转到配置，将这个项目转换成 maven 项目
4.  将 depend*e*ncis 添加到 *pom.xml* 文件中。
5.  之后，创建一个 Java 类，并通过给出 PDF 文件的特定路径来构建这段代码。

**实施:**

平铺前的 PDF 页面内容如下:

![](img/0c377bf4abf37c24972bd912634cacf8.png)

**例**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Tile a Page Content in a PDF

// Importing input output classes
// Importing required classes from itextpdf
import com.itextpdf.kernel.geom.AffineTransform;
import com.itextpdf.kernel.geom.PageSize;
import com.itextpdf.kernel.geom.Rectangle;
import com.itextpdf.kernel.pdf.PdfDocument;
import com.itextpdf.kernel.pdf.PdfPage;
import com.itextpdf.kernel.pdf.PdfReader;
import com.itextpdf.kernel.pdf.PdfWriter;
import com.itextpdf.kernel.pdf.canvas.PdfCanvas;
import com.itextpdf.kernel.pdf.xobject.PdfFormXObject;
import java.io.*;

// Main class
class GFG {

    // Main driver method
    public static void main(String args[]) throws Exception
    {

        // Creating an object Pdf Writer
        String writing_pdf
            = "C:\Users\HP\Downloads\document.pdf";
        PdfWriter pdf_writer = new PdfWriter(writing_pdf);

        // Creating an object Pdf Reader
        String reading_pdf
            = "C:\Users\HP\Downloads\image.pdf";
        PdfReader pdf_reader = new PdfReader(reading_pdf);

        // Creating a PdfDocument objects by
        // creating both objects of PdfDocument class
        PdfDocument write = new PdfDocument(pdf_writer);
        PdfDocument read = new PdfDocument(pdf_reader);

        // Step 1: Opening a page from the existing PDF
        PdfPage origPage = read.getPage(1); // srcPdf= read

        // Step 2: Getting the page size
        Rectangle orig = origPage.getPageSizeWithRotation();

        // Step 3: Getting the size of the page
        PdfFormXObject pageCopy
            = origPage.copyAsFormXObject(write);

        // Step 4: Getting the size of the tile
        Rectangle Size = PageSize.A4.rotate();

        AffineTransform transformationMatrix
            = AffineTransform.getScaleInstance(
                Size.getWidth() / orig.getWidth() * 2f,
                Size.getHeight() / orig.getHeight() * 2f);

        // Step 5: Now creating the titles
        PdfPage page
            = write.addNewPage(PageSize.A4.rotate());

        // 1st tile
        PdfCanvas obj = new PdfCanvas(page);
        obj.concatMatrix(transformationMatrix);
        obj.addXObject(pageCopy, 0, -orig.getHeight() / 2f);

        // 2nd tile
        page = write.addNewPage(PageSize.A4.rotate());

        obj = new PdfCanvas(page);
        obj.concatMatrix(transformationMatrix);
        obj.addXObject(pageCopy, -orig.getWidth() / 2f,
                       -orig.getHeight() / 2f);

        // 3rd tile
        page = write.addNewPage(PageSize.A4.rotate());

        obj = new PdfCanvas(page);
        obj.concatMatrix(transformationMatrix);
        obj.addXObject(pageCopy, 0, 0);

        // 4th tile
        page = write.addNewPage(PageSize.A4.rotate());

        obj = new PdfCanvas(page);
        obj.concatMatrix(transformationMatrix);
        obj.addXObject(pageCopy, -orig.getWidth() / 2f, 0);

        // Step 6: Closing the pdfdocument objects
        // using close() methods, optimizing program by
        // releasing the memory space
        write.close();
        read.close();

        // Display message on console only illustrating
        // successful execution of the program
        System.out.println(
            "PDF document is created successfully.");
    }
}
```

**输出:**

输出控制台上的消息。

```
PDF document is created successfully.
```

此外，在指定位置打开保存的 PDF 后，您将看到该 PDF 中的页面内容平铺，新生成的 PDF 如下:

![](img/1ea3ab4e2d6683f3f4b2bd13ce0b3fb1.png)