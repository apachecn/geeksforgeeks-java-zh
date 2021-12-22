# 如何在社交媒体安卓 App 中检索用户档案上的博客？

> 原文:[https://www . geesforgeks . org/如何检索-博客-用户档案-社交媒体-安卓-app/](https://www.geeksforgeeks.org/how-to-retrieve-blogs-on-user-profile-in-social-media-android-app/)

这是 **【在 Android Studio 上构建社交媒体 App】**教程的 **第 16 部分** ，我们将在本文中介绍以下功能:

*   We will retrieve blogs written by users on their profiles.
*   As mentioned earlier, we have added user data, such as email, name and profile picture, to the profile section.
*   We will also retrieve blogs written by current users in their profiles.
*   Let's look at the implementation of showing blogs written by current users.

### **分步实施**

**步骤 1:** **处理片段文件**

这里我们添加了**recycle view**来查看当前用户发布的博客。

## XML

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
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
                android:scaleType="fitXY"></ImageView>

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

            <androidx.recyclerview.widget.RecyclerView
                android:id="@+id/recyclerposts"
                android:layout_width="match_parent"
                android:layout_height="match_parent"
                android:layout_below="@id/linearLayout" />

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