# 如何在安卓系统中读取 Firebase Firestore 的数据？

> 原文:[https://www . geeksforgeeks . org/how-read-data-from-firebase-firestore-in-Android/](https://www.geeksforgeeks.org/how-to-read-data-from-firebase-firestore-in-android/)

在前一篇文章中，我们已经在[上看到了如何在安卓](https://www.geeksforgeeks.org/create-and-add-data-to-firebase-firestore-in-android/)中向 Firebase Firestore 添加数据。这是本系列的继续。现在我们将看到**如何在我们的 Firebase Firestore** 中读取这些添加的数据。现在我们将在安卓 [Firebase](https://www.geeksforgeeks.org/firebase-introduction/) 中实现这个读取数据。

### 我们将在本文中构建什么？

我们将在之前的应用程序中创建一个新的屏幕，在这个屏幕中，我们将显示我们在[回收视图](https://www.geeksforgeeks.org/android-recyclerview/)中的 **Firebase Firestore** 中添加的数据。我们将在我们的应用程序中读取 Firebase Firestore 的所有数据。

### **分步实施**

**步骤 1:使用 activity_main.xml 文件**

转到 **activity_main.xml** 文件，再添加一个按钮，显示所有添加课程的列表。下面是代码片段，最后添加代码。

## 可扩展标记语言

```java
<!--Button for showing the list of added courses-->
<Button
  android:id="@+id/idBtnViewCourses"
  android:layout_width="match_parent"
  android:layout_height="wrap_content"
  android:layout_margin="10dp"
  android:text="View Added Courses"
  android:textAllCaps="false" />
```

下面是添加上述代码片段后 **activity_main.xml** 文件的更新代码。

## XML

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <!--Edittext for getting course Name-->
    <EditText
        android:id="@+id/idEdtCourseName"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginStart="10dp"
        android:layout_marginTop="20dp"
        android:layout_marginEnd="10dp"
        android:hint="Course Name"
        android:importantForAutofill="no"
        android:inputType="text" />

    <!--Edittext for getting course Duration-->
    <EditText
        android:id="@+id/idEdtCourseDuration"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginStart="10dp"
        android:layout_marginTop="20dp"
        android:layout_marginEnd="10dp"
        android:hint="Course Duration in min"
        android:importantForAutofill="no"
        android:inputType="time" />

    <!--Edittext for getting course Description-->
    <EditText
        android:id="@+id/idEdtCourseDescription"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginStart="10dp"
        android:layout_marginTop="20dp"
        android:layout_marginEnd="10dp"
        android:hint="Course Description"
        android:importantForAutofill="no"
        android:inputType="text" />

    <!--Button for adding your course to Firebase-->
    <Button
        android:id="@+id/idBtnSubmitCourse"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="10dp"
        android:text="Submit Course Details"
        android:textAllCaps="false" />

    <!--Button for showing the list of added courses-->
    <Button
        android:id="@+id/idBtnViewCourses"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="10dp"
        android:text="View Added Courses"
        android:textAllCaps="false" />

</LinearLayout>
```

**步骤 2:现在我们将创建新的活动，用于在 recycle view**中显示 Firebase Firestore 的数据

要创建新的活动，我们必须导航到**应用程序> java >您的应用程序的包名>右键单击包名>新建>空活动**并将您的活动命名为**课程详细信息**并创建新的活动。确保选择空活动。

**第 3 步:现在我们将在课程详细信息活动**中进行 **的 XML 实现**

导航至 **app > res >布局>activity _ course _ details . XML**并添加以下代码。

## XML

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".CourseDetails">

    <!--Recycler view for displaying
        our data from Firestore-->
    <androidx.recyclerview.widget.RecyclerView
        android:id="@+id/idRVCourses"
        android:layout_width="match_parent"
        android:layout_height="match_parent" />

    <!--Progress bar for showing loading screen-->
    <ProgressBar
        android:id="@+id/idProgressBar"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_centerInParent="true" />

</RelativeLayout>
```