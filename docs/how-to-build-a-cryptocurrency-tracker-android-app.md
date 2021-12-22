# 如何打造密码货币追踪器安卓应用？

> 原文:[https://www . geesforgeks . org/how-to-build-a-crypto currency-tracker-Android-app/](https://www.geeksforgeeks.org/how-to-build-a-cryptocurrency-tracker-android-app/)

如今，加密货币的需求最大，许多人都在投资这些货币以获得高回报。许多网站和应用程序为我们提供了加密市场上不同加密货币的利率信息。在本文中，我们将构建一个类似的应用程序，其中我们将在 RecyclerView 中显示应用程序中不同加密货币的汇率。

![How-to-Build-a-Cryptocurrency-Tracker-Android-App](img/dddfc3acea67876004ac7300c1e62e66.png)

### **我们将在本应用程序中构建什么？**

我们将构建一个简单的应用程序，在这个程序中，我们将在我们的应用程序的[recycle view](https://www.geeksforgeeks.org/android-recyclerview/)中显示不同加密货币的汇率。下面是视频，我们将在其中看到我们将在本文中构建的内容。请注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-617882-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210609174905/20210609_174706.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210609174905/20210609_174706.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210609174905/20210609_174706.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:在进入编码部分之前，你首先要做一些前置任务**

转到**应用程序>RES>values>colors . XML**部分，为您的应用程序设置颜色。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<resources>
    <color name="purple_200">#0F9D58</color>
    <color name="purple_500">#0F9D58</color>
    <color name="purple_700">#0F9D58</color>
    <color name="teal_200">#0F9D58</color>
    <color name="teal_700">#FF018786</color>
    <color name="black">#FF000000</color>
    <color name="white">#FFFFFFFF</color>

    <color name="blac_shade_1">#292D36</color>
    <color name="black_shade_2">#272B33</color>
    <color name="black_shade_3">#22252D</color>
    <color name="dark_blue_shade">#021853</color>
    <color name="yellow">#ffa500</color>

</resources>
```

**第三步:在 build.gradle 文件**中添加凌空的依赖关系

转到**梯度脚本>构建.梯度(模块:应用)**部分，导入以下依赖项，并单击上面弹出窗口中的“**立即同步**”。

```java
// Volley library
implementation 'com.android.volley:volley:1.1.1'
```

**第四步:在 AndroidManifest.xml 文件**中添加互联网权限

导航到**应用程序> AndroidManifest.xml** 文件，并在其中添加下面一行代码。

## 可扩展标记语言

```java
<uses-permission android:name="android.permission.INTERNET" />
```

**第 5 步:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@color/blac_shade_1"
    tools:context=".MainActivity">

    <!--edit text for searching our currency-->
    <EditText
        android:id="@+id/idEdtCurrency"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="8dp"
        android:focusable="auto"
        android:hint="Search Currency"
        android:textColor="@color/white"
        android:textColorHint="@color/white" />

    <!--recycler view for displaying the list of currencies-->
    <androidx.recyclerview.widget.RecyclerView
        android:id="@+id/idRVcurrency"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:layout_below="@id/idEdtCurrency"
        tools:listitem="@layout/currency_rv_item" />

    <!--progress bar for loading indicator-->
    <ProgressBar
        android:id="@+id/idPBLoading"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true"
        android:visibility="gone" />

</RelativeLayout>
```

**第六步:创建一个新的 Java 文件来存储我们的数据**

我们必须将数据存储在一个模态类中，为此我们将创建一个新的 Java 类文件。创建这个文件。导航到**应用程序> java >你的应用程序的包名>右键单击它>新建> Java 类**选项，然后选择类并将你的文件命名为 CurrencyModal 并添加下面的代码。代码中添加了注释，以便更详细地了解。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
package com.gtappdevelopers.cryptotracker;

public class CurrencyModal {
    // variable for currency name,
      // currency symbol and price.
    private String name;
    private String symbol;
    private double price;

    public CurrencyModal(String name, String symbol, double price) {
        this.name = name;
        this.symbol = symbol;
        this.price = price;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getSymbol() {
        return symbol;
    }

    public void setSymbol(String symbol) {
        this.symbol = symbol;
    }

    public double getPrice() {
        return price;
    }

    public void setPrice(double price) {
        this.price = price;
    }
}
```

**第 7 步:为我们的回收视图**创建一个新的布局文件

导航至 **app > res >布局>右键单击>新建>布局文件**并将其命名为 **currency_rv_item** 并添加以下代码。代码中添加了注释，以便更详细地了解。下面的布局文件将用于显示我们的回收视图的每个项目。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<androidx.cardview.widget.CardView 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:id="@+id/idCVCurrency"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_margin="4dp"
    app:cardBackgroundColor="@color/black_shade_2"
    app:cardCornerRadius="4dp"
    app:cardElevation="3dp">

    <RelativeLayout
        android:id="@+id/idRLCurrency"
        android:layout_width="match_parent"
        android:layout_height="wrap_content">

        <!--text view for displaying symbol-->
        <TextView
            android:id="@+id/idTVSymbol"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_margin="2dp"
            android:layout_toStartOf="@id/idTVRate"
            android:layout_toLeftOf="@id/idTVRate"
            android:padding="3dp"
            android:text="Symbol"
            android:textColor="@color/white"
            android:textStyle="bold" />

        <!--text view for displaying currency name-->
        <TextView
            android:id="@+id/idTVName"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_below="@id/idTVSymbol"
            android:layout_margin="2dp"
            android:padding="3dp"
            android:text="Name"
            android:textColor="@color/white"
            android:textSize="13sp" />

        <!--text view for displaying currency rate-->
        <TextView
            android:id="@+id/idTVRate"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_alignParentEnd="true"
            android:layout_alignParentRight="true"
            android:layout_marginStart="2dp"
            android:layout_marginLeft="2dp"
            android:layout_marginTop="2dp"
            android:layout_marginEnd="3dp"
            android:layout_marginRight="3dp"
            android:layout_marginBottom="2dp"
            android:padding="3dp"
            android:text="123456"
            android:textColor="@color/white" />

    </RelativeLayout>

</androidx.cardview.widget.CardView>
```