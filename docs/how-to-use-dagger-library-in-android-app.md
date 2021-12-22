# 如何在安卓 App 中使用匕首库？

> 原文:[https://www . geeksforgeeks . org/操作方法-安卓匕首库-app/](https://www.geeksforgeeks.org/how-to-use-dagger-library-in-android-app/)

当我们创建一个新的安卓项目时，最终我们开始积累不同的依赖关系来获得某些功能，但是随着时间的推移，管理它们变得很麻烦，因此像匕首这样的注入框架开始发挥作用。然而，设置像 Dagger 这样的注入服务需要大量的样板代码，并且具有非常陡峭的学习曲线。本来在没有安卓支持的情况下添加 Dagger 的原始依赖/版本就是一场噩梦。

**但是** …..接下来是匕首-安卓，它改变了这个游戏，满足了原始匕首所缺乏的一切，比如减少了预先制作的(锅炉板)代码，但它仍然没有成功。在本文中，我们将通过构建一个简单的项目来理解以下内容。

*   What is **dagger library and**
*   Type **depends on injection,** and
*   How to use **constructor dependency injection in Android?**

我们将建立一个非常简单的应用程序，我们将在其中显示文本。但是我们将通过使用构造函数依赖注入来做到这一点。

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:添加依赖关系**

复制以下匕首依赖项，并将其粘贴到您的应用级 [build.gradle](https://www.geeksforgeeks.org/android-build-gradle/) 文件中。

> 实现【匕首:2 . 38 . 1】
> 
> 注释处理器【匕首:2 . 38 . 1】

继续使用最新的匕首版本，可以从这里获得[。](https://github.com/google/dagger/releases)

**步骤 3:使用 activity_main.xml 文件**

导航到 **app > res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是**activity _ main . XML**文件的代码。在 **activity_main.xml** 文件中添加一个简单的 [TextView](https://www.geeksforgeeks.org/textview-widget-in-android-using-java-with-examples/) 。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textSize="30sp"      
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintLeft_toLeftOf="parent"
        app:layout_constraintRight_toRightOf="parent"
        app:layout_constraintTop_toTopOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

**第 4 步:创建两个新的 Java 类**

制作 2 个类**引擎**和**轮子**，它们的空构造函数如下所示

## Java

```
import java.io.*;

class Engine {
   // Constructor
   public void Engine() { 
   }
}
```

## Java

```
import java.io.*;

class Wheel {
   // Constructor
   public void Wheel() { 
   }
}
```

**第五步:创建另一个 Java 类**

*   Create a Car class whose constructor takes two objects (engine and wheel) as parameters.
*   Create a function driver () that will return a string. Returns a simple string "Driving……" in the drive () function.

## Java

```
import java.io.*;

class Car {

  Engine engine;
  Wheel wheel;

  // Constructor
  public void Car(Engine engine , Wheel wheel) {
    this.engine = engine;
    this.wheel = wheel
  }

  // method 
  public String drive(){
    return "Driving...";
  }  
}
```

**第六步:使用****MainActivity.java 文件**

现在在主活动中，

1.  Declare a text view and define it.
2.  Create new objects of wheel and engine class.
3.  Now use the wheel and engine objects.
4.  To create a car object, just use the driver function we created in the car class to get the string.

转到**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。**

## **Java**

```
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;

public class MainActivity extends AppCompatActivity {

    // Declaring
    TextView text;
    Wheel wheel;
    Engine engine;
    Car car;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // Defining
        text = findViewById(R.id.textView);
        wheel = new Wheel();
        engine = new Engine();
        car = new Car(engine, wheel);

        // Use the drive method from the car object
        String message = car.drive();
        text.setText(message);
    }
}
```