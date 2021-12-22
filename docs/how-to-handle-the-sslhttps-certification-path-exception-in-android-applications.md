# 如何处理安卓应用中的 SSL(HTTPs)认证路径异常？

> 原文:[https://www . geesforgeks . org/如何处理-sslhttps-认证-路径-安卓应用中的异常/](https://www.geeksforgeeks.org/how-to-handle-the-sslhttps-certification-path-exception-in-android-applications/)

如果您在连接到 SSL 服务器(HTTPS)的系统上运行由您创建的 Java 程序时没有被下面提到的异常刺痛，请在您的开发生涯中的某个时候为糟糕的体验做好准备。

> **异常** : PKIX 路径构建失败:sun . security . provider . cert path . suncertpathbuilder 异常:找不到指定目标的有效证书路径。

为了说明前面提到的问题，我们想强调几个场景，在这些场景中，您可以创建一个不同于安卓、Tomcat Server 和 JavaFX 的 Java 应用程序。

1.  为产品或公司开发机器人时。
2.  一个安卓应用程序，需要从服务器检索数据，并放在每个构建的资产文件夹中。
3.  根据您的需要创建文件解析器。
4.  我在从事计算机视觉项目。
5.  我在做机器学习项目。
6.  制作一个 Java 库

> **极客提示:**如果 Java 程序试图连接到受 SSL 保护的服务器(HTTPS 站点)，可能会出现上述异常。

利用 SSL 进行识别和加密的服务器会提供一个经过可信第三方(如 Verisign、GoDaddy 和其他一些公司)验证的证书。浏览器或 java 客户端可以使用该证书来确保它们与正确的站点(它声称是谁)通信，而不是与重定向的代理站点通信。如果我们使用浏览器访问一个站点，这个阶段是非常明显的，因为如果 SSL 证书不在浏览器的可信存储中，它将提示我们添加它，并且它将被添加。但是，当我们使用 Java 程序访问安全站点时，SSL 握手的这个阶段对用户来说是不可见的。

### 证书在哪里验证？

证书使用 JRE 的信任库进行验证。这个信任库位于 JDK 安装目录中，被 JAVA HOME($ JAVA HOME/JRE/lib/security)引用，通常被称为“cacerts”如果安全站点给出的证书存在于 JRE 的 trustStore 上，将创建一个 SSL 连接；但是，如果证书不存在，Java 将抛出一个异常(如上所述)，我们需要将该证书添加到 trustStore 来解决这个问题。

> **极客提示:**在使用“让我们加密”SSL 证书的服务器上，此问题更为常见。然而，因为我们是开源爱好者，我们会利用它，因为它是免费的。

该程序试图使用 OkHttp 对 https://httpbin.org/get URL 进行 API 调用(httpbin 是一个开源项目)，然后使用 Gson 将返回的 JSON 解析为 Java POJO 模型类对象。我创建了一个 JsonParserclass，使解析变得简单和通用。现在我们已经建立了在 Java 应用程序中可能出现这个问题的场景，让我们看看如何解决它。如前所述，该站点的 SSL 证书必须添加到 JRE 的信任库。要将 SSL 证书添加到 JRE 的信任库，请遵循下面概述的过程。

**第一步:获取站点的 SSL 证书**

第一步是获取站点的 SSL 证书。为此，启动终端并导航到证书保存位置。证书存储在桌面目录中。

```
openssl s_client -connect <site-url>:443 -servername <site-url> > <saved-certificate-file-name-we-want-to-give>
```

要退出，请在命令后按 ctrl + z。在任何文本编辑器中查看文件内容(如崇高)。它将包括颁发机构的名称、密钥、加密技术和其他信息。

**步骤#2:现在我们将证书(即 cacerts)放在密钥库中。运行以下命令完成此操作**

```
sudo keytool -import -keystore cacerts -alias <alias-name> -file <certificate-file-path>
```

它会问你两次密码，一次是 sudo，一次是密钥库。密钥库的默认密码是“changeit”。

> **注意:**如果输入“changeit”后提示输入新密码，请使用相同的“changeit”或更改密码并记住以备将来使用。

按照此命令，它将验证证书，然后提示您进行确认。当提示“信任此证书”时，输入“y”。最后，它将输出“证书已上载到密钥库。”