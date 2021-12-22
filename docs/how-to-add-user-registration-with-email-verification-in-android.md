# 如何在安卓中添加带邮件验证的用户注册？

> 原文:[https://www . geesforgeks . org/如何添加用户-通过电子邮件注册-安卓验证/](https://www.geeksforgeeks.org/how-to-add-user-registration-with-email-verification-in-android/)

我们已经看到大多数应用程序通过用户的电子邮件地址或电话号码来验证他们的用户，方法是向他们发送验证链接或向用户的手机号码发送动态口令。在本文中，我们将看看用户注册在安卓中的实现及其电子邮件验证。为此，我们将使用 **Back4App** 服务，该服务为我们提供了一个功能，以便我们可以将自动电子邮件验证链接发送给我们的用户进行验证。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，其中我们将显示一个简单的用户注册和登录表单。用户注册后，我们将向用户的电子邮件地址发送验证链接，以验证用户的电子邮件地址。下面是视频，我们将在其中看到我们将在本文中构建的内容。

<video class="wp-video-shortcode" id="video-572858-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210315151702/User-Registration-with-Email-Verification-in-Android.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210315151702/User-Registration-with-Email-Verification-in-Android.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210315151702/User-Registration-with-Email-Verification-in-Android.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:将你的应用连接到 Back4App**

本任务请参考[如何连接安卓 App 和 Back4App](https://www.geeksforgeeks.org/how-to-connect-android-app-with-back4app/) 。

**步骤 3:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <!--text view for heading-->
    <TextView
        android:id="@+id/idTVHeader"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_marginTop="30dp"
        android:gravity="center_horizontal"
        android:padding="5dp"
        android:text="Welcome to Geeks for Geeks \n Register Form"
        android:textAlignment="center"
        android:textColor="@color/purple_700"
        android:textSize="18sp" />

    <!--edit text for user name-->
    <EditText
        android:id="@+id/idEdtUserName"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idTVHeader"
        android:layout_marginStart="10dp"
        android:layout_marginTop="50dp"
        android:layout_marginEnd="10dp"
        android:hint="Enter UserName"
        android:inputType="text" />

    <!--edit text for user email-->
    <EditText
        android:id="@+id/idEdtEmail"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idEdtUserName"
        android:layout_marginStart="10dp"
        android:layout_marginTop="20dp"
        android:layout_marginEnd="10dp"
        android:hint="Enter Email Address"
        android:inputType="textEmailAddress" />

    <!--edit text for user password-->
    <EditText
        android:id="@+id/idEdtPassword"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idEdtEmail"
        android:layout_marginStart="10dp"
        android:layout_marginTop="20dp"
        android:layout_marginEnd="10dp"
        android:hint="Enter Password"
        android:inputType="textPassword" />

    <!--button to register our new user-->
    <Button
        android:id="@+id/idBtnRegister"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idEdtPassword"
        android:layout_marginStart="10dp"
        android:layout_marginTop="20dp"
        android:layout_marginEnd="10dp"
        android:text="Register User"
        android:textAllCaps="false" />

</RelativeLayout>
```

**第四步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.content.Intent;
import android.os.Bundle;
import android.text.TextUtils;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;

import com.parse.ParseException;
import com.parse.ParseUser;
import com.parse.SignUpCallback;

public class MainActivity extends AppCompatActivity {

    // creating variables for our edit text and buttons.
    private EditText userNameEdt, passwordEdt, userEmailEdt;
    private Button registerBtn;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initializing our edit text  and buttons.
        userNameEdt = findViewById(R.id.idEdtUserName);
        passwordEdt = findViewById(R.id.idEdtPassword);
        userEmailEdt = findViewById(R.id.idEdtEmail);
        registerBtn = findViewById(R.id.idBtnRegister);

        // adding on click listener for our button
        registerBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                // on below line we are getting data from our edit text.
                String userName = userNameEdt.getText().toString();
                String password = passwordEdt.getText().toString();
                String email = userEmailEdt.getText().toString();

                // checking if the entered text is empty or not.
                if (TextUtils.isEmpty(userName) && TextUtils.isEmpty(password) && TextUtils.isEmpty(email)) {
                    Toast.makeText(MainActivity.this, "Please enter user name and password", Toast.LENGTH_SHORT).show();
                }

                // calling a method to register a user.
                registerUser(userName, password, email);
            }
        });
    }

    private void registerUser(String userName, String password, String email) {

        // on below line we are creating
        // a new user using parse user.
        ParseUser user = new ParseUser();

        // Set the user's username, user email and password,
        // which can be obtained from edit text
        user.setUsername(userName);
        user.setEmail(email);
        user.setPassword(password);

        // calling a method to register the user.
        user.signUpInBackground(new SignUpCallback() {
            @Override
            public void done(ParseException e) {
                // on user registration checking
                // if the error is null or not.
                if (e == null) {
                    // if the error is null we are displaying a toast message and
                    // redirecting our user to login activity and passing the user name.
                    Toast.makeText(MainActivity.this, "User Registered successfully \n Please verify your email", Toast.LENGTH_SHORT).show();
                    Intent i = new Intent(MainActivity.this, LoginActivity.class);
                    i.putExtra("usereName", userName);
                    i.putExtra("password", password);
                    startActivity(i);
                } else {
                    // if we get any error then we are logging out
                    // our user and displaying an error message
                    ParseUser.logOut();
                    Toast.makeText(MainActivity.this, "Fail to Register User..", Toast.LENGTH_SHORT).show();
                }
            }
        });
    }
}
```