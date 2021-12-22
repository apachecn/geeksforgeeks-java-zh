# 如何使用 Firebase Firestore 在安卓中创建动态介绍滑块？

> 原文:[https://www . geesforgeks . org/how-create-dynamic-intro-slider-in-Android-use-firebase-firestore/](https://www.geeksforgeeks.org/how-to-create-dynamic-intro-slider-in-android-using-firebase-firestore/)

我们已经看到[在安卓](https://www.geeksforgeeks.org/how-to-create-a-basic-intro-slider-of-an-android-app/)中创建了一个基本的 Intro Slider，用于通知我们的用户关于我们的应用程序的功能以及更多。在这篇文章中，我们将在 [Firebase](https://www.geeksforgeeks.org/firebase-introduction/) 的帮助下，看看**动态介绍滑块在我们的应用程序中的实现。借助 Firebase Firestore，我们可以从 Firebase 控制台动态更改所有数据。现在让我们转向实现。**

### 我们将在这个项目中构建什么？

我们将建立一个简单的介绍滑块，我们将从 Firebase 控制台加载所有数据，并在我们的滑块中显示这些数据。借助 Firebase，我们可以根据自己的需求动态更新数据。下面给出了一个 GIF 示例，来了解一下在本文中要做什么。请注意，我们将使用 **Java** 语言来实现这个项目。

![Create Dynamic Intro Slider in Android using Firebase Firestore Sample GIF](img/de74260fc82c5ed277905d0c74f4bcfd.png)

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:将你的应用连接到 Firebase**

创建新项目后。导航到顶部栏上的工具选项。点击火焰基地。点击 Firebase 后，你可以看到截图中下面提到的右栏。

![](img/7403667f8de6879fd2daed9cf6e280b5.png)

在那一栏中，导航到火基云火石。点击那个选项，你会看到两个选项:连接应用到 Firebase 和添加云 Firestore 到你的应用。单击立即连接选项，您的应用程序将连接到 Firebase。之后点击第二个选项，现在你的应用程序连接到 Firebase。将您的应用程序连接到 Firebase 后，您将看到下面的屏幕。

![](img/f196c7eb4b95bcd215964a732d6b1064.png)

之后，验证 Firebase Firestore 数据库的依赖项是否已经添加到我们的 Gradle 文件中。导航到该文件中的应用程序>渐变脚本，检查下面的依赖项是否已添加。如果您的 build.gradle 文件中不存在以下依赖项。在依赖项部分添加以下依赖项。

> 实现' com . Google . firebase:firebase-firestore:22 . 0 . 1 '
> 
> 实现' com.squareup .毕加索:毕加索:2.71828 '

添加此依赖项后，同步您的项目，现在我们可以创建我们的应用程序了。如果你想了解更多关于连接你的应用到 Firebase。参考本文详细了解[如何给安卓 App](https://www.geeksforgeeks.org/adding-firebase-to-android-app/) 添加 Firebase。当我们从网址加载图像时，我们必须使用[毕加索](https://www.geeksforgeeks.org/image-loading-caching-library-android-set-1/)。

**第三步:添加互联网权限**

因为我们将从网址加载图像，所以我们必须在您的 AndroidManifest.xml 文件中添加互联网权限。用于添加权限。导航到 app > AndroidManifest.xml 文件，并添加以下权限。

## 可扩展标记语言

```java
<!--Permissions for internet-->
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

**第 4 步:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    android:weightSum="5"
    tools:context=".MainActivity">

    <!--view pager for displaying our slides-->
    <androidx.viewpager.widget.ViewPager
        android:id="@+id/idViewPager"
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:layout_weight="4.5" />

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:layout_weight="0.5"
        android:orientation="horizontal"
        android:weightSum="5">

        <View
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="2" />

        <!--adding linear layout for creating dots view-->
        <LinearLayout
            android:id="@+id/idLLDots"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_gravity="center_horizontal"
            android:layout_weight="1"
            android:gravity="center_horizontal"
            android:orientation="horizontal" />

        <!--button for skipping our intro slider-->
        <Button
            android:id="@+id/idBtnSkip"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_gravity="center"
            android:layout_margin="10dp"
            android:layout_weight="2"
            android:background="@color/purple_500"
            android:backgroundTint="@color/purple_500"
            android:text="Skip"
            android:textAllCaps="false"
            android:textColor="@color/white" />

    </LinearLayout>

</LinearLayout>
```

**第五步:为我们的滑块项目**创建布局文件

现在，我们将创建一个项目，我们将显示在我们的滑块。因此，要创建新布局，请导航至**应用程序> res >布局>右键单击它>单击新建>布局资源文件**并将其命名为 **slider_layout** 并向其添加以下代码。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <!--text view for displaying our heading-->
    <TextView
        android:id="@+id/idTVtitle"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="20dp"
        android:padding="10dp"
        android:text="Slide 1"
        android:textAlignment="center"
        android:textColor="@color/black"
        android:textSize="20sp" />

    <!--Image view for displaying our slider image-->
    <ImageView
        android:id="@+id/idIV"
        android:layout_width="200dp"
        android:layout_height="200dp"
        android:layout_below="@id/idTVtitle"
        android:layout_centerHorizontal="true"
        android:layout_marginTop="50dp"
        android:padding="10dp"
        android:src="@mipmap/ic_launcher" />

    <!--text view for displaying our slider description-->
    <TextView
        android:id="@+id/idTVheading"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/idIV"
        android:layout_marginStart="20dp"
        android:layout_marginTop="90dp"
        android:layout_marginEnd="20dp"
        android:padding="10dp"
        android:text="C++ data structure and ALgorithm Course"
        android:textAlignment="center"
        android:textSize="15sp" />

</RelativeLayout>
```

**步骤 6:创建一个模态类来存储滑块项目的所有数据**

要创建新的 Modal 类，导航到**应用程序> java >你的应用程序的包名>右键单击它，然后单击新建> Java 类**，并将其命名为**slidermodel**。创建此类后，向其中添加以下代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
public class SliderModal {

    // string variable for storing title,
    // image url and description.
    private String title;
    private String heading;
    private String imgUrl;

    public SliderModal() {
        // empty constructor is required
        // when using firebase
    }

    // creating getter methods.
    public String getTitle() {
        return title;
    }

    public void setTitle(String title) {
        this.title = title;
    }

    public String getHeading() {
        return heading;
    }

    // creating setter methods
    public void setHeading(String heading) {
        this.heading = heading;
    }

    public String getImgUrl() {
        return imgUrl;
    }

    public void setImgUrl(String imgUrl) {
        this.imgUrl = imgUrl;
    }

    // constructor for our modal class
    public SliderModal(String title, String heading, String imgUrl) {
        this.title = title;
        this.heading = heading;
        this.imgUrl = imgUrl;
    }
}
```

**第 7 步:创建一个适配器类，为每个视图设置数据**

用于创建新的适配器类。导航到**应用> java >你的应用的包名>右键点击>新 java 类>将其命名为** **SliderAdapter** 并添加下面的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.content.Context;
import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import android.widget.ImageView;
import android.widget.RelativeLayout;
import android.widget.TextView;

import androidx.annotation.NonNull;
import androidx.viewpager.widget.PagerAdapter;

import com.squareup.picasso.Picasso;

import java.util.ArrayList;

public class SliderAdapter extends PagerAdapter {

    // creating variables for layout inflater,
    // context and array list.
    LayoutInflater layoutInflater;
    Context context;
    ArrayList<SliderModal> sliderModalArrayList;

    // creating constructor.
    public SliderAdapter(Context context, ArrayList<SliderModal> sliderModalArrayList) {
        this.context = context;
        this.sliderModalArrayList = sliderModalArrayList;
    }

    @Override
    public int getCount() {
        // inside get count method returning
        // the size of our array list.
        return sliderModalArrayList.size();
    }

    @Override
    public boolean isViewFromObject(@NonNull View view, @NonNull Object object) {
        // inside isViewFrombject method we are
        // returning our Relative layout object.
        return view == (RelativeLayout) object;
    }

    @NonNull
    @Override
    public Object instantiateItem(@NonNull ViewGroup container, int position) {
        // in this method we will initialize all our layout items
        // and inflate our layout file as well.
        layoutInflater = (LayoutInflater) context.getSystemService(context.LAYOUT_INFLATER_SERVICE);

        // below line is use to inflate the layout file which we created.
        View view = layoutInflater.inflate(R.layout.slider_layout, container, false);

        // initializing our views.
        ImageView imageView = view.findViewById(R.id.idIV);
        TextView titleTV = view.findViewById(R.id.idTVtitle);
        TextView headingTV = view.findViewById(R.id.idTVheading);

        // setting data to our views.
        SliderModal modal = sliderModalArrayList.get(position);
        titleTV.setText(modal.getTitle());
        headingTV.setText(modal.getHeading());
        Picasso.get().load(modal.getImgUrl()).into(imageView);

        // after setting the data to our views we
        // are adding the view to our container.
        container.addView(view);

        // at last we are returning the view.
        return view;
    }

    @Override
    public void destroyItem(@NonNull ViewGroup container, int position, @NonNull Object object) {
        // this is a destroy view method which
        // is use to remove a view.
        container.removeView((RelativeLayout) object);
    }
}
```

**第 8 步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.os.Bundle;
import android.text.Html;
import android.widget.LinearLayout;
import android.widget.TextView;
import android.widget.Toast;

import androidx.annotation.NonNull;
import androidx.appcompat.app.AppCompatActivity;
import androidx.viewpager.widget.ViewPager;

import com.google.android.gms.tasks.OnFailureListener;
import com.google.android.gms.tasks.OnSuccessListener;
import com.google.firebase.firestore.DocumentSnapshot;
import com.google.firebase.firestore.FirebaseFirestore;
import com.google.firebase.firestore.QuerySnapshot;

import java.util.ArrayList;
import java.util.List;

public class MainActivity extends AppCompatActivity {

    // creating variables for view pager,
    // lineralyout, adapter and our array list.
    private ViewPager viewPager;
    private LinearLayout dotsLL;
    SliderAdapter adapter;
    private ArrayList<SliderModal> sliderModalArrayList;
    private TextView[] dots;
    int size;
    FirebaseFirestore db;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        db = FirebaseFirestore.getInstance();

        // initializing all our views.
        viewPager = findViewById(R.id.idViewPager);
        dotsLL = findViewById(R.id.idLLDots);

        // in below line we are creating a new array list.
        sliderModalArrayList = new ArrayList<>();
        loadDataFromFirebase();

        // calling method to add dots indicator
        addDots(size, 0);

        // below line is use to call on page
        // change listener method.
        viewPager.addOnPageChangeListener(viewListner);
    }

    private void loadDataFromFirebase() {

        // below line is use to get data from Firebase
        // firestore using collection in android.
        db.collection("SliderData").get()
                .addOnSuccessListener(new OnSuccessListener<QuerySnapshot>() {
                    @Override
                    public void onSuccess(QuerySnapshot queryDocumentSnapshots) {
                        // after getting the data we are calling on success method
                        // and inside this method we are checking if the received
                        // query snapshot is empty or not.
                        if (!queryDocumentSnapshots.isEmpty()) {
                            // if the snapshot is not empty we are hiding our
                            // progress bar and adding our data in a list.
                            List<DocumentSnapshot> list = queryDocumentSnapshots.getDocuments();
                            for (DocumentSnapshot d : list) {
                                // after getting this list we are passing
                                // that list to our object class.
                                SliderModal sliderModal = d.toObject(SliderModal.class);

                                // after getting data from Firebase we are
                                // storing that data in our array list
                                sliderModalArrayList.add(sliderModal);
                            }
                            // below line is use to add our array list to adapter class.
                            adapter = new SliderAdapter(MainActivity.this, sliderModalArrayList);

                            // below line is use to set our
                            // adapter to our view pager.
                            viewPager.setAdapter(adapter);

                            // we are storing the size of our
                            // array list in a variable.
                            size = sliderModalArrayList.size();
                        } else {
                            // if the snapshot is empty we are displaying a toast message.
                            Toast.makeText(MainActivity.this, "No data found in Database", Toast.LENGTH_SHORT).show();
                        }
                    }
                }).addOnFailureListener(new OnFailureListener() {
            @Override
            public void onFailure(@NonNull Exception e) {
                // we are displaying a toast message when
                // we get any error from Firebase.
                Toast.makeText(MainActivity.this, "Fail to load data..", Toast.LENGTH_SHORT).show();
            }
        });
    }

    private void addDots(int size, int pos) {
        // inside this method we are
        // creating a new text view.
        dots = new TextView[size];

        // below line is use to remove all
        // the views from the linear layout.
        dotsLL.removeAllViews();

        // running a for loop to add number
        // of dots to our slider.
        for (int i = 0; i < size; i++) {
            // below line is use to add the dots
            // and modify its color.
            dots[i] = new TextView(this);
            dots[i].setText(Html.fromHtml("•"));
            dots[i].setTextSize(35);

            // below line is called when the
            // dots are not selected.
            dots[i].setTextColor(getResources().getColor(R.color.white));
            dotsLL.addView(dots[i]);
        }
        if (dots.length > 0) {
            // this line is called when the dots
            // inside linear layout are selected
            dots[pos].setTextColor(getResources().getColor(R.color.purple_200));
        }
    }

    // creating a method for view pager for on page change listener.
    ViewPager.OnPageChangeListener viewListner = new ViewPager.OnPageChangeListener() {
        @Override
        public void onPageScrolled(int position, float positionOffset, int positionOffsetPixels) {

        }

        @Override
        public void onPageSelected(int position) {
            // we are calling our dots method to
            // change the position of selected dots.
            addDots(size, position);
        }

        @Override
        public void onPageScrollStateChanged(int state) {

        }
    };
}
```