# 在社交媒体安卓应用中实现检索个人资料功能

> 原文:[https://www . geesforgeks . org/implement-retrieve-profile-data-functional-in-social-media-Android-app/](https://www.geeksforgeeks.org/implement-retrieve-profile-data-functionality-in-social-media-android-app/)

这是 **【在 Android Studio 上构建社交媒体 App】**教程的 **第 4 部分** ，我们将在本文中介绍以下功能:

*   We will retrieve the user's data from Firebase.
*   This is a simple clip. We will retrieve the user's data from the real-time database, such as name, email and profile picture, and display it in the text layout and image layout.
*   In the future, we will also display users' blogs on the profile page.

### **分步实施**

**步骤 1:** **处理片段文件**

在此页面上将检索用户的电子邮件、姓名和个人资料图片。我们还增加了[物料浮动动作按钮](https://www.geeksforgeeks.org/floating-action-button-fab-in-android-with-example/)来更新数据。导航到 **app > res >布局>fragment _ profile . XML**并将下面的代码添加到该文件中。下面是**fragment _ profile . XML**文件的代码。

## XML

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#F1EDED"
    tools:context=".ProfileFragment">

    <ScrollView
        android:layout_width="match_parent"
        android:layout_height="wrap_content">

        <RelativeLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content">

            <ImageView
                android:id="@+id/cavertv"
                android:layout_width="match_parent"
                android:layout_height="180dp"
                android:background="@color/colorPrimaryDark"
                android:scaleType="fitXY">
            </ImageView>

            <LinearLayout
                android:id="@+id/linearLayout"
                android:layout_width="match_parent"
                android:layout_height="120dp"
                android:layout_marginTop="100dp"
                android:orientation="horizontal">

                <ImageView
                    android:id="@+id/avatartv"
                    android:layout_width="120dp"
                    android:layout_height="120dp"
                    android:layout_gravity="center_horizontal"
                    android:layout_marginStart="20dp"
                    android:background="@color/colorPrimary"
                    android:padding="5dp"
                    android:src="@drawable/ic_images" />

                <LinearLayout
                    android:layout_width="match_parent"
                    android:layout_height="wrap_content"
                    android:background="#77000000"
                    android:orientation="vertical">

                    <TextView
                        android:id="@+id/nametv"
                        android:layout_width="match_parent"
                        android:layout_height="wrap_content"
                        android:layout_marginStart="5dp"
                        android:layout_marginLeft="5dp"
                        android:layout_marginTop="5dp"
                        android:textColor="@color/colorWhite"
                        android:textSize="25sp" />

                    <TextView
                        android:id="@+id/emailtv"
                        android:layout_width="match_parent"
                        android:layout_height="wrap_content"
                        android:layout_marginStart="5dp"
                        android:layout_marginLeft="5dp"
                        android:textColor="@color/colorWhite" />
                </LinearLayout>

            </LinearLayout>

        </RelativeLayout>

    </ScrollView>

    <com.google.android.material.floatingactionbutton.FloatingActionButton
        android:id="@+id/fab"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentEnd="true"
        android:layout_alignParentRight="true"
        android:layout_alignParentBottom="true"
        android:layout_margin="10dp"
        android:src="@drawable/ic_edit_white" />

</RelativeLayout>
```