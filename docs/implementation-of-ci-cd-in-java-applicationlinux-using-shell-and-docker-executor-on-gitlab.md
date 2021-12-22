# 在 GitLab 上使用 Shell 和 Docker 执行器实现 Java 应用(Linux)中的 CI/CD

> 原文:[https://www . geesforgeks . org/implementation-of-ci-CD-in-Java-application Linux-using-shell-and-docker-executor-on-git lab/](https://www.geeksforgeeks.org/implementation-of-ci-cd-in-java-applicationlinux-using-shell-and-docker-executor-on-gitlab/)

有很多执行器可以用 GitLab Runner 实现 CI/CD。然而，Shell 和 Docker 在其中更受欢迎，我们可以很容易地用这些 runners 配置一个存储库。可以根据资源的需求和可用性来选择这些跑步者。本文主要研究 Java Linux 应用程序的 Shell 和 Docker 执行程序，代码是用 bash 脚本编写的。应用程序可以使用 bash 脚本进行构建和测试。

**Shell Executor**:Shell Executor 是一个非常简单的执行器，有助于在机器上本地构建解决方案，其中安装了 GitLab Runner。在这种情况下，GitLab Runner 安装在 Linux Machine 上，因此需要在同一个系统中安装所需的软件。

**Docker Executor:** 它是一个功能强大的工具，包含很多软件，可以通过图像访问。这个执行器的优点是，我们不需要手动安装任何软件，一切都将通过 docker 来处理，所需的映像将从 docker hub 下载。但是，缺点是，出于安全目的，这种通信在某些组织中被阻止。所以，如果是这种情况，Shell Executor 是最好的选择。

**在 Shell 执行器上实现 Java:**

**要求:**这些是需要安装在 Linux 机器上的基本软件。但是，它可以根据编译脚本进行更改，如果需要，需要下载其他软件。

<figure class="table">

| software | describe |
| --- | --- |
| 饭桶 | This is the first requirement to submit changes on GitLab. It is a version control software that tracks the changes of file groups. |
| 【JDK】 | You need to install a specific version of JDK on the machine you are aiming at to build jar files. OpenJDK-8, for example |
| 阿帕奇人 Ant | This is a tool to help build the process and generate the project jar file while running this file. It contains more information about the project and adds this information to the jar. |

</figure>

**路径配置:**安装成功后，需要在机器中设置该安装软件的路径，如果没有设置的话。在机器上运行以下命令。

<figure class="table">

| Variables/files | path |
| --- | --- |
| 饭桶 | 在 Linux 机器中设置 Git 的路径，如果它已经没有设置的话。可以用**检查哪些 git**导出 Git =/usr/bin/Git |
| Java 语言（一种计算机语言，尤用于创建网站） | t29]是安藤吗 Java =/usr/bin/javat 31 gitlab-ci . yml | This file should be in the root directory of the project containing all CI/CD configurations (including software and script paths). Here, you can mention how this repository should work. Before adding this file to the root directory, you should check whether it is a valid yml file. |

</figure>

**GitLab Runner 设置**:按照以下步骤下载并配置 GitLab Runner。

**1。**在 Linux 机器上下载 GitLab Runner

```java
sudo curl -L --output /usr/local/bin/gitlab-runner https://gitlab-runner-downloads.s3.amazonaws.com/latest/binaries/gitlab-runner-linux-amd64
```

**2。使用以下命令授予其执行**的权限:

```java
sudo chmod +x /usr/local/bin/gitlab-runner
```

**3。使用以下命令创建一个 GitLab 配置项:**

```java
sudo useradd --comment 'GitLab Runner' --create-home gitlab-runner --shell /bin/bash
```

**4。使用以下命令安装并作为** **服务**运行:

```java
sudo gitlab-runner install --user=gitlab-runner --working-directory=/home/gitlab-runner
```

**5。使用以下命令启动 gitrab Runner**:

```java
sudo gitlab-runner start
```

**6。在使用以下命令注册存储库之前，停止 gitrab Runner**:

```java
sudo gitlab-runner stop
```

**7。**一旦 GitLab Runner 成功停止，在终端输入以下命令进行存储库注册。

```java
sudo gitlab-runner register
```

**8。**当你在 GitLab Runner 做仓库注册时，下面的问题必须回答。

*   **输入你的 GitLab 实例 URL:** 每个组织可以不同，格式会像 http://gitlab.example.com
*   **路径:**转到 GitLab 账号→选择要向 runner 注册的存储库→设置→ CI/CD →展开 Runner
*   **输入该跑步者的 gitlab-ci 令牌:**这将是注册时需要的每个项目的唯一令牌，并且可以找到
*   **路径:**转到 GitLab 账号→选择要向 runner 注册的存储库→设置→ CI/CD →展开 Runner
*   **输入该跑步者的 gitlab-ci 描述:**输入跑步者名称(任何名称)，这将帮助您记住哪个跑步者在跑步
*   **输入此跑步者的 gitlab-ci 标签:**当 yml 文件中有特定标签可用时，如果您想启动 gitlab 跑步者，这是可选的。
*   **进入执行器:**会有几个执行器的列表，输入 shell(因为 GitLab Runner 会运行我们的系统)

**9。**成功注册**后，**使用以下命令启动 GitLab Runner

```java
sudo gitlab-runner start
```

验证 GitLab Runner 已经注册了相应的存储库，并且 Runner 已经启动。转到 GitLab 帐户→选择要向 runner 注册的存储库→设置→配置项/光盘→展开 Runner，将出现一个绿色圆圈，并显示消息“Runner 已为此项目激活”。

**注意:**如果圆圈是灰色的，表示跑者还没有出发，再次出发。

### **Linux gitrab Runner 命令**

<figure class="table">

| 命令 | 描述 |
| --- | --- |
| sudo gitlab-runner 注册 | 向 GitLab Runner 注册该项目 |
| sudo gitlab-runner 注册 | 启动跑步者 |
| sudo gitlab-runner 停止 | 拦住跑者 |
| sudo gitlab runner 状态 | 了解 gitlab-runner 的状态 |
| sudo git lab-runner unregister–名称测试-runner | 注销一个项目的 runner，用你的 runner 名字替换测试 Runner，这个名字可以在 config.toml 文件(你的 gitlab-runner 所在的地方)中找到。 |
| sudo gitlab-runner unregister–URL http://gitlab . example . com/–token T3 n | 通过网址和令牌删除跑步者 |
| sudo git lab-跑步者取消注册-所有跑步者 | 注销所有跑步者 |
| sudo gitlab runner 重新启动 | 该命令停止，然后启动 GitLab Runner 服务 |
| sudo gitlab-runner 卸载 | 该命令停止并卸载作为服务运行的 GitLab Runner |
| sudo gitlab runner exec | 要查看可用执行者的列表，请运行 |
| sudo git lab-runner–帮助 | 通过执行以下命令来检查最近的命令列表 |
| sudo git lab-runner run–帮助 | 可以看到环境变量的名称 |
| sudo gitlab runner-除错 | 要在调试模式下运行命令 |
| sudo gitlab-runner exec shell | 要查看 shell 执行器所有可用选项的列表，请运行 |

</figure>

**。gitlab-ci.yml_shell Executor** :以下是的内容。外壳执行器模式下的 gitlab-ci.yml。但是，如果需要，可以根据需求进行更改。

```java
stages:
 - build
 - execute

build:
 stage: build
 script:  
   - ant -f build.xml

 artifacts:
   paths:
   - abc.jar

execute:
 stage: execute
 script:  
  - pwd  
  - cd scripts
  - chmod -R 777 *
  - pwd  
  - ./run.sh
```

**Java 在 Docker Executor 上的实现**:不需要手动安装任何软件，一切都会从 Docker 容器中取出。但是，您可以安装所需的软件，在 yml 文件中输入名称，也可以导出路径。要在 docker 执行器模式下运行 GitLab runner，请转到 GitLab Runner 设置(上图)，并选择 docker 而不是 shell。

**。gitlab-ci.yml_ Docker 执行器**:以下是的内容。docker 执行器模式下的 gitlab-ci.yml。但是，如果需要，可以更改它。

```java
image: ubuntu:latest

stages:
 - build
 - execute

before_script:
 - echo "Before script section"
 - apt-get update && apt-get -y install openjdk-8-jdk  && apt-get -y install ant

build:
 stage: build
 script:  
   - ant -f build.xml

 artifacts:
   paths:
   - abc.jar

execute:
 stage: execute
 script:  
  - pwd  
  - cd scripts
  - chmod -R 777 *
  - pwd  
  - ./runtest.sh
```