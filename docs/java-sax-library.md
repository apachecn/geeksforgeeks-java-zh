# Java SAX 库

> 原文:[https://www.geeksforgeeks.org/java-sax-library/](https://www.geeksforgeeks.org/java-sax-library/)

**SAX(XML 的简单 API)**，是 Java 中最广泛采用的 XML API，被认为是事实上的标准。虽然它最初是一个专属于 Java 的库，但现在它是一个众所周知的应用编程接口，分布在各种编程语言中。这是一个开源项目，最近转到了 **SourceForge 项目基础设施**，这使得在大量 xml-dev 列表之外跟踪开放 SAX 问题变得更加容易。截至 2018 年 1 月 10 日的最新版本为 **SAX 2.0** 。它使用事件驱动的串行访问机制来访问 XML 文档，并且经常被需要访问 XML 文档的小程序使用，因为它是可用于解析 XML 文档的最快和最少内存消耗的应用编程接口。SAX 使用的机制使其独立于之前的元素，即它是**状态独立的**。

设置 **[DOM(文档对象模型)](https://www.geeksforgeeks.org/dom-document-object-model/)** 比设置 SAX 容易，SAX 比 DOM 更难可视化，因为它的解析器根据调用的事件解释 XML 项。这也意味着您不能返回到 SAX 解释的特定部分或重新排列它们。因此，**用户量大的应用程序应该使用 [DOM](https://www.geeksforgeeks.org/dom-document-object-model/) 而不是 SAX** 。

但是，有很多**的理由让你熟悉 SAX** ，即使你使用的是 DOM。下面是 SAX 相对于 [DOM](https://www.geeksforgeeks.org/dom-document-object-model/) : 的各种**优势**

*   **相同的错误处理:**SAX 和 [DOM](https://www.geeksforgeeks.org/dom-document-object-model/) 生成的异常种类相同。
*   **处理验证错误:**如果想在验证错误发生时抛出异常，需要了解 SAX 错误处理机制。
*   **转换现有数据:**在 [DOM](https://www.geeksforgeeks.org/dom-document-object-model/) 中，可以将现有数据集转换为 XML。但是为了能够实现它，您需要对 SAX 有一个基本的了解。

**为什么或者什么时候用 SAX？**

**SAX 使用事件模型结构**将数据转换或解析为 XML，只需修改现有的应用程序，在它读取数据时传递 SAX 事件。

**SAX 快速高效**，但其事件模型使其最适用于状态无关的过滤。当遇到元素标签和文本时，它会调用不同的方法。因此，只要处理是独立于状态的(这意味着它不依赖于之前的元素)，那么 SAX 就可以正常工作。

它不会像 [DOM](https://www.geeksforgeeks.org/dom-document-object-model/) 那样创建 XML 数据的内部表示(树形结构)，而是在读取数据时简单地将数据发送给应用程序，因此**消耗的内存更少**。

SAX 应用编程接口就像一个串行输入/输出流，因此强烈建议需要 XML 解析器的简单应用程序使用它。

**SAX 库中的类:**SAX 库中的类很少，使得解析工作非常容易。这些是:

1.  **HandlerBase:** 这个类为 DocumentHandler、ErrorHandler、DTDHandler 和 EntityResolver 提供默认实现:当用户没有指定处理程序时，解析器编写器可以使用这个提供默认实现，应用程序编写器可以将其子类化，以简化处理程序编写。
2.  **输入源**这个类允许 SAX 应用程序将关于输入源的信息封装在一个对象中，该对象可以包括公共标识符、系统标识符、字节流(可能具有指定的编码)和/或字符流。

**示例:**

***待解析的 XML 文件*** :

```
<?xml version="1.0"?>
<GFG>
    <contributor>
        <firstname>Baibhav</firstname>
        <lastname>Ojha</lastname>
    </contributor>
</GFG>
```

***Java 程序解析文件*** :

```
// Java Code to describe implementation
// of SAX library

import javax.xml.parsers.SAXParser;
import javax.xml.parsers.SAXParserFactory;
import org.xml.sax.Attributes;
import org.xml.sax.SAXException;
import org.xml.sax.helpers.DefaultHandler;

public class ReadXMLFile {

    public static void main(String argv[])
    {
        try {
            SAXParserFactory factory
                = SAXParserFactory.newInstance();
            SAXParser saxParser
                = factory.newSAXParser();

            DefaultHandler handler
                = new DefaultHandler() {

                      boolean bfname = false;
                      boolean blname = false;

                      public void startElement(String uri,
                                               String localName,
                                               String qName,
                                               Attributes attributes)
                          throws SAXException
                      {
                          if (qName.equalsIgnoreCase("firstname")) {
                              bfname = true;
                          }

                          if (qName.equalsIgnoreCase("lastname")) {
                              blname = true;
                          }
                      }

                      public void characters(char ch[],
                                             int start,
                                             int length)
                          throws SAXException
                      {
                          if (bfname) {
                              System.out.println("First Name : "
                                                 + new String(ch,
                                                              start,
                                                              length));
                              bfname = false;
                          }

                          if (blname) {
                              System.out.println("Last Name : "
                                                 + new String(ch,
                                                              start,
                                                              length));
                              blname = false;
                          }
                      }

                  };

            saxParser.parse("C:\\gfg.xml", handler);
        }
        catch (Exception e) {
            e.printStackTrace();
        }
    }
}
```