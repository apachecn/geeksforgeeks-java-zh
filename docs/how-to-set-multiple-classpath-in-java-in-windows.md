# 如何在 Windows 中用 Java 设置多个类路径？

> 原文:[https://www . geesforgeks . org/如何在 windows 中设置多个 java 类路径/](https://www.geeksforgeeks.org/how-to-set-multiple-classpath-in-java-in-windows/)

在 java 中，您必须在运行任何 JAVA 程序之前正确设置 PATH 和 CLASSPATH 变量。安装 JDK 后，下一步是在 Windows 系统环境变量中设置路径和类路径变量。类路径是一个环境变量，应用程序类加载器使用它来定位和加载类文件。

要设置类路径，有以下方法:

**A.** 可以在环境中永久设置 CLASSPATH。

*   点击窗口按钮，选择控制面板选择系统。

![](img/2f13771342855c05364befcce73563a3.png)

*   单击高级系统设置。

![](img/fe4d193d4ff99b655b7f40189f060b1c.png)

*   将会打开一个对话框。单击环境变量。

![](img/e508bc11beb19985f481b1bfc09ba6e4.png)

*   如果系统变量中已经存在类路径，单击编辑按钮，然后放一个分号(；)结尾。粘贴 MySQL-Connector Java.jar 文件的路径。
    否则点击新建按钮。

![](img/ff7dcc9b11b04c7781d3eede60096cb7.png)

*   将变量名键入为 CLASSPATH，变量值键入为 C:\ Program Files \ Java \ JRE 1.8 \ MySQL-Connector Java . jar；。；
    注:放；。；在类路径的末尾。

![](img/edaa9f89acc96e4beba5a8d2cb8ad2bc.png)

**B.** 可以使用命令提示符设置类路径:

*   安装最新的 JDK
*   打开命令提示符，输入命令:javac -version，显示如下错误。

![](img/4c1ec835e5bbaa3d3871e8e2f1249380.png)

*   设置路径:

> 设置路径= % path %<java installed="" directory=""></java>
> 
> 例如:设置路径= % path %c:\程序文件(x86)\Java\jdk1.7.0\bin

![](img/ef53264454d86a178057532d5145cce3.png)

*   现在设置类路径，即

> 设置类路径= % classpath %<java installed="" directory=""></java>
> 
> 例如:设置类路径= % classpath %c:\程序文件(x86)\Java\jdk1.7.0\lib\*。冲突

![](img/ca6915b67f78e264275543e572882d77.png)

*   测试 **javac** 和 **java** 命令

![](img/985c430743f771a5679eefe79897f1d4.png) ![](img/e24dcdd2e94eb6282aa409c1d044e9e1.png)

*   现在在 cmd 中键入 java

![](img/99202cff5da20cc70731c622c65f2350.png)

*   现在 java 已经为你准备好了。