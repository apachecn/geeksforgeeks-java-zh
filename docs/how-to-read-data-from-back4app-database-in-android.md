# 如何在安卓系统中从 Back4App 数据库读取数据？

> 原文:[https://www . geesforgeks . org/如何从 back4app 读取数据-安卓数据库/](https://www.geeksforgeeks.org/how-to-read-data-from-back4app-database-in-android/)

我们已经看到[在安卓应用中向 Back4App 数据库](https://www.geeksforgeeks.org/how-to-add-data-to-back4app-database-in-android/)添加数据。在本文中，我们将从我们的安卓应用程序中的数据库中读取这些数据。

### **本文我们要构建什么？**

我们将在之前的应用程序中创建一个新的屏幕，在这个屏幕中，我们将显示我们在[](https://www.geeksforgeeks.org/android-recyclerview/)<u>中的 **Back4App 数据库**中添加的数据。</u>

### <u>**分步实施**</u>

<u>**步骤 1:使用 activity_main.xml 文件**</u>

<u>转到 **activity_main.xml** 文件，再添加一个按钮，显示所有添加课程的列表。下面是代码片段，最后添加代码。</u>

## <u>可扩展标记语言</u>

```java
<!--Button for reading your course to Firebase-->
<Button
  android:id="@+id/idBtnReadCourse"
  android:layout_width="match_parent"
  android:layout_height="wrap_content"
  android:layout_margin="10dp"
  android:text="Read Course Details"
  android:textAllCaps="false" />
```

<u>下面是添加上述代码片段后 **activity_main.xml** 文件的更新代码。</u>

## <u>XML</u>

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <!--Edit text for getting course Name-->
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

    <!--Button for reading your course to Firebase-->
    <Button
        android:id="@+id/idBtnReadCourse"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="10dp"
        android:text="Read Course Details"
        android:textAllCaps="false" />

</LinearLayout>
```

<u>**步骤 2:现在我们将创建新的活动，用于在 recycle view**中显示 Firebase Firestore 的数据</u>

<u>要创建新活动，我们必须导航到**应用程序> java >您的应用程序的包名>右键单击包名>新建>空活动**并将您的活动命名为**家庭活动**并创建新活动。确保选择空活动。</u>

<u>**第三步:创建一个模态类来存储我们的数据。**</u>

<u>导航到**应用> java >你的应用的包名>右键点击>新建> java 类**并命名为 **CourseModal** 并添加下面的代码。代码中添加了注释，以便更详细地了解。</u>

 <u>## 爪哇

```java
public class CourseModal {

    // variables for our course name,
    // description and duration.
    private String courseName;
    private String courseDescription;
    private String courseDuration;

    // constructor class.
    public CourseModal(String courseName, String courseDescription, String courseDuration) {
        this.courseName = courseName;
        this.courseDescription = courseDescription;
        this.courseDuration = courseDuration;
    }

    // getter and setter methods.
    public String getCourseName() {
        return courseName;
    }

    public void setCourseName(String courseName) {
        this.courseName = courseName;
    }

    public String getCourseDescription() {
        return courseDescription;
    }

    public void setCourseDescription(String courseDescription) {
        this.courseDescription = courseDescription;
    }

    public String getCourseDuration() {
        return courseDuration;
    }

    public void setCourseDuration(String courseDuration) {
        this.courseDuration = courseDuration;
    }
}
```</u>