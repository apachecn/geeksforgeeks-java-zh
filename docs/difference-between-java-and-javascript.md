# 【Java 和 JavaScript 的区别

> 原文:[https://www . geesforgeks . org/Java 和 javascript 的区别/](https://www.geeksforgeeks.org/difference-between-java-and-javascript/)

在本文中，我们将了解 Java 和 Javascript，并看到 Java 和 Javascript 之间的显著区别。

[**JavaScript**](https://www.geeksforgeeks.org/javascript-tutorial/)**:**
JavaScript 是一种轻量级编程语言(“脚本语言”)，用于使网页具有交互性。它可以将动态文本插入到 HTML 中。JavaScript 也被称为浏览器的语言。JavaScript(JS)与 Java 不相似，也不相关。这两种语言都有类似于 C 的语法，并且广泛用于客户端和服务器端的 Web 应用程序，但是只有很少的相似之处。

**Javascript 的特性:**

*   JavaScript 最初是为 DOM 操作而创建的。早期的网站大多是静态的，在 JS 被创建后，动态网站被创建。
*   JS 中的函数是对象。它们可能像另一个对象一样具有属性和方法。它们可以作为参数在其他函数中传递。
*   可以处理日期和时间。
*   执行表单验证，尽管表单是使用 HTML 创建的。
*   不需要编译器。

**示例:**这是基本的 Javascript 示例。

## 超文本标记语言

```
<script>
    console.log("Welcome to GeeksforGeeks Learning");
</script>
```

**输出:**

```
Welcome to GeeksforGeeks Learning
```

[**Java**](https://www.geeksforgeeks.org/java/)**:**
Java 是一种面向对象的编程语言，拥有一个虚拟机平台，可以让你创建几乎在每个平台上运行的编译程序。Java 承诺，“只写一次，随处运行”。

**Java 的特点:**

*   **平台无关:**编译器将源代码转换为字节码，然后 JVM 执行编译器生成的字节码。这个字节码可以在任何平台上运行。
*   **面向对象编程语言:**用对象集合的方式组织程序是面向对象编程的一种方式，每一个对象都代表一个类的实例。面向对象的概念有四大支柱:
    *   抽象
    *   包装
    *   遗产
    *   多态性
*   **Simple:** Java 是简单的语言之一，因为它没有指针、运算符重载、多重继承、显式内存分配等复杂特性。
*   **健壮:** Java 语言健壮意味着可靠。它的开发方式是尽可能早地投入大量精力检查错误，这就是为什么 java 编译器能够检测到其他编程语言不容易检测到的错误。
*   **Secure:** 在 java 中，我们没有指针，所以我们不能访问越界数组，也就是说，如果我们尝试这样做，它会显示**arrayindexoofbound 异常**。
*   **分布式:**我们可以使用 java 编程语言创建分布式应用程序。远程方法调用和企业 Java Beans 用于在 Java 中创建分布式应用程序。
*   **多线程:** Java 支持多线程。这是一个 Java 特性，允许同时执行程序的两个或多个部分，以最大限度地利用 CPU。

**示例:**这是基本的 Java 程序。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.io.*;

class GFG {
    public static void main(String[] args)
    {
        System.out.println(
            "Welcome to GeeksforGeeks Learning");
    }
}
```

**输出:**

```
Welcome to GeeksforGeeks Learning
```

【Java 和 JavaScript 的区别:

<figure class="table">

| **Java** | **JavaScript** |
| --- | --- |
| Java 是一种强类型语言，变量必须首先声明才能在程序中使用。在 Java 中，变量的类型在编译时被检查。 | JavaScript 是一种弱类型的语言，有更宽松的语法和规则。 |
| Java 是一种面向对象的编程语言。 | JavaScript 是一种基于对象的脚本语言。 |
| Java 应用程序可以在任何虚拟机(JVM)或浏览器中运行。 | JavaScript 代码过去只能在浏览器中运行，但现在可以通过 Node.js 在服务器上运行。 |
| java 的对象是基于类的，即使我们不创建一个类也不能用 Java 编写任何程序。 | JavaScript 对象是基于原型的。 |
| Java 程序有文件扩展名”。并将源代码翻译成由 JVM(Java 虚拟机)执行的字节码。 | JavaScript 文件有文件扩展名”。js”而且它是被解释的但不是被编译的，每个浏览器都有 Javascript 解释器来执行 JS 代码。 |
| Java 是一种独立的语言。 | 包含在网页中并与其 HTML 内容集成。 |
| Java 有一种基于线程的并发方法。 | Javascript 有一种基于事件的并发方法。 |
| Java 支持多线程。 | Javascript 不支持多线程。 |

</figure>