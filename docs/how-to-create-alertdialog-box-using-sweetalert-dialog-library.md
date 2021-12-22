# 如何使用 SweetAlert 对话框库创建报警对话框？

> 原文:[https://www . geesforgeks . org/how-create-alertdialog-box-use-sweet alert-dialog-library/](https://www.geeksforgeeks.org/how-to-create-alertdialog-box-using-sweetalert-dialog-library/)

在本文中，我们将学习如何使用 SweetAlert Dialog Library 在应用程序中添加自定义[](https://www.geeksforgeeks.org/android-alert-dialog-box-and-how-to-create-it/)**报警对话框。它是一个弹出框，响应用户的任何操作而出现。 **AlertBox** 在验证方面非常有用，可以用来显示确认消息。假设如果用户没有保存更改就按了后退按钮，那么为了警告，可以使用它。当交易在支付应用中完成时，可以向用户显示一个简短的**对话框**，描述交易的状态。
**优势:**** 

*   **它为我们提供了非常好的用户界面，使得用户体验非常好。**
*   **它使工作变得非常容易，所以它被用在需要创建整个布局的 [**【自定义对话框】**](https://www.geeksforgeeks.org/how-to-create-a-custom-alertdialog-in-android/) 上。**
*   **它为对话框提供了许多不同类型的布局。**

****方法:**
**步骤 1:** 在 [**build.gradle**](https://www.geeksforgeeks.org/android-build-gradle/) 文件中添加支持库，并在依赖项部分添加依赖项。这个库有内置的警报对话框，可以直接使用。** 

## **可扩展标记语言**

```
dependencies {        
        implementation 'com.github.f0ris.sweetalert:library:1.5.1'        
}
```

****第二步:**现在在 **activity_main.xml** 文件中添加以下代码。该代码在活动中增加了**五个按钮**。每个按钮用于调用不同样式的**报警对话框**。** 

**<gfg-tab role="tab" slot="tab" id="gfg-tab-0">activity_main.xml</gfg-tab><gfg-panel role="tabpanel" slot="panel" id="gfg-panel-0" data-code-lang="XML"></gfg-panel>**

```
 `<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <Button
        android:onClick="showDialog"
        android:id="@+id/basic_dialog"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Basic Dialog"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.452"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.124" />

    <Button
        android:onClick="showDialog"
        android:id="@+id/error_dialog"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Error Dialog"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.452"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.284" />

    <Button
        android:onClick="showDialog"
        android:id="@+id/warning_dialog"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Warning Dialog"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.452"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.45" />

    <Button
        android:onClick="showDialog"
        android:id="@+id/success_dialog"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginBottom="256dp"
        android:text="Success Dialog"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.47"
        app:layout_constraintStart_toStartOf="parent" />

    <Button
        android:onClick="showDialog"
        android:id="@+id/custom_dialog"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginBottom="156dp"
        android:text="Custom Dialog"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.464"
        app:layout_constraintStart_toStartOf="parent" />
</androidx.constraintlayout.widget.ConstraintLayout>` 
```