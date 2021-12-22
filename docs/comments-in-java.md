# Java 中的注释

> 原文:[https://www.geeksforgeeks.org/comments-in-java/](https://www.geeksforgeeks.org/comments-in-java/)

在程序中，注释通过放置所涉及的代码细节，参与使程序变得更具可读性，并且注释的正确使用使维护变得更容易，并且容易发现错误。编译代码时，编译器会忽略注释。

在 Java 中，有三种类型的注释:

1.  单行注释。
2.  多行注释。
3.  文件注释。

**单行评论**

初级程序员主要使用单行注释来描述代码功能。这是最容易输入的注释。
语法:

```
//Comments here( Text in this line only is considered as comment )

```

示例:

```
//Java program to show single line comments
class Scomment
{
    public static void main(String args[])
    { 
         // Single line comment here
         System.out.println("Single line comment above"); 
    }
}
```

**多行评论**

要在代码或复杂的代码片段中描述完整的方法，单行注释可能会写得很乏味，因为我们必须在每一行给出“//”。所以为了克服这一点，可以使用多行注释。
语法:

```
/*Comment starts
continues
continues
.
.
.
Commnent ends*/

```

示例:

```
//Java program to show multi line comments
class Scomment
{
    public static void main(String args[])
    { 
        System.out.println("Multi line comments below");
        /*Comment line 1
          Comment line 2 
          Comment line 3*/
    }
}
```

我们还可以使用如下所示的语法来完成单行注释:

```
/*Comment line 1*/

```

**文件注释**

这种类型的注释通常在为项目/软件包编写代码时使用，因为它有助于生成供参考的文档页面，该页面可用于获取有关所呈现的方法及其参数等的信息。
例如[http://docs . Oracle . com/javase/7/docs/API/Java/util/scanner . html](http://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html)是一个自动生成的文档页面，它是通过使用文档注释和用于处理注释的 javadoc 工具生成的。

**语法:**

```
/**Comment start
*
*tags are used in order to specify a parameter
*or method or heading
*HTML tags can also be used 
*such as <h1>
*
*comment ends*/

```

可用标签:

| 标签 | 描述 | 句法 |
| @作者 | 添加类的作者。 | @作者姓名-文本 |
| {@code} | 以代码字体显示文本，而不将文本解释为 HTML 标记或嵌套的 javadoc 标记。 | {@code text} |
| {@docRoot} | 表示从任何生成的页面到生成的文档根目录的相对路径。 | {@docRoot} |
| @已弃用 | 添加一条注释，指示不应再使用此应用编程接口。 | @已弃用的 deprecatedtext |
| @异常 | 在生成的文档中添加一个**抛出**副标题，带有类名和描述文本。 | @异常类名描述 |
| { @ Inheritadoc } | 从最近的**可继承类或可实现接口继承注释。** | 从直接超类继承注释。 |
| {@link} | 插入带有可见文本标签的内嵌链接，该链接指向被引用类的指定包、类或成员名称的文档。 | { @ link package.class #成员标签} |
| {@linkplain} | 与{@link}相同，只是链接的标签以纯文本而不是代码字体显示。 | { @ linkplain package.class #成员标签} |
| @param | 向“参数”部分添加一个带有指定参数名称和指定描述的参数。 | @param 参数-名称描述 |
| @返回 | 添加带有描述文本的“返回”部分。 | @返回描述 |
| @参见 | 添加带有指向引用的链接或文本条目的“另请参阅”标题。 | @参见参考资料 |
| @serial | 用于默认可序列化字段的文档注释中。 | @serial 字段-描述&#124;包含&#124;排除 |
| @序列化 | 记录由 writeObject()或 writeExternal()方法写入的数据。 | @ serial data-description |
| @ SerVices field | 记录对象流字段组件。 | @ serialField 字段-名称字段-类型字段-描述 |
| @自 | 向生成的文档中添加带有指定自文本的“自”标题。 | @自发布以来 |
| @抛出 | @throws 和@exception 标记是同义词。 | @抛出类名描述 |
| {@value} | 当在静态字段的文档注释中使用{@value}时，它会显示该常量的值。 | {@value package.class#field} |
| @版本 | 使用-version 选项时，在生成的文档中添加带有指定版本文本的“Version”副标题。 | @版本版本-文本 |

```
//Java program to illustrate frequently used 
// Comment tags

/**
* <h1>Find average of three numbers!</h1>
* The FindAvg program implements an application that
* simply calculates average of three integers and Prints
* the output on the screen.
*
* @author  Pratik Agarwal
* @version 1.0
* @since   2017-02-18
*/
public class FindAvg 
{
    /**
    * This method is used to find average of three integers.
    * @param numA This is the first parameter to findAvg method
    * @param numB  This is the second parameter to findAvg method
    * @param numC  This is the second parameter to findAvg method
    * @return int This returns average of numA, numB and numC.
    */
    public int findAvg(int numA, int numB, int numC) 
    {
        return (numA + numB + numC)/3;
    }

    /**
    * This is the main method which makes use of findAvg method.
    * @param args Unused.
    * @return Nothing.
    */

    public static void main(String args[]) 
    {
        FindAvg obj = new FindAvg();
        int avg = obj.findAvg(10, 20, 30);

        System.out.println("Average of 10, 20 and 30 is :" + avg);
    }
}
```

**输出:**

```
Average of 10, 20 and 30 is :20

```

对于以上代码文档可以使用工具‘Javadoc’生成:
Javadoc 可以通过在终端运行以下命令来使用。

```
javadoc FindAvg.java

```

本文由 **[Pratik Agarwal](https://www.facebook.com/Pratik.Agarwal01)** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。