# Java 11–特性和比较

> 原文:[https://www . geesforgeks . org/Java-11-功能和比较/](https://www.geeksforgeeks.org/java-11-features-and-comparison/)

每 6 个月，甲骨文就会发布新的 Java 版本。9 月份的 Java 11 版本甚至在发布之前就已经在计算机科学领域引起了很大的轰动，它宣称从现在开始 Java 将为商业用途付费。

以下文章将展示 JDK 11 的重要特性、增强功能和不推荐使用的特性。

### 重要变更和信息

*   运行小程序和 web 应用程序所需的部署堆栈已从 JDK 移除，这在 JDK 9 中已被否决。
*   由于部署堆栈不可用，支持的浏览器的整个部分已从支持的配置列表中删除。
*   自动更新已从 Windows 和 MacOS 的 JRE 安装中删除。
*   JavaFX 和 Java 任务控制现在可以单独下载。
*   不再提供法语、德语、意大利语、韩语、葡萄牙语(巴西)、西班牙语和瑞典语的 Java 语言翻译。
*   在这个版本中，不再提供 JRE 或服务器 JRE。只有 JDK 被录用了。
*   Windows 的更新打包格式已从 tar.gz 更改为。活力
*   macOS 的更新包格式已从。应用到。dmg

### 新特性和增强功能

1.  **新字符串方法:**
    *   **isBlank():** This is a boolean method. It just returns true when a string is empty and vice-versa.

        ```
        class GFG {
            public static void main(String args[])
            {
                String str1 = "";
                System.out.println(str1.isBlank());

                String str2 = "GeeksForGeeks";
                System.out.println(str2.isBlank());
            }
        }
        ```

        **输出:**

        ```
        True
        False

        ```

    *   **lines():** This method is to return a collection of strings which are divided by line terminators.

        ```
        class GFG {
            public static void main(String args[])
            {
                String str = "Geeks\nFor\nGeeks";
                System.out.println(str
                                       .lines()
                                       .collect(
                                           Collectors.toList()));
            }
        }
        ```

        **输出:**

        ```
        Geeks
        For
        Geeks

        ```

    *   **repeat(n):** Result is the concatenated string of original string repeated the number of times in the argument.

        ```
        class GFG {
            public static void main(String args[])
            {
                String str = "GeeksForGeeks";
                System.out.println(str.repeat(4));
            }
        }
        ```

        **输出:**

        ```
        GeeksForGeeksGeeksForGeeksGeeksForGeeksGeeksForGeeks

        ```

    *   **stripLeading():** It is used to remove the white-space which is in-front of the string

        ```
        class GFG {
            public static void main(String args[])
            {
                String str = " GeeksForGeeks";
                System.out.println(str.stripLeading());
            }
        }
        ```

        **输出:**

        ```
        GeeksForGeeks

        ```

    *   **stripTrailing():** It is used to remove the white-space which is in back of the string

        ```
        class GFG {
            public static void main(String args[])
            {
                String str = "GeeksForGeeks ";
                System.out.println(str.stripTrailing());
            }
        }
        ```

        **输出:**

        ```
        GeeksForGeeks

        ```

    *   **strip():** It is used to remove the white-spaces which are in-front and back of the string

        ```
        class GFG {
            public static void main(String args[])
            {
                String str = " GeeksForGeeks ";
                System.out.println(str.strip());
            }
        }
        ```

        **输出:**

        ```
        GeeksForGeeks

        ```

2.  **新文件方法**
    *   writeString():-这是在文件中写入一些内容。

        ```
        jshell>Files.writeString(Path.of(example.txt), "GeeksForGeeks!");
        ```

    *   readString():-用于读取文件的内容。

        ```
        jshell>Files.readString(Path.of(example.txt));

        Output: "GeeksForGeeks!"

        ```

    *   isSameFile():-这个方法用来知道两个路径是否定位同一个文件。

        ```
        jshell>Files.isSameFile(Path.of("example1.txt"), Path.of("example1.txt"));
        Output: true

        jshell>Files.isSameFile(Path.of("example2.txt"), Path.of("example1.txt"));
        Output: false

        ```

3.  **模式识别方法:**
    *   asmatchepredicate():-该方法类似于 Java 8 方法 asPredicate()。在 JDK 11 中引入，如果模式与输入字符串匹配，这个方法将创建一个谓词。

        ```
        jshell>var str = Pattern.compile("aba").asMatchPredicate();

        jshell>str.test(aabb);
        Output: false

        jshell>str.test(aba);
        Output: true

        ```

4.  **Epsilon Garbage Collector:**

    这处理内存分配，但没有实际的内存回收机制。一旦可用的 Java 堆耗尽，JVM 将关闭。
    其目标是:-

    *   性能试验
    *   记忆压力测试
    *   上次丢弃延迟改进
5.  **删除了 Java EE 和 CORBA 模块:**这些模块在 Java 9 中已被弃用，并声明在进一步的 JDK 版本中删除这些模块。
6.  **移除线程功能:** **停止(可投掷对象)**和**销毁()**对象已从 JDK 11 中移除，因为它们分别仅投掷**不支持**和**不支持方法错误**。除此之外，它们毫无用处。
7.  **时间单位转换:**该方法用于将给定时间转换为像日、月、年这样的单位，也用于时间。

    ```
    jshell>TimeUnit c = TimeUnit.DAYS;
    Output: DAYS

    jshell>c.convert(Duration.ofHours(24));
    Output: 1

    jshell>c.convert(Duration.ofHours(50));
    Output: 2

    ```

8.  **可选。isEmpty()** 如果任何对象的值为空，则该方法返回真，否则返回假。

    ```
    jshell>Optional str = Optional.empty();
    jshell>str.isEmpty();
    Output: true

    jshell>Optional str = Optional.of("TonyStark");
    jshell>str.isEmpty();
    Output: false

    ```

9.  **Local-Variable Syntax for Lambda Parameters**: JDK 11 allows ‘var’ to be used in lambda expressions. This was introduced to be consistent with local ‘var’ syntax of Java 10.

    ```
    //Variable used in lambda expression

    public class VarInLambdaExample {
      public static void main(String[] args) {
          IntStream.of(1, 2, 3, 5, 6, 7)
                   .filter((var i) -> i % 2 == 0)
                   .forEach(System.out::println);
      }
    }
    ```

    **输出:**

    ```
    2
    6

    ```

    ```
    //Variable without using lambda expression

    public class WithoutVarInLambdaExample {
      public static void main(String[] args) {
          IntStream.of(1, 2, 3, 5, 6, 7)
                   .filter(i -> i % 2 == 0)
                   .forEach(System.out::println);
      }
    }
    ```

    **输出:**

    ```
    2
    6

    ```

### 删除的功能和选项

1.  删除 com . sun . awt . awtutions 类
2.  从甲骨文 JDK 中删除露西达字体
3.  移除 appletviewer 启动器
4.  甲骨文 JDK 公司的 javax.imageio JPEG 插件不再支持带有 alpha 的图像
5.  删除 sun . misc . unsafe . define 类
6.  移除线程.销毁()和线程.停止(可抛出)方法
7.  删除 sun . nio . ch . disablesystemwideploppingfilelockcheck 属性
8.  删除 sun.locale.formatasdefault 属性
9.  移除 JVM-MANAGEMENT-MIB.mib
10.  删除简单网络管理协议代理
11.  删除 Java 部署技术
12.  将 JMC 从神谕 JDK 中移除
13.  从甲骨文 JDK 中删除 JavaFX
14.  JEP 320 删除 Java EE 和 CORBA 模块

### 不推荐使用的功能和选项

1.  线程池执行器不应指定终结依赖项
2.  JEP 335 反对纳斯霍恩的 JavaScript 引擎
3.  折旧-XX+积极选项
4.  对商业功能的过时支持
5.  不赞成基于流的通用文本方法
6.  JEP 336 反对 Pack200 工具和应用编程接口