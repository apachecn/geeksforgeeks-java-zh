# 从 PDF 中提取图像的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-extract-a-image-from-a-pdf/](https://www.geeksforgeeks.org/java-program-to-extract-a-image-from-a-pdf/)

使用 Java 从 PDF 中提取图像的程序。程序中需要导入外部 jar 文件。下面是相同的实现。

**算法:**

*   使用 APACHE PDF Box 模块提取图像。
*   使用文件 io 加载现有的 PDF 文档。
*   正在创建 PDFRenderer 类的对象。
*   使用 BufferedImage 类从 PDF 文档渲染图像。
*   将提取的图像写入新文件。
*   关闭文档。

**注意:** [执行](https://pdfbox.apache.org/download.html)操作需要下载外部文件。有关用于参考[的模块的更多文档。](https://pdfbox.apache.org/)

**实施:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Extracting  Images  from a PDF using java
import java.io.*;
import java.awt.image.BufferedImage;
import javax.imageio.ImageIO;
import org.apache.pdfbox.pdmodel.PDDocument;
import org.apache.pdfbox.rendering.PDFRenderer;

class GFG {
    public static void main(String[] args) throws Exception
    {
        // Existing PDF Document
        // to be Loaded using file io
        File newFile
            = new File("C:/Documents/GeeksforGeeks.pdf");
        PDDocument pdfDocument = PDDocument.load(newFile);

        // PDFRenderer class to be Instantiated
        // i.e. creating it's object
        PDFRenderer pdfRenderer
            = new PDFRenderer(pdfDocument);

        // Rendering an image
        // from the PDF document
        // using BufferedImage class
        BufferedImage img = pdfRenderer.renderImage(0);
        // Writing the extracted
        // image to a new file
        ImageIO.write(
            img, "JPEG",
            new File("C:/Documents/GeeksforGeeks.png"));
        System.out.println(
            "Image has been extracted successfully");

        // Closing the PDF document
        pdfDocument.close();
    }
}
```

**执行前 PDF:**

![](img/f934fee297d71c2fc6823918f3fa07f4.png)

**包含待提取图像的现有 PDF 文档**

**提取后的图像:**

![](img/dc2deee431033f762641779ce5722a77.png)

**从 PDF 文档中提取的图像**