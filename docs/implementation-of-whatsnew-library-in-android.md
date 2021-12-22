# 安卓中 WhatsNew Library 的实现

> 原文:[https://www . geesforgeks . org/implementation-of-whatsnew-library in-Android/](https://www.geeksforgeeks.org/implementation-of-whatsnew-library-in-android/)

在本文中，我们将使用 WhatsNew 库展示该应用程序的重要内容。它可以被简单地认为是显示一些信息，如通知、说明、常见问题解答或条款和条件等。下面给出了一个示例 GIF，以了解我们将在本文中做什么。注意，我们将使用 **Java** 语言来实现这个项目。

![](img/9fdd8b89271c50d6cd02db64c73b2a14.png)

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:添加依赖和 mavenCentral()存储库**

导航到**渐变脚本>构建.渐变(模块:应用)**，并在依赖项部分添加以下依赖项。

> 实现' io . github . tonyl:what snew:0 . 1 . 7 '

将 **mavenCentral()** 存储库添加到您的构建文件中。将其添加到 allprojects{ }部分内存储库末尾的 root build.gradle 中。

> *所有项目{*
> 
> *存储库{*
> 
> *……*
> 
> *蓝色中心()*
> 
> *}*
> 
> *}*

添加这个依赖项后，同步您的项目，现在我们将开始实现它。

**步骤 3:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:gravity="center"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <Button
        android:id="@+id/whatsnew"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Whats New" />

</LinearLayout>
```

**第四步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。

> //这就是我们用来展示数据的
> 新 WhatsNewItem(“Firebase 身份验证”，“Firebase 身份验证服务”提供了易于使用的 UI 库和 SDK，用于向您的应用程序验证用户。”可画圆)，

以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.os.Bundle;
import android.view.View;
import android.widget.Button;

import androidx.appcompat.app.AppCompatActivity;

import io.github.tonnyl.whatsnew.WhatsNew;
import io.github.tonnyl.whatsnew.item.WhatsNewItem;
import io.github.tonnyl.whatsnew.util.PresentationOption;

public class MainActivity extends AppCompatActivity {

    Button button;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initialising layout
        button = findViewById(R.id.whatsnew);

        // click on button
        button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // creating a new Instance for 
                // showing Content using WhatsNew
                WhatsNew whatsNew = WhatsNew.newInstance(
                        // add as much item you want with 
                        // item title, description and image
                        new WhatsNewItem("Firebase Authentication", "Firebase Authentication service provides easy to use UI libraries and SDKs to authenticate users to your app.", R.drawable.circle),
                        new WhatsNewItem("Firebase Realtime Database", "The Firebase Realtime Database is a cloud based NoSQL database ", R.drawable.circle),
                        new WhatsNewItem("Cloud Firestore", " The cloud Firestore is a NoSQL document database that provides services like store, sync, and query through the application on a global scale", R.drawable.circle),
                        new WhatsNewItem("Firebase", " irebase is a product of Google which helps developers to build, manage, and grow their apps easily. It helps developers to build their apps faster and in a more secure way.", WhatsNewItem.NO_IMAGE_RES_ID)
                );
                whatsNew.setPresentationOption(PresentationOption.DEBUG);
                // on click present this layout
                whatsNew.presentAutomatically(MainActivity.this);
            }
        });
    }
}
```

**输出:**

<video class="wp-video-shortcode" id="video-603742-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210420234728/whatsnew.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210420234728/whatsnew.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210420234728/whatsnew.mp4)</video>