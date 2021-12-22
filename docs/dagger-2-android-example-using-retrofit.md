# 匕首 2 安卓使用改装示例

> 原文:[https://www . geesforgeks . org/dagger-2-Android-示例-使用-改装/](https://www.geeksforgeeks.org/dagger-2-android-example-using-retrofit/)

匕首 2 安卓实现更容易，它基于依赖注入架构。依赖注入是一种设计模式，它是面向对象编程的概念，在这种模式下，我们不会使用新的关键字(对于 Java)在类内创建另一个类的对象。相反，我们从外部提供所需的对象。它是一个完全静态的编译时依赖注入框架，适用于 Java 和 Android。它是由 Square 创建的早期版本的改编，现在由谷歌维护。注意，我们将使用 **Java** 语言来实现这个项目。

### **匕首 2 的理论部分**

*   **依赖项提供者:**依赖项是我们需要在类内部实例化的对象。我们不能在类中实例化一个类。向我们提供被称为依赖项的对象的人被称为依赖项提供者。dagger2 是您想要创建依赖项提供程序的类，它需要用 **@Module** 注释对其进行注释。
*   **依赖消费者:**依赖消费者是我们需要实例化对象的类。匕首会提供依赖，为此我们只需要用 **@Inject 标注对象声明即可。**
*   **组件:**我们的依赖项提供者和依赖项消费者之间的连接是通过一个接口提供的，该接口使用**@组件**对其进行注释。剩下的事情将由匕首完成。

### 例子

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:** **先去编码区之前你要做一些前置任务**

在进入编码部分之前，你首先要做一些前期工作。转到**应用程序>RES>values>colors . XML**部分，为您的应用程序设置颜色。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <color name="colorPrimary">#0F9D58</color>
    <color name="colorPrimaryDark">#0F9D58</color>
    <color name="colorAccent">#FF4081</color>
</resources>
```

转到**梯度脚本>构建.梯度(模块:应用)**部分，导入以下依赖项，并点击上面弹出的“**立即同步**”。

> //增加这两条线路是为了改造
> 
> 实现' com.squareup.retrofit2:改装:2.7.2 '
> 
> 实现' com . squareup . retro fit 2:converter-gson:2 . 7 . 2 '
> 
> //这两行是为匕首增加的
> 
> 实现' com.google .匕首:匕首:2.13 '
> 
> 注释处理器' com.google .匕首:匕首-编译器:2.13 '

转到**应用程序>清单>和**允许“互联网许可”部分。**下面是 **AndroidManifests.xml** 文件的代码。**

**第三步:设计 UI**

下面是 **activity_main.xml** 文件的代码。这将在 **app > src >主> res >布局文件夹**下。取决于不同的分辨率，有时我们可能需要在布局> hdpi 或布局> xhdpi 文件夹等下拥有它。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <ListView
        android:id="@+id/listViewCountries"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:background="@color/colorPrimaryDark"/>

</RelativeLayout>
```

**第 4 步:使用 Java 文件**

**App Module.java 文件:**

在改装(改装是 Java 和安卓的 REST 客户端)中，我们需要**上下文**对象。为了提供对象，这里我们将创建这个模块，它将为我们提供上下文。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.app.Application;
import javax.inject.Singleton;
import dagger.Module;
import dagger.Provides;

@Module
class AppModule {
    private Application mApplication;

    AppModule(Application mApplication) {
        this.mApplication = mApplication;
    }

    @Provides
    @Singleton
    Application provideApplication() {
        return mApplication;
    }
}
```

有了匕首，当我们只想要单个实例时，我们需要注释 **@Singleton。**

**API Module.java:**

对于改装，我们需要一堆东西。缓存、Gson、OkHttpClient 和改装本身。因此，我们将在本模块中定义这些对象的提供者。

*   **Gson:** 它是一个 Java 库，可以用来将 Java Objects 转换成它们的 JSON 表示。
*   **Okhttp:** 与 reflution 配合使用，reflution 是 REST 的一个出色的 API。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.app.Application;
import com.google.gson.FieldNamingPolicy;
import com.google.gson.Gson;
import com.google.gson.GsonBuilder;
import javax.inject.Singleton;
import dagger.Module;
import dagger.Provides;
import okhttp3.Cache;
import okhttp3.OkHttpClient;
import retrofit2.Retrofit;
import retrofit2.converter.gson.GsonConverterFactory;

@Module
class ApiModule {

    String mBaseUrl;

    ApiModule(String mBaseUrl) {
        this.mBaseUrl = mBaseUrl;
    }

    @Provides
    @Singleton
    Cache provideHttpCache(Application application) {
        int cacheSize = 10 * 1024 * 1024;
        Cache cache = new Cache(application.getCacheDir(), cacheSize);
        return cache;
    }

    @Provides
    @Singleton
    Gson provideGson() {
        GsonBuilder gsonBuilder = new GsonBuilder();
        gsonBuilder.setFieldNamingPolicy(FieldNamingPolicy.LOWER_CASE_WITH_UNDERSCORES);
        return gsonBuilder.create();
    }

    @Provides
    @Singleton
    OkHttpClient provideOkhttpClient(Cache cache) {
        OkHttpClient.Builder client = new OkHttpClient.Builder();
        client.cache(cache);
        return client.build();
    }

    @Provides
    @Singleton
    Retrofit provideRetrofit(Gson gson, OkHttpClient okHttpClient) {
        return new Retrofit.Builder()
                .addConverterFactory(GsonConverterFactory.create(gson))
                .baseUrl(mBaseUrl)
                .client(okHttpClient)
                .build();
    }
}
```

**建筑构件:ApiComponent.java**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import javax.inject.Singleton;
import dagger.Component;

@Singleton
@Component(modules = {AppModule.class, ApiModule.class})
public interface ApiComponent {
    void inject(MainActivity activity);
}
```

我们将注入主活动。我们还使用 **@Component** 注释定义了所有模块，正如我们在代码中看到的。

**MyApplication.java 档案:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.app.Application;

public class MyApplication extends Application {

    private ApiComponent mApiComponent;

    @Override
    public void onCreate() {
        super.onCreate();
        // https://restcountries.eu/rest/v2/all -> It will list all the country details
        mApiComponent = DaggerApiComponent.builder()
                .appModule(new AppModule(this))
                .apiModule(new ApiModule("https://restcountries.eu/rest/v2/"))
                .build();
    }

    public ApiComponent getNetComponent() {
        return mApiComponent;
    }
}
```