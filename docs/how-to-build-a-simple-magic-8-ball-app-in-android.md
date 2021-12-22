# 如何在安卓中搭建一个简单的魔球 App？

> 原文:[https://www . geeksforgeeks . org/如何在安卓中构建一个简单的魔法 8 球应用/](https://www.geeksforgeeks.org/how-to-build-a-simple-magic-8-ball-app-in-android/)

在本文中，我们将使用安卓系统中的 **Java 和 XML** 构建一个**魔法 8 球应用程序**项目。该应用程序基于决策应用程序。在这个应用中，用户可以问球**他们应该做出什么决定**。球会随机回答是、否、不确定等类似的答案。这个应用程序中只有一个活动。下面给出了一个 GIF 示例，来了解一下我们在本文中要做什么。

![Build a Simple Magic 8 Ball App in Android Sample GIF](img/4a7d96b05b5b7c343fbe8cfddc827322.png)

### 逐步实施

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:在进入编码部分之前，你首先要做一些前置任务**

**球图像:**下面列出了所有的球图像。将它们保存在资源中的可绘制文件夹中。转到**应用程序>资源>可绘制**并粘贴以下文件:

*   [球 1](https://media.geeksforgeeks.org/wp-content/uploads/20210116143157/ball1-300x272.png)
*   [球 2](https://media.geeksforgeeks.org/wp-content/uploads/20210116143158/ball2-300x272.png)
*   [球 3](https://media.geeksforgeeks.org/wp-content/uploads/20210116143200/ball3-300x272.png)
*   [球 4](https://media.geeksforgeeks.org/wp-content/uploads/20210116143201/ball4-300x272.png)
*   [球 5](https://media.geeksforgeeks.org/wp-content/uploads/20210116143201/ball4-300x272.png)

**将样式更改为** **主题. xml 文件中的无功能栏:**