# 如何打造比特币追踪器安卓应用？

> 原文:[https://www . geesforgeks . org/如何构建比特币追踪器-安卓-app/](https://www.geeksforgeeks.org/how-to-build-a-bitcoin-tracker-android-app/)

在本文中，我们将在安卓系统中使用 Java 和 XML 构建一个比特币追踪器应用程序项目。该应用程序将使用比特币应用编程接口显示不同国家的比特币当前汇率。有许多免费的应用编程接口可供使用，对于这个项目，我们将使用 **Coinlayer 提供的应用编程接口。**API 会返回一个 JSON，我们会根据自己的需求进行解析。这个应用程序中只有一个活动。下面给出了一个 GIF 示例，以了解我们在本文中要做什么。

![Build a Bitcoin Tracker Android App Sample GIF](img/3a0bc673d57226927ea9eff036064b15.png)

### 逐步实施

**第一步:创建新项目**

在安卓工作室创建新项目请参考 [**【如何在安卓工作室创建/启动新项目】**](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/) 。注意选择 **Java** 作为编程语言。

**第二步:在进入编码部分之前，你首先要做一些前置任务**

**权限:**在 **AndroidManifest.xml** 文件中添加互联网权限

**在 themes.xml 文件中将样式更改为 NOACtionbar:**