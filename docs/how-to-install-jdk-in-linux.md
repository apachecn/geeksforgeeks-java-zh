# 如何在 Linux 中安装 JDK？

> 原文:[https://www.geeksforgeeks.org/how-to-install-jdk-in-linux/](https://www.geeksforgeeks.org/how-to-install-jdk-in-linux/)

[Java](https://www.geeksforgeeks.org/java-tutorial/) 是一种非常流行的通用编程语言，非常接近 flow Oop 的理论，可以在任何平台上独立运行，但是它的运行时环境依赖于平台[**JVM(Java Virtual Machine)**](https://www.geeksforgeeks.org/jvm-works-jvm-architecture/)又称。其首先将 Java 文件字节码和字节码解释为机器语言。这里我们将在基于 Debian 的 Ubuntu 操作系统中安装 JDK。

### **分步安装:**

**第一步**:打开浏览器，导航到[这个链接。](https://www.oracle.com/java/technologies/javase-downloads.html)

![How to Install JDK in Linux?](img/837b01493ea704c96b56a4c4ca59ec21.png)

**第二步**:向下滚动，点击 JDK 下载链接。

![How to Install JDK in Linux?](img/e2538ca3307dd4cd19a91978e5ff3888.png)

**第三步**:然后选择兼容文件。

![How to Install JDK in Linux?](img/df9e8edbfb7f0c692d0f18f7c697fa55.png)

点击链接后，他们会显示弹出窗口以确认他们的条款和条件，并点击下载按钮。

![How to Install JDK in Linux?](img/1f8872c4afc83db7f360141f10903088.png)

勾选并点击下载。

![How to Install JDK in Linux?](img/4b881b74a14f6b3da681e0efc0ce7ef9.png)

**第四步**:下载后导航到你的下载文件夹，打开终端，进入下载文件夹。

![How to Install JDK in Linux?](img/0d40af329655c5323549098105c79784.png)

**第 5 步:**键入命令。

```
sudo dpkg -i package_name
```

键入命令后，按 enter 键。

![How to Install JDK in Linux?](img/939928b621b00f4203e1597d101cefa5.png)

这个过程几乎不需要时间。

**第 6 步**:完成上述步骤后，进行下一步更新路径和备选方案。

```
sudo update-alternatives --install /usr/bin/java java /usr/lib/jvm/jdk-15.0.2/bin/java 1
```

![How to Install JDK in Linux?](img/a1246469cc6e02f2594d56cda1161220.png)

**输出:**

![](img/8b509a53e3bf174d53d75e6b1843810c.png)

**对于备选方案**:

```
sudo update-alternatives --install /usr/bin/javac javac /usr/lib/jvm/jdk-15.0.2/bin/javac 1
```

![How to Install JDK in Linux?](img/7bd126dfbbcecc5a928ce09d1c18725f.png)

**输出:**

![](img/1ff9470fdea666154519ce7c2f2ae182.png)

**第七步**:最后，Java JDK 安装成功。

检查 Java 安装是否正确。

![](img/bc36a0ed9aa5f1a8a51d1161606c82ff.png)

并检查 Javac 安装是否正确。

![How to Install JDK in Linux?](img/6b296cd2bc8f993771c199d79b075a58.png)