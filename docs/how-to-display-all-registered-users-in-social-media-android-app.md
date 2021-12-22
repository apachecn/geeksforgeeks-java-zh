# 如何在社交媒体安卓 App 中显示所有注册用户？

> 原文:[https://www . geeksforgeeks . org/如何显示所有注册用户-社交媒体-安卓-app/](https://www.geeksforgeeks.org/how-to-display-all-registered-users-in-social-media-android-app/)

这是 **【在 Android Studio 上构建社交媒体 App】**教程的 **第 8 部分** ，我们将在本文中介绍以下功能:

*   We will show all registered users of our App.
*   We will display the user list in **user group** .

### **分步实施**

**步骤 1:创建一个新的 java 类**

使用**ModelUsers.java**文件。创建此活动是为了初始化密钥，以便我们以后可以检索密钥的值。

## 爪哇

```
package com.example.socialmediaapp;

public class ModelUsers {
    String name;

    public ModelUsers() {
    }

    String onlineStatus;
    String typingTo;

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getTypingTo() {
        return typingTo;
    }

    public void setTypingTo(String typingTo) {
        this.typingTo = typingTo;
    }

    public String getEmail() {
        return email;
    }

    public void setEmail(String email) {
        this.email = email;
    }

    public String getImage() {
        return image;
    }

    public void setImage(String image) {
        this.image = image;
    }

    public String getUid() {
        return uid;
    }

    public void setUid(String uid) {
        this.uid = uid;
    }

    public ModelUsers(String name, String onlineStatus, String typingTo, String email, String image, String uid) {
        this.name = name;
        this.onlineStatus = onlineStatus;
        this.typingTo = typingTo;
        this.email = email;
        this.image = image;
        this.uid = uid;
    }

    String email;

    String image;

    String uid;
}
```