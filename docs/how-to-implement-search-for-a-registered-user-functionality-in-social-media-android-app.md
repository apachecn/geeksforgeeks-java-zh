# 如何在社交媒体安卓 App 中实现搜索注册用户功能？

> 原文:[https://www . geesforgeks . org/如何实现-搜索注册用户-社交媒体中的功能-安卓-app/](https://www.geeksforgeeks.org/how-to-implement-search-for-a-registered-user-functionality-in-social-media-android-app/)

这是 **【在 Android Studio 上构建社交媒体 App】**教程的 **第 9 部分** ，我们将在本文中介绍以下功能:

*   We will search for users on the users page.
*   If there are few people registered in our application, it is easy to find a person.
*   But when our application registered 1000 users, then searching for a specific user became a very complicated and time-consuming task.
*   That's why we implement this function to search users with the provided **name or email** .

### **分步实施**

**步骤 1:** **使用主菜单. xml 文件**

在**主菜单. xml** 文件中添加搜索图标。

## XML

```
<item
  android:id="@+id/search"
  android:icon="@drawable/ic_search"
  android:title="Search"
  app:actionViewClass="android.widget.SearchView"
  app:showAsAction="always">
</item>
```