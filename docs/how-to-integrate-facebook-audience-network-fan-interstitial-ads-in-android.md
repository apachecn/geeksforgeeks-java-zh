# 如何在安卓系统中整合脸书观众网(FAN)间隙广告？

> 原文:[https://www . geesforgeks . org/如何整合-Facebook-受众-网络-粉丝-间隙-安卓广告/](https://www.geeksforgeeks.org/how-to-integrate-facebook-audience-network-fan-interstitial-ads-in-android/)

为了从[安卓](https://www.geeksforgeeks.org/android-app-development-fundamentals-for-beginners/)应用或游戏中赚钱，有很多方式，如应用内购买、赞助、广告等。但是还有一种从安卓应用中赚钱的流行方法是整合第三方广告，例如名为 [**的脸书观众网络。**](https://developers.facebook.com/products/audience-network/) 脸书观众网旨在帮助用户体验货币化。通过使用高价值的格式、高质量的广告、和创新的出版商工具，它有助于在保持人们参与的同时发展业务。

#### **为什么是脸书观众网？**

*   脸书观众网是谷歌广告业务货币化安卓或 IOS 应用的最佳选择之一。
*   最低支付额为 **$100**
*   广泛的广告格式
*   最大填充率
*   高 **eCPM** (每千分之一有效成本)
*   优质广告
*   个性化广告

#### **脸书观众网**业态

在脸书观众网络中，主要有五种灵活、高性能的格式

*   **原生:**你设计的适合应用的广告，无缝衔接
*   **间隙:**吸引眼球并成为体验一部分的全屏广告。
*   **横幅:**传统业态多种摆放。
*   [**有奖视频**](https://www.geeksforgeeks.org/how-to-integrate-facebook-audience-network-fan-rewarded-video-ads-in-android/) **:** 一款沉浸式、用户发起的视频广告，奖励用户观看。
*   **Playables:** 先试后买的广告体验，允许用户在安装前预览游戏。

在本文中，让我们将**脸书观众网络间隙广告**整合到安卓应用中。

**间隙广告:**间隙广告是覆盖 app 整个 UI 的全屏广告。间隙广告的 **eCPM** (每千分之一的有效成本)相对高于横幅广告，也导致更高的点击率(点击率)，从而从应用程序中获得更多收入。

![interstitial ads](img/b142c6c7b83488522d5e2b0dcfd4e34d.png)

### 方法

#### **第一步:创建**新的**项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目。](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)注意选择 **Java** 作为语言，虽然我们要用 Java 语言实现这个项目。

#### **第二步:**去编码区之前先做一些前置任务

*   转到**应用程序->RES->values->colors . XML**文件，为应用程序设置颜色。

## colors.xml

```java
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <color name="colorPrimary">#0F9D58</color>
    <color name="colorPrimaryDark">#0F9D58</color>
    <color name="colorAccent">#05af9b</color>
</resources>
```

*   转到**Gradle Scripts->**[**build . Gradle(模块:app)**](https://www.geeksforgeeks.org/android-build-gradle/) 部分，导入以下依赖项，点击上方弹出的“**立即同步”**。

> 实现' com.facebook.android:受众-网络-sdk:5。+'

*   转到 **app - >清单- > AndroidManifests.xml** 部分，允许“[互联网许可](https://www.geeksforgeeks.org/android-how-to-request-permissions-in-android-application/)”。

#### **第三步:设计 UI**

在 **activity_main.xml** 文件中只添加一个**按钮**，这样每当用户点击按钮时，就会播放奖励视频广告。

## activity_main.xml

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <!-- Button to Show Interstitial Ad By Clicking it -->
    <Button
        android:id="@+id/showInterBtn"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true"
        android:layout_margin="8dp"
        android:background="@color/colorPrimary"
        android:padding="16dp"
        android:text="Show  Interstitial "
        android:textColor="#ffff"
        android:textSize="20dp" />

</RelativeLayout>
```

#### **步骤 4:** 使用**MainActivity.java**文件

*   在类内打开**MainActivity.java**文件，首先创建**按钮**类的对象。

> //创建按钮类的对象
> 
> 按钮 showiinteresttialbtn

*   现在在**onCreate()****方法中，将这些对象与它们在 **activity_main.xml** 文件中给出的各自的 id 进行链接。**

> **//将这些对象与我们在 activity_main.xml 文件中给出的它们各自的 id 链接起来**
> 
> **showInterstitialBtn=（Button）findViewById（R.id.showInterBtn）;**

*   **现在里面 **onCreate()** 方法，初始化**脸书观众网 SDK。****

> **//初始化受众网络软件开发工具包**
> 
> **audiencenetworkads . initialize(this)；**

*   **在**MainActivity.java**类中创建一个**中间级**的对象**

> **//创建中间对象**
> 
> **州际足球协会；**

*   **接下来创建一个私有虚空**load quisity()**法外 **onCreate()** 法并定义它。**

> **私有空隙显示间隙()**
> 
> **{**
> 
> **//初始化中间对象**
> 
>  **//中间初始化构造函数接受 2 个参数
> 
> // 1)上下文
> 
> // 2)放置标识
> 
> fbInterstitialAd =新的 InterstitialAd(此处为“IMG _ 16 _ 9 _ APP _ INSTALL # YOUR _ PLACEMENT _ ID”)；
> 
> //加载 Ad
> 
> fbInterstitialAd.loadAd
> 
> }**

*   **初始化 SDK 后调用 **内部的**load 间质()**onCreate()**方法。**

> ****注:**将“IMG _ 16 _ 9 _ APP _ INSTALL # YOUR _ PLACEMENT _ ID”替换为自己的 placement id，即可展示真实广告。**

*   **接下来创建一个空**show 间质()** 法外 **onCreate()** 法我们后面称之为 show ad。**

> **void showiinteresttial_)**
> 
> **{**
> 
> **//检查广告是否已加载**
> 
> **if(fbinterinitialad . isadloaded())**
> 
> **{**
> 
> **//显示广告**
> 
> **fbinterinitialad . show()；**
> 
> **}**
> 
> **其他**
> 
> **{**
> 
> **//如果广告未加载，则加载广告**
> 
> **fbInterstitialAd.loadAd**
> 
>  **}
> 
> }**

*   **所以接下来的事情就是当用户点击一个 show ad 按钮时调用**【show 间质()】** 方法。**
*   **现在在 **onCreate()** 方法中创建一个**点击监听器**为按钮并调用**显示间隙()。****

> **//单击监听器显示间隙广告**
> 
> **showinterstate albtn . setnccklistener(新视图)。onclicklistener()& gt**
> 
> **@覆盖**
> 
> **公共空间单击(查看视图){ 0**
> 
> **showinteritial _)；**
> 
> **}**
> 
> **});**

*   **现在添加**间质广告监听器**为间质广告，这样用户就知道广告的状态了。要添加**间质监听器**打开 **加载间质()** 方法，并在 **之前添加下面的代码。****

> **//填隙式 AdListener**
> 
> **fbinterstitialad . setadlistener(新 interstate dlistener()=)**
> 
> **@覆盖**
> 
> **公共 void on interstialdisplayed(Ad Ad){ 0**
> 
> **//显示祝酒词**
> 
> **Toast . make text(main activity . this，“onInterstitialDisplayed”，Toast。LENGTH_SHORT)。show()；**
> 
> **}**
> 
> **@覆盖**
> 
> **公共 void on interstialized(Ad Ad){ 0**
> 
> **//显示祝酒词**
> 
> **Toast . make text(main activity . this，“onInterstitialDismissed”，Toast。LENGTH_SHORT)。show()；**
> 
>  **}
> 
> @覆盖
> 
> public void onerror(例如 aderor ader error)}
> 
> //显示祝酒词
> 
> 吐司. makeText(MainActivity.this，“onError”，吐司。LENGTH_SHORT)。show()；
> 
> }
> 
> @覆盖
> 
> 公共 void OnAdloaded(Ad Ad){ 0
> 
> //显示祝酒词
> 
> 吐司. makeText(MainActivity.this，“onAdLoaded”，吐司。LENGTH_SHORT)。show()；
> 
> }
> 
> @覆盖
> 
> 公共空间
> 
> //显示祝酒词
> 
> 吐司. makeText(MainActivity.this，“onAdClicked”，吐司。LENGTH_SHORT)。show()；
> 
> }
> 
> @覆盖
> 
> public 请参阅 onlogingimpression(ad)}
> 
> //显示祝酒词
> 
> Toast . make text(main activity . this，“onLoggingImpression”，Toast。LENGTH_SHORT)。show()；
> 
> }
> 
> });**

*   **而在**interstitallistener Override**方法中会显示一条[祝酒信息](https://www.geeksforgeeks.org/android-what-is-toast-and-how-to-use-it-with-examples/)，让用户知道广告的状态。以下是**MainActivity.java**文件的完整代码。**

## **MainActivity.java**

```java
package org.geeksforgeeks.project;

import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.Toast;
import androidx.appcompat.app.AppCompatActivity;
import com.facebook.ads.Ad;
import com.facebook.ads.AdError;
import com.facebook.ads.AudienceNetworkAds;
import com.facebook.ads.InterstitialAd;
import com.facebook.ads.InterstitialAdListener;

public class MainActivity extends AppCompatActivity {

    // Creating a object of Button class
    Button showInterstitialBtn;
    // creating object of InterstitialAd
    InterstitialAd fbInterstitialAd;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // link those objects with their respective id's that we have given in activity_main.xml file
        showInterstitialBtn = (Button) findViewById(R.id.showInterBtn);

        // initializing the Audience Network SDK
        AudienceNetworkAds.initialize(this);

        loadInterstitial();

        // click listener to show Interstitial  Ad
        showInterstitialBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                showInterstitial();
            }
        });
    }

    void showInterstitial() {
        // Checking If Ad is Loaded or Not
        if (fbInterstitialAd.isAdLoaded()) {
            // showing Ad
            fbInterstitialAd.show();
        } else {
            // Loading Ad If Ad is Not Loaded
            fbInterstitialAd.loadAd();
        }
    }

    private void loadInterstitial() {
        // initializing InterstitialAd Object
        // InterstitialAd Constructor Takes 2 Arguments
        // 1)Context
        // 2)Placement Id
        fbInterstitialAd = new InterstitialAd(this, "IMG_16_9_APP_INSTALL#YOUR_PLACEMENT_ID");

        // Interstitial AdListener
        fbInterstitialAd.setAdListener(new InterstitialAdListener() {
            @Override
            public void onInterstitialDisplayed(Ad ad) {
                // Showing Toast Message
                Toast.makeText(MainActivity.this, "onInterstitialDisplayed", Toast.LENGTH_SHORT).show();
            }

            @Override
            public void onInterstitialDismissed(Ad ad) {
                // Showing Toast Message
                Toast.makeText(MainActivity.this, "onInterstitialDismissed", Toast.LENGTH_SHORT).show();
            }

            @Override
            public void onError(Ad ad, AdError adError) {
                // Showing Toast Message
                Toast.makeText(MainActivity.this, "onError", Toast.LENGTH_SHORT).show();
            }

            @Override
            public void onAdLoaded(Ad ad) {
                // Showing Toast Message
                Toast.makeText(MainActivity.this, "onAdLoaded", Toast.LENGTH_SHORT).show();
            }

            @Override
            public void onAdClicked(Ad ad) {
                // Showing Toast Message
                Toast.makeText(MainActivity.this, "onAdClicked", Toast.LENGTH_SHORT).show();
            }

            @Override
            public void onLoggingImpression(Ad ad) {
                // Showing Toast Message
                Toast.makeText(MainActivity.this, "onLoggingImpression", Toast.LENGTH_SHORT).show();
            }
        });

        // loading Ad
        fbInterstitialAd.loadAd();
    }
}
```

#### ****输出:在仿真器上运行****

**<video class="wp-video-shortcode" id="video-476096-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200824180045/Facebook-Audience-Network-Interstitial-Ad.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200824180045/Facebook-Audience-Network-Interstitial-Ad.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200824180045/Facebook-Audience-Network-Interstitial-Ad.mp4)</video>**