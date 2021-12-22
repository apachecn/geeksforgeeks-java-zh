# 如何在安卓系统中从 Firebase 更新/更改邮件？

> 原文:[https://www . geesforgeks . org/如何更新-更改-电子邮件-来自安卓 firebase/](https://www.geeksforgeeks.org/how-to-update-change-email-from-firebase-in-android/)

在任何应用程序中，我们都有一个使用电子邮件和密码登录的功能。有时，我们想更改我们的电子邮件，或者我们丢失了以前电子邮件的密码，所以在这里，我们将使用 Firebase 身份验证实现相同的功能来更改我们的电子邮件。注意，我们将使用 **Java** 语言来实现这个项目。

### **分步实施**

让我们假设您已经有一个现有的项目，或者您可以创建一个新的项目。

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**步骤 2:使用 XML 文件**

转到 **XML** 文件，参考以下代码。下面是 **XML** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:gravity="center"
    tools:context=".ChangeEmail">

    <EditText
        android:id="@+id/email"
        android:layout_width="267dp"
        android:layout_height="wrap_content"
        android:layout_alignParentStart="true"
        android:layout_alignParentTop="true"
        android:layout_marginStart="36dp"
        android:layout_marginTop="120dp"
        android:ems="10"
        android:hint="Email"
        android:inputType="textEmailAddress" />

    <EditText
        android:id="@+id/logpass"
        android:layout_width="259dp"
        android:layout_height="58dp"
        android:layout_alignParentStart="true"
        android:layout_alignParentTop="true"
        android:layout_marginStart="32dp"
        android:layout_marginTop="161dp"
        android:ems="10"
        android:hint="Password"
        android:inputType="textPassword" />

    <EditText
        android:id="@+id/change"
        android:layout_width="259dp"
        android:layout_height="58dp"
        android:layout_alignParentStart="true"
        android:layout_alignParentTop="true"
        android:layout_marginStart="32dp"
        android:layout_marginTop="211dp"
        android:ems="10"
        android:hint="Change Email"
        android:inputType="textEmailAddress" />

    <Button
        android:id="@+id/changeemail"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentStart="true"
        android:layout_alignParentTop="true"
        android:layout_marginStart="192dp"
        android:layout_marginTop="277dp"
        android:background="@color/colorPrimary"
        android:text="Change Email Here"
        android:textSize="15dp" />

</RelativeLayout>
```

**步骤 3:** **使用 Java 文件**

所以主要部分存在于 java 文件中。在这个文件中，我们需要**重新认证**用户，因为根据文档，更改主电子邮件地址是一个敏感的操作。下面是执行相同操作的代码片段。

## Java 语言(一种计算机语言，尤用于创建网站)

```
FirebaseUser user = FirebaseAuth.getInstance().getCurrentUser();

// Get auth credentials from the user for re-authentication
AuthCredential credential = EmailAuthProvider.getCredential(email, password); // Current Login Credentials

// Prompt the user to re-provide their sign-in credentials
user.reauthenticate(credential).addOnCompleteListener(new OnCompleteListener<Void>() {
                    @Override
                    public void onComplete(@NonNull Task<Void> task) {

                        Log.d("value", "User re-authenticated.");

                        // Now change your email address \\
                        //----------------Code for Changing Email Address----------\\
                        FirebaseUser user = FirebaseAuth.getInstance().getCurrentUser();
                        user.updateEmail(change.getText().toString()).addOnCompleteListener(new OnCompleteListener<Void>() {
                                    @Override
                                    public void onComplete(@NonNull Task<Void> task) {
                                        if (task.isSuccessful()) {
                                            Toast.makeText(ChangeEmail.this, "Email Changed" + " Current Email is " + change.getText().toString(), Toast.LENGTH_LONG).show();
                                        }
                             }
                 });
       }
});
```

下面是****Java 文件**的完整代码，上面是 **XML 文件**。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
import androidx.annotation.NonNull;
import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.util.Log;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

import com.google.android.gms.tasks.OnCompleteListener;
import com.google.android.gms.tasks.Task;
import com.google.firebase.auth.AuthCredential;
import com.google.firebase.auth.EmailAuthProvider;
import com.google.firebase.auth.FirebaseAuth;
import com.google.firebase.auth.FirebaseUser;

public class ChangeEmail extends AppCompatActivity {

    FirebaseAuth auth;
    Button changeemail;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_change_email);

        // Initialising the email and password
        final EditText email = findViewById(R.id.email);
        final EditText password = findViewById(R.id.logpass);
        changeemail = findViewById(R.id.changeemail);

        // click on this to change email
        changeemail.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                changeemail(email.getText().toString(), password.getText().toString());
            }
        });

    }

    EditText change;

    // Here we are going to change our email using firebase re-authentication
    private void changeemail(String email, final String password) {

        change = findViewById(R.id.change);

        FirebaseUser user = FirebaseAuth.getInstance().getCurrentUser();

        // Get auth credentials from the user for re-authentication
        AuthCredential credential = EmailAuthProvider.getCredential(email, password); // Current Login Credentials

        // Prompt the user to re-provide their sign-in credentials
        user.reauthenticate(credential).addOnCompleteListener(new OnCompleteListener<Void>() {
                    @Override
                    public void onComplete(@NonNull Task<Void> task) {

                        Log.d("value", "User re-authenticated.");

                        // Now change your email address \\
                        //----------------Code for Changing Email Address----------\\
                        FirebaseUser user = FirebaseAuth.getInstance().getCurrentUser();
                        user.updateEmail(change.getText().toString()).addOnCompleteListener(new OnCompleteListener<Void>() {
                                    @Override
                                    public void onComplete(@NonNull Task<Void> task) {
                                        if (task.isSuccessful()) {
                                            Toast.makeText(ChangeEmail.this, "Email Changed" + " Current Email is " + change.getText().toString(), Toast.LENGTH_LONG).show();
                                        }
                                    }
                                });
                         }
             });
    }
}
```

****输出:****

**<video class="wp-video-shortcode" id="video-574398-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210315191316/change-email.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210315191316/change-email.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210315191316/change-email.mp4)</video>**