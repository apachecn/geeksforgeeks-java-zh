# 用 Java 加密 PDF

> 原文:[https://www.geeksforgeeks.org/encrypt-pdf-using-java/](https://www.geeksforgeeks.org/encrypt-pdf-using-java/)

我们可以通过使用外部库 [PDFBox](https://pdfbox.apache.org/download.cgi) 使用 Java 对任何 PDF 进行加密。在 PDFBox 库中，有两个可用的类:标准保护策略和访问权限类。

**加密方式:**

通过使用 PDFBox 库，您将看到如何加密 PDF 文件。当用户希望自己的数据或文件处于保护模式时，使用加密。加密被用作加密文件的内置算法，这只是访问文件所需的凭证。

**访问权限**类用于通过分配访问权限来保护 PDF。此类将限制用户对 PDF 执行不同的操作。例子。打印、复印、修改等。

**StandardProtectionPolicy** 类用于对 PDF 文档应用密码。**T3】**

**PDFBox 的马文依赖:**

```
<dependency>
    <groupId>org.apache.pdfbox</groupId>
    <artifactId>pdfbox</artifactId>
    <version>2.0.21</version>
</dependency>
```

### 将 **密码应用于 PDF** 的步骤

**1。加载 PDF 文档:**

使用类 PDDocument 的 Load()静态方法(我们可以使用类名来访问)加载 PDF 文件。load()方法将接受 PDF 文件作为参数。

```
File f = new File("path_of_PDFfile");
PDDocument pdd = PDDocument.load(f);
```

**2。创建访问权限类的** **实例:**

```
AccessPermission ap = new AccessPermission();
```

**3。创建标准保护策略的** **实例:**

在 StandardProtectionPolicy 类的实例化过程中，传递所有者密码、用户密码和“ap”的 AccessPermission 类的对象。

```
StandardProtectionPolicy stpp = new StandardProtectionPolicy("Owner_pass" , "user_pass" , ap);
```

这里我们可以使用任何密码来加密 PDF 文件。

**示例:**这里将密码“abcd”视为用户和所有者密码。

```
StandardProtectionPolicy stpp = new StandardProtectionPolicy("abcd" , "abcd" , ap); 
```

**4。设置加密密钥的长度:**

使用 StandardProtectionPolicy 类的 setEncryptionKeyLength()方法设置加密密钥的长度。

```
stpp.setEncryptionKeyLength(128);
```

**5。设置权限:**

使用标准保护策略类的 setPermission()方法将权限设置为 PDF。您必须在 setPermission()方法中将 AccessPermissionclass 的对象作为参数传递。

```
stpp.setPermission(ap);
```

**6。保护 PDF 文件:**

使用 PDDocument 类的 Protect()方法保护 PDF 文件。在这里，我们必须将 StandardProtectionPolicy 类的对象作为参数传递。

```
pdd.protect(stpp);
```

**7。保存并关闭文档:**

最后，使用 PDDocument 类的 save()和 close()方法保存并关闭文档。

```
pdd.save("path_of_PDFfile");         // save the document
pdd.close();                        // close the document
```

## 爪哇

```
import org.apache.pdfbox.pdmodel.PDDocument;
import org.apache.pdfbox.pdmodel.encryption.AccessPermission;
import org.apache.pdfbox.pdmodel.encryption.StandardProtectionPolicy;
import java.io.File;
import java.io.IOException;

class PdfEncryption {
    public static void main(String[] args)
        throws IOException
    {
        // step 1\. Loading the pdf file
        File f = new File("D:\\demo.pdf");
        PDDocument pdd = PDDocument.load(f);

        // step 2.Creating instance of AccessPermission
        // class
        AccessPermission ap = new AccessPermission();

        // step 3\. Creating instance of
        // StandardProtectionPolicy
        StandardProtectionPolicy stpp
            = new StandardProtectionPolicy("abcd", "abcd", ap);

        // step 4\. Setting the length of Encryption key
        stpp.setEncryptionKeyLength(128);

        // step 5\. Setting the permission
        stpp.setPermissions(ap);

        // step 6\. Protecting the PDF file
        pdd.protect(stpp);

        // step 7\. Saving and closing the the PDF Document
        pdd.save("D:\\demo.pdf1");
        pdd.close();

        System.out.println("PDF Encrypted successfully...");
    }
}
```