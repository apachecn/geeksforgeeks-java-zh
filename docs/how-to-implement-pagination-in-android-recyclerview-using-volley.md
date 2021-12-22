# 如何使用凌空在安卓 RecyclerView 中实现分页？

> 原文:[https://www . geeksforgeeks . org/如何在 android 中实现分页-recycle view-use-凌空/](https://www.geeksforgeeks.org/how-to-implement-pagination-in-android-recyclerview-using-volley/)

**分页**是最重要的因素之一，它有助于减少应用程序内部的加载时间，并提高以列表形式表示的数据的性能。在本文中，我们将看看如何在我们的安卓[回收视图](https://www.geeksforgeeks.org/android-recyclerview/)中添加分页。为了从 API 获取数据，我们将使用[截击](https://www.geeksforgeeks.org/json-parsing-in-android-using-volley-library/)库。

### 什么是分页？

分页是根据需求加载数据，而不是一次加载完整的数据。因此，这有助于减少从应用编程接口加载数据的时间，并提高应用程序的性能。

### 在数据列表中使用分页有什么好处？

很多时候，我们不得不在列表视图或回收视图中一次加载大量数据。因此，如果我们一次加载所有数据，将需要一些时间来加载数据，这将增加 Recycler 视图的加载时间。分页将为您提供支持，在它的帮助下，我们可以以块的形式加载数据，因此这将防止我们的回收视图降低其性能，并且数据加载将会更快。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，其中我们将在我们的安卓回收视图中显示一个数据列表，我们将在我们的回收视图中添加分页来加载我们的数据。下面给出了一个示例视频，让我们了解一下在本文中要做什么。请注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-563922-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210221125506/Screenrecorder-2021-02-21-12-53-05-546.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210221125506/Screenrecorder-2021-02-21-12-53-05-546.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210221125506/Screenrecorder-2021-02-21-12-53-05-546.mp4)</video>

### **分步实施**

**第一步:创建新项目**

在安卓工作室创建新项目请参考 [<u>【如何在安卓工作室创建/启动新项目】</u>](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/) 。注意选择 **Java** 作为编程语言。

**第二步:在你的 build.gradle 文件**中添加下面的依赖项

下面是凌空的依赖，我们将使用它从应用编程接口获取数据。要添加此依赖项，请导航至**应用程序>渐变脚本> build.gradle(应用程序)**，并在依赖项部分添加以下依赖项。我们已经使用了毕加索从网址图像加载依赖。

> //下面的依赖项用于使用毕加索图像加载库和截击
> 
> 实现' com.squareup .毕加索:毕加索:2.71828 '
> 
> 实现‘com . Android .凌空:凌空:1 . 1 . 1’

添加这个依赖项后，同步你的项目，现在进入 **AndroidManifest.xml** 部分。

**第三步:在 AndroidManifest.xml 文件**中添加互联网权限

导航到**应用程序> AndroidManifest.xml** ，并添加以下代码。

## 可扩展标记语言

```
<uses-permission android:name="android.permission.INTERNET" />
```

**第 4 步:使用 activity_main.xml 文件**

导航到**应用程序> res >布局> activity_main.xml** 并将下面的代码添加到该文件中。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<!--in this we are displaying a nested scroll view-->
<androidx.core.widget.NestedScrollView 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/idNestedSV"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <!--linear layout for displaying
        our recycler view-->
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:orientation="vertical">

        <!--recycler view for displaying our list of data
            and we are making nested scroll for our 
            recycler view as false-->
        <androidx.recyclerview.widget.RecyclerView
            android:id="@+id/idRVUsers"
            android:layout_width="match_parent"
            android:layout_height="0dp"
            android:layout_weight="1"
            android:nestedScrollingEnabled="false"
            tools:listitem="@layout/user_rv_item" />

        <!--we are adding progress bar
            for the purpose of loading-->
        <ProgressBar
            android:id="@+id/idPBLoading"
            android:layout_width="match_parent"
            android:layout_height="wrap_content" />
    </LinearLayout>

</androidx.core.widget.NestedScrollView>
```

**第 5 步:创建一个模态类来存储我们的数据**

为了存储数据，我们必须创建一个新的 java 类。要创建一个新的 java 类，导航到**应用程序> java >你的应用程序的包名>右键单击它>新建> Java 类**并将其命名为**用户模式**并添加下面的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
public class UserModal {
    // variables for our first name, 
    // last name, email and avatar
    private String first_name;
    private String last_name;
    private String email;
    private String avatar;

    public String getFirst_name() {
        return first_name;
    }

    public void setFirst_name(String first_name) {
        this.first_name = first_name;
    }

    public String getLast_name() {
        return last_name;
    }

    public void setLast_name(String last_name) {
        this.last_name = last_name;
    }

    public String getEmail() {
        return email;
    }

    public void setEmail(String email) {
        this.email = email;
    }

    public String getAvatar() {
        return avatar;
    }

    public void setAvatar(String avatar) {
        this.avatar = avatar;
    }

    public UserModal(String first_name, String last_name, String email, String avatar) {
        this.first_name = first_name;
        this.last_name = last_name;
        this.email = email;
        this.avatar = avatar;
    }
}
```

**第 6 步:为我们的回收视图**的每个项目创建一个布局文件

导航至 **app > res >布局>右键点击>新建>布局资源文件**，文件名为 **user_rv_item** ，并添加以下代码。代码中添加了注释，以便更详细地了解。

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<androidx.cardview.widget.CardView 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:elevation="8dp"
    app:cardCornerRadius="8dp">

    <RelativeLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="2dp">

        <!--image view for displaying user image-->
        <ImageView
            android:id="@+id/idIVUser"
            android:layout_width="100dp"
            android:layout_height="100dp"
            android:layout_margin="10dp" />

        <!--text view for displaying first name-->
        <TextView
            android:id="@+id/idTVFirstName"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_marginTop="10dp"
            android:layout_toEndOf="@id/idIVUser"
            android:layout_toRightOf="@id/idIVUser"
            android:text="First Name"
            android:textColor="@color/black"
            android:textSize="15sp" />

        <!--text view for displaying last name-->
        <TextView
            android:id="@+id/idTVLastName"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_below="@id/idTVFirstName"
            android:layout_marginTop="10dp"
            android:layout_toEndOf="@id/idIVUser"
            android:layout_toRightOf="@id/idIVUser"
            android:text="Last Name"
            android:textColor="@color/black"
            android:textSize="15sp" />

        <!--text view for displaying user email-->
        <TextView
            android:id="@+id/idTVEmail"
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_below="@id/idTVLastName"
            android:layout_marginTop="10dp"
            android:layout_toEndOf="@id/idIVUser"
            android:layout_toRightOf="@id/idIVUser"
            android:text="Email"
            android:textColor="@color/black"
            android:textSize="15sp" />

    </RelativeLayout>

</androidx.cardview.widget.CardView>
```

**第 7 步:创建一个适配器类，用于将数据设置到我们的回收视图项**

要创建一个新的适配器类，导航到**应用程序> java >你的应用程序的包名>右键单击它>新建> Java 类**并将其命名为**用户适配器**并添加下面的代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.content.Context;
import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import android.widget.ImageView;
import android.widget.TextView;

import androidx.annotation.NonNull;
import androidx.recyclerview.widget.RecyclerView;

import com.squareup.picasso.Picasso;

import java.util.ArrayList;

public class UserRVAdapter extends RecyclerView.Adapter<UserRVAdapter.ViewHolder> {

    // variable for our array list and context.
    private ArrayList<UserModal> userModalArrayList;
    private Context context;

    // creating a constructor.
    public UserRVAdapter(ArrayList<UserModal> userModalArrayList, Context context) {
        this.userModalArrayList = userModalArrayList;
        this.context = context;
    }

    @NonNull
    @Override
    public ViewHolder onCreateViewHolder(@NonNull ViewGroup parent, int viewType) {
        // inflating our layout file on below line.
        View view = LayoutInflater.from(context).inflate(R.layout.user_rv_item, parent, false);
        return new ViewHolder(view);
    }

    @Override
    public void onBindViewHolder(@NonNull ViewHolder holder, int position) {

        // getting data from our array list in our modal class.
        UserModal userModal = userModalArrayList.get(position);

        // on below line we are setting data to our text view.
        holder.firstNameTV.setText(userModal.getFirst_name());
        holder.lastNameTV.setText(userModal.getLast_name());
        holder.emailTV.setText(userModal.getEmail());

        // on below line we are loading our image 
        // from url in our image view using picasso.
        Picasso.get().load(userModal.getAvatar()).into(holder.userIV);
    }

    @Override
    public int getItemCount() {
        // returning the size of array list.
        return userModalArrayList.size();
    }

    public class ViewHolder extends RecyclerView.ViewHolder {
        // creating a variable for our text view and image view.
        private TextView firstNameTV, lastNameTV, emailTV;
        private ImageView userIV;

        public ViewHolder(@NonNull View itemView) {
            super(itemView);

            // initializing our variables.
            firstNameTV = itemView.findViewById(R.id.idTVFirstName);
            lastNameTV = itemView.findViewById(R.id.idTVLastName);
            emailTV = itemView.findViewById(R.id.idTVEmail);
            userIV = itemView.findViewById(R.id.idIVUser);
        }
    }
}
```

**步骤 8:使用 MainActivity.java 文件**

转到**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```
import android.os.Bundle;
import android.view.View;
import android.widget.ProgressBar;
import android.widget.Toast;

import androidx.appcompat.app.AppCompatActivity;
import androidx.core.widget.NestedScrollView;
import androidx.recyclerview.widget.LinearLayoutManager;
import androidx.recyclerview.widget.RecyclerView;

import com.android.volley.Request;
import com.android.volley.RequestQueue;
import com.android.volley.Response;
import com.android.volley.VolleyError;
import com.android.volley.toolbox.JsonObjectRequest;
import com.android.volley.toolbox.Volley;

import org.json.JSONArray;
import org.json.JSONException;
import org.json.JSONObject;

import java.util.ArrayList;

public class MainActivity extends AppCompatActivity {

    // creating a variable for our array list, adapter class,
    // recycler view, progressbar, nested scroll view
    private ArrayList<UserModal> userModalArrayList;
    private UserRVAdapter userRVAdapter;
    private RecyclerView userRV;
    private ProgressBar loadingPB;
    private NestedScrollView nestedSV;

    // creating a variable for our page and limit as 2
    // as our api is having highest limit as 2 so 
    // we are setting a limit = 2
    int page = 0, limit = 2;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // creating a new array list.
        userModalArrayList = new ArrayList<>();

        // initializing our views.
        userRV = findViewById(R.id.idRVUsers);
        loadingPB = findViewById(R.id.idPBLoading);
        nestedSV = findViewById(R.id.idNestedSV);

        // calling a method to load our api.
        getDataFromAPI(page, limit);

        // adding on scroll change listener method for our nested scroll view.
        nestedSV.setOnScrollChangeListener(new NestedScrollView.OnScrollChangeListener() {
            @Override
            public void onScrollChange(NestedScrollView v, int scrollX, int scrollY, int oldScrollX, int oldScrollY) {
                // on scroll change we are checking when users scroll as bottom.
                if (scrollY == v.getChildAt(0).getMeasuredHeight() - v.getMeasuredHeight()) {
                    // in this method we are incrementing page number,
                    // making progress bar visible and calling get data method.
                    page++;
                    loadingPB.setVisibility(View.VISIBLE);
                    getDataFromAPI(page, limit);
                }
            }
        });
    }

    private void getDataFromAPI(int page, int limit) {
        if (page > limit) {
            // checking if the page number is greater than limit.
            // displaying toast message in this case when page>limit.
            Toast.makeText(this, "That's all the data..", Toast.LENGTH_SHORT).show();

            // hiding our progress bar.
            loadingPB.setVisibility(View.GONE);
            return;
        }
        // creating a string variable for url .
        String url = "https://reqres.in/api/users?page=" + page;

        // creating a new variable for our request queue
        RequestQueue queue = Volley.newRequestQueue(MainActivity.this);

        // creating a variable for our json object request and passing our url to it.
        JsonObjectRequest jsonObjectRequest = new JsonObjectRequest(Request.Method.GET, url, null, new Response.Listener<JSONObject>() {
            @Override
            public void onResponse(JSONObject response) {
                try {

                    // on below line we are extracting data from our json array.
                    JSONArray dataArray = response.getJSONArray("data");

                    // passing data from our json array in our array list.
                    for (int i = 0; i < dataArray.length(); i++) {
                        JSONObject jsonObject = dataArray.getJSONObject(i);

                        // on below line we are extracting data from our json object.
                        userModalArrayList.add(new UserModal(jsonObject.getString("first_name"), jsonObject.getString("last_name"), jsonObject.getString("email"), jsonObject.getString("avatar")));

                        // passing array list to our adapter class.
                        userRVAdapter = new UserRVAdapter(userModalArrayList, MainActivity.this);

                        // setting layout manager to our recycler view.
                        userRV.setLayoutManager(new LinearLayoutManager(MainActivity.this));

                        // setting adapter to our recycler view.
                        userRV.setAdapter(userRVAdapter);
                    }
                } catch (JSONException e) {
                    e.printStackTrace();
                }
            }
        }, new Response.ErrorListener() {
            @Override
            public void onErrorResponse(VolleyError error) {
                // handling on error listener method.
                Toast.makeText(MainActivity.this, "Fail to get data..", Toast.LENGTH_SHORT).show();
            }
        });
        // calling a request queue method 
        // and passing our json object
        queue.add(jsonObjectRequest);
    }
}
```

**现在运行您的应用程序，并查看应用程序的输出。**

### ****输出:****

**<video class="wp-video-shortcode" id="video-563922-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210221125506/Screenrecorder-2021-02-21-12-53-05-546.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210221125506/Screenrecorder-2021-02-21-12-53-05-546.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210221125506/Screenrecorder-2021-02-21-12-53-05-546.mp4)</video>**