# 如何在安卓系统中从 IFSC 码获取银行详细信息？

> 原文:[https://www . geesforgeks . org/how-to-bank-details-from-ifsc-code-in-Android/](https://www.geeksforgeeks.org/how-to-get-bank-details-from-ifsc-code-in-android/)

许多应用程序，如电子商务应用程序，要求接受用户为其提供不同产品或服务或为其用户支付的费用。因此，这些应用程序要求用户输入支付的银行详细信息。在这个支付网关中，用户被要求添加他们的银行 IFSC 代码，以获得他们银行的详细信息。如此多的应用程序都有自己的功能，以至于在输入银行 IFSC 代码时，用户的银行详细信息(如银行地址、银行城市和其他常见信息)都是从该 IFSC 代码中提取的。因此，在本文中，我们将了解如何从安卓系统中的 IFSC 代码中获取常见的银行详细信息。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，其中我们将通过 [EditText](https://www.geeksforgeeks.org/edittext-widget-in-android-using-java-with-examples/) 从用户处获取 IFSC 代码，之后，用户必须点击一个简单的按钮来从该 IFSC 代码中获取数据，如银行地址、银行 MICR 代码、联系号码和其他详细信息。为了执行这个任务，我们将使用一个简单的应用编程接口，我们将把它添加到我们的应用程序中。该应用程序将从 API 向我们提供与银行相关的基本数据。下面是 GIF 图像，我们将在其中看到我们将在本文中构建的内容。注意，我们将使用 **Java** 语言来实现这个项目。

![ Get Bank Details from IFSC Code in Android Sample GIF](img/6137817b472a1a8c912446c3ed1c96d6.png)

### **分步实施**

**第一步:在安卓工作室创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:在你的 build.gradle 文件**中添加下面的依赖项

下面是凌空的依赖，我们将使用它从应用编程接口获取数据。要添加此依赖项，请导航至**应用程序>渐变脚本> build.gradle(应用程序)**，并在依赖项部分添加以下依赖项。

> 实现‘com . Android .凌空:凌空:1 . 1 . 1’

添加此依赖项后，同步您的项目，现在转向 XML 部分。

**步骤 3:使用 activity_main.xml 文件**

转到 **activity_main.xml** 文件，参考以下代码。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <!--heading text view-->
    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="20dp"
        android:text="IFSC Code Validator"
        android:textAlignment="center"
        android:textColor="@color/purple_500"
        android:textSize="30sp" />

    <!-- edit text for entering our IFSC code
         we are specifying input type as number 
         and we are also mentioning our input type
         as textcapCharacters because IFSC code is
         having all capital characters-->
    <EditText
        android:id="@+id/idedtIfscCode"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="20dp"
        android:hint="Enter IFSC code"
        android:importantForAutofill="no"
        android:inputType="textCapCharacters"
        android:maxLines="1"
        android:singleLine="true"
        android:textAllCaps="true" />

    <!--button to get the data from IFSC code-->
    <Button
        android:id="@+id/idBtnGetBankDetails"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_gravity="center_horizontal"
        android:layout_marginTop="50dp"
        android:text="Get Bank Details"
        android:textAllCaps="false" />

    <!--text view to display the 
        data received from IFSC code-->
    <TextView
        android:id="@+id/idTVBankDetails"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="20dp"
        android:padding="10dp"
        android:textAlignment="center"
        android:textAllCaps="false"
        android:textColor="@color/purple_500"
        android:textSize="15sp" />

</LinearLayout>
```