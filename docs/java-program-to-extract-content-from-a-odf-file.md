# 从 ODF 文件中提取内容的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-program-to-extract-content-from-a-ODF-file/](https://www.geeksforgeeks.org/java-program-to-extract-content-from-a-odf-file/)

ODF 的全部是开放文档格式。它是一个国际标准家族，继承了常见的不推荐使用的特定于供应商的文档格式，如。医生。wpd，。xls。与其他格式相比，ODF 文档更小。从 TIKA 库中使用 OpenDocumentParser 类从 ODF 文件中提取内容。

**使用的方法:**

1.  **BodyContentHandler():** 它创建一个内容处理程序，将 XHTML 正文字符事件写入内部字符串缓冲区。
2.  **Metadata() :** 它构造新的、空的元数据。
3.  **ParseContext():** 它创建了一个 ParseContext 对象，用于将上下文信息传递给 Tika 解析器。
4.  **parse():** 实例化解析器对象，调用 parse 方法。

**以下是执行以下 java 代码所需的依赖项:**

```
tika-parsers-1.24.1.jar
commons-io-2.8.0.jar
slf4j-api-2.0.0-alpha0.jar
```

**实施:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program to Extract Content from a ODF file
import org.apache.tika.exception.TikaException;
import org.apache.tika.metadata.Metadata;
import org.apache.tika.parser.ParseContext;
import org.apache.tika.parser.odf.OpenDocumentParser;
import org.apache.tika.sax.BodyContentHandler;
import org.xml.sax.SAXException;

import java.io.File;
import java.io.FileInputStream;
import java.io.IOException;
import sun.security.util.Length;

public class OdfContentExtractor {
    public static void main(String[] args)
    {

        try {
            BodyContentHandler handler
                = new BodyContentHandler();

            Metadata metadata = new Metadata();

            // Here .odt is open document text format.
            FileInputStream inputstream
                = new FileInputStream(
                    new File("F:\\geeks.odt"));
            ParseContext parsecontent = new ParseContext();

            // Parsing the open document.
            OpenDocumentParser opendocumentparser
                = new OpenDocumentParser();

            // Passing the InputStream , ContentHandler,
            // Metadata , ParseContext to the parse method.
            opendocumentparser.parse(inputstream, handler,
                                     metadata,
                                     parsecontent);
            System.out.println("Content in the document :"
                               + handler.toString());

            // Displaying the metadata of the odf file.
            System.out.println("Metadata of the document:");
            String[] metaName = metadata.names();
            int l = metaName.length;
            for (int i = 0; i < l; i++) {
                System.out.println(
                    metaName[i]
                    + " : =  " + metadata.get(metaName[i]));
            }
        }
        catch (Exception e) {

            System.out.println(
                "failed to extract content due to " + e);
        }
    }
}
```

**输出:**

```
Content in the document :Geekforgeeks has a great content on DSA.

Metadata of the document:
date : =  2020-11-21T05:38:00Z
meta:paragraph-count : =  1
meta:word-count : =  6
meta:initial-author : =  Mohan Sai
initial-creator : =  Mohan Sai
dc:creator : =  Mohan Sai
generator : =  MicrosoftOffice/15.0 MicrosoftWord
Word-Count : =  6
dcterms:created : =  2020-11-21T05:36:00Z
dcterms:modified : =  2020-11-21T05:38:00Z
Last-Modified : =  2020-11-21T05:38:00Z
nbPara : =  1
Last-Save-Date : =  2020-11-21T05:38:00Z
meta:character-count : =  40
Paragraph-Count : =  1
meta:save-date : =  2020-11-21T05:38:00Z
modified : =  2020-11-21T05:38:00Z
Edit-Time : =  PT0S
nbCharacter : =  40
nbPage : =  1
nbWord : =  6
Content-Type : =  application/vnd.oasis.opendocument.text
creator : =  Mohan Sai
meta:author : =  Mohan Sai
meta:creation-date : =  2020-11-21T05:36:00Z
Creation-Date : =  2020-11-21T05:36:00Z
xmpTPg:NPages : =  1
Character Count : =  40
editing-cycles : =  3
Page-Count : =  1
Author : =  Mohan Sai
meta:page-count : =  1
```