# 如何从安卓 App 中删除 Firebase 用户？

> 原文:[https://www . geeksforgeeks . org/如何从安卓 app 中删除 firebase-user/](https://www.geeksforgeeks.org/how-to-delete-a-firebase-user-from-android-app/)

我们已经在许多应用程序中看到，如果可以选择删除用户，或者可以说永久删除您的帐户。在这里，我们将看到如何在我们的应用程序中实现这一点，并可以从 firebase 身份验证中永久删除我们的帐户。这里，在编写代码时，我们将删除用户，但在此之前，我们将重新验证用户。

### **分步实施**

**第一步:**如果你是 [Firebase](https://www.geeksforgeeks.org/firebase-introduction/) 的新手，那么可以参考[在安卓](https://www.geeksforgeeks.org/user-authentication-using-firebase-in-android/)中使用 Firebase 进行用户认证。

**第二步:**按照所有步骤“登录”你的安卓应用。然后创建一个**主菜单**文件如下

## XML

```
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto">

    <item
        android:id="@+id/menulogout"
        android:title="Logout" />

    <item
        android:id="@+id/delete"
        android:title="Delete User" />

</menu>
```