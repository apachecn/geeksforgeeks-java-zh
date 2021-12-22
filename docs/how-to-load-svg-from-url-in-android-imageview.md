# 如何在安卓 ImageView 中从 URL 加载 SVG？

> 原文:[https://www . geesforgeks . org/how-load-SVG-from-URL-in-Android-imageview/](https://www.geeksforgeeks.org/how-to-load-svg-from-url-in-android-imageview/)

可以看到，许多安卓应用程序要求使用高质量的图像，在缩放时不会模糊。所以我们必须使用高质量的图像。但是如果我们使用的是 PNG 图像，那么缩放后会变得模糊，因为 PNG 图像是由像素组成的，缩放后会降低质量。所以 SVG 图像更适合使用，因为 SVG 图像是由矢量组成的，即使缩放后也不会降低质量。现在我们将看看如何在我们的安卓应用程序中从其网址加载 SVG。

### 从网址加载静止图像的步骤

**第一步:新建安卓工作室项目**

创建新的安卓工作室项目只需点击**文件>新建>新项目**。确保选择你的语言作为 **JAVA** 。你可以参考[如何创建](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/) [新安卓工作室项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)这个帖子。

**步骤 2:在进入编码部分之前，在你的构建中添加这两个依赖项**

转到**梯度脚本>构建.梯度(模块:应用)**部分，添加以下依赖项，并点击上面弹出的“**立即同步**”。添加这两个依赖项。

> *   Is' com'. -Professional football team. okhttp3:okhttp:3。 10 .0‘
> *   Is' com'. Pixar city. Sharp: Library: 1.1.0'

**第三步:现在我们将走向设计部分**

导航到**应用程序> res >布局> activity_main.xml** 。下面是**activity _ main . XML**文件的代码。

> **注意:**可绘制添加在 app > res >可绘制文件夹中。

## XML

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <ImageView
        android:id="@+id/imageview"
        android:layout_width="match_parent"
        android:layout_height="200dp"
        android:layout_centerHorizontal="true"
        android:layout_marginLeft="10dp"
        android:layout_marginTop="40dp"
        android:layout_marginRight="10dp"
        android:contentDescription="@string/app_name"
        android:src="@drawable/gfgimage" />

</RelativeLayout>
```

**第 4 步:现在创建一个新的 JAVA 类作为 Utils**

在这个 JAVA 类中，我们以字节流的形式从网址加载数据。sharp 库将转换这个字节流，并将 SVG 图像加载到我们的目标 [ImageView](https://www.geeksforgeeks.org/imageview-in-kotlin/) 中。要创建新的 JAVA 类，请导航到**应用程序> java >您的应用程序包名称> >右键单击它，然后单击它并单击新建> Java 类**。给你的 JAVA 类起一个名字。下面是**Utils.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java

```java
import android.content.Context;
import android.widget.ImageView;
import com.pixplicity.sharp.Sharp;
import java.io.IOException;
import java.io.InputStream;
import okhttp3.Cache;
import okhttp3.Call;
import okhttp3.Callback;
import okhttp3.OkHttpClient;
import okhttp3.Request;
import okhttp3.Response;

public class Utils {

    private static OkHttpClient httpClient;

    // this method is used to fetch svg and load it into target imageview.
    public static void fetchSvg(Context context, String url, final ImageView target) {
        if (httpClient == null) {
            httpClient = new OkHttpClient.Builder()
                    .cache(new Cache(context.getCacheDir(), 5 * 1024 * 1014))
                    .build();
        }

        // here we are making HTTP call to fetch data from URL.
        Request request = new Request.Builder().url(url).build();
        httpClient.newCall(request).enqueue(new Callback() {
            @Override
            public void onFailure(Call call, IOException e) {
                // we are adding a default image if we gets any error.
                target.setImageResource(R.drawable.gfgimage);
            }

            @Override
            public void onResponse(Call call, Response response) throws IOException {
                // sharp is a library which will load stream which we generated
                // from url in our target imageview.
                InputStream stream = response.body().byteStream();
                Sharp.loadInputStream(stream).into(target);
                stream.close();
            }
        });
    }
}
```