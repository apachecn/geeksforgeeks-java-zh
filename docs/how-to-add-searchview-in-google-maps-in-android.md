# 如何在安卓的谷歌地图中添加 SearchView？

> 原文:[https://www . geeksforgeeks . org/how-add-search view-in-Google-map-in-Android/](https://www.geeksforgeeks.org/how-to-add-searchview-in-google-maps-in-android/)

我们已经看到了[谷歌地图在安卓系统中的实现以及上面的标记](https://www.geeksforgeeks.org/how-to-add-custom-marker-to-google-maps-in-android/)。但许多应用程序提供了一些功能，让用户可以指定他们必须放置标记的位置。因此，在本文中，我们将在我们的安卓应用程序中实现一个[搜索视图](https://www.geeksforgeeks.org/android-searchview-with-example/)，这样我们就可以搜索一个位置名称，并在该位置添加一个标记。

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，其中我们将显示一个简单的谷歌地图和一个**搜索视图**。在该搜索视图中，当用户输入任何位置名称时，我们将在谷歌地图上为该位置添加一个标记。下面给出了一个示例视频，让我们了解一下在本文中要做什么。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-552351-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210126163040/Screenrecorder-2021-01-26-16-21-59-991.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210126163040/Screenrecorder-2021-01-26-16-21-59-991.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210126163040/Screenrecorder-2021-01-26-16-21-59-991.mp4)</video>

### **分步实施**

**第一步:创建新项目**

在安卓工作室创建新项目请参考 [<u>【如何在安卓工作室创建/启动新项目】</u>](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/) 。注意选择 **Java** 作为编程语言。创建新项目时，确保选择**映射活动**。

**第二步:生成使用谷歌地图的应用编程接口密钥**

要为地图生成应用编程接口密钥，您可以参考[<u>如何为在安卓系统中使用谷歌地图生成应用编程接口密钥</u>](https://www.geeksforgeeks.org/how-to-generate-api-key-for-using-google-maps-in-android/) 。在为谷歌地图生成你的应用编程接口密钥后。我们必须将这个密钥添加到我们的项目中。要在我们的应用程序中添加此密钥，请导航至**值文件夹> google_maps_api.xml** 文件，在第 23 行，您必须添加您的 api 密钥来代替 **YOUR_API_KEY** 。

**步骤 3:使用 activity_maps.xml 文件**

当我们在谷歌地图中添加**搜索视图**来搜索一个位置并在该位置添加标记时。所以我们必须给我们的**活动文件添加一个搜索视图。要添加搜索视图，请导航至**应用程序> res >布局> activity_maps.xml** ，并添加以下代码。代码中添加了注释，以便更详细地了解。**

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <!--fragment to display our maps-->
    <fragment xmlns:tools="http://schemas.android.com/tools"
        android:id="@+id/map"
        android:name="com.google.android.gms.maps.SupportMapFragment"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        tools:context=".MapsActivity" />

    <!--search view to search our location-->
    <androidx.appcompat.widget.SearchView
        android:id="@+id/idSearchView"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_margin="10dp"
        android:background="#BFBFBF"
        android:elevation="5dp"
        app:iconifiedByDefault="false"
        app:queryHint="Search Here" />

</RelativeLayout>
```

**步骤 4:使用 MapsActivity.java 文件**

转到**MapsActivity.java**文件，参考以下代码。以下是**MapsActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.location.Address;
import android.location.Geocoder;
import android.os.Bundle;

import androidx.appcompat.widget.SearchView;
import androidx.fragment.app.FragmentActivity;

import com.google.android.gms.maps.CameraUpdateFactory;
import com.google.android.gms.maps.GoogleMap;
import com.google.android.gms.maps.OnMapReadyCallback;
import com.google.android.gms.maps.SupportMapFragment;
import com.google.android.gms.maps.model.LatLng;
import com.google.android.gms.maps.model.MarkerOptions;

import java.io.IOException;
import java.util.List;

public class MapsActivity extends FragmentActivity implements OnMapReadyCallback {

    private GoogleMap mMap;

    // creating a variable 
    // for search view.
    SearchView searchView;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_maps);

        // initializing our search view.
        searchView = findViewById(R.id.idSearchView);

        // Obtain the SupportMapFragment and get notified 
        // when the map is ready to be used.
        SupportMapFragment mapFragment = (SupportMapFragment) getSupportFragmentManager().findFragmentById(R.id.map);

        // adding on query listener for our search view.
        searchView.setOnQueryTextListener(new SearchView.OnQueryTextListener() {
            @Override
            public boolean onQueryTextSubmit(String query) {
                // on below line we are getting the 
                // location name from search view.
                String location = searchView.getQuery().toString();

                // below line is to create a list of address
                // where we will store the list of all address.
                List<Address> addressList = null;

                // checking if the entered location is null or not.
                if (location != null || location.equals("")) {
                    // on below line we are creating and initializing a geo coder.
                    Geocoder geocoder = new Geocoder(MapsActivity.this);
                    try {
                        // on below line we are getting location from the 
                        // location name and adding that location to address list.
                        addressList = geocoder.getFromLocationName(location, 1);
                    } catch (IOException e) {
                        e.printStackTrace();
                    }
                    // on below line we are getting the location 
                    // from our list a first position.
                    Address address = addressList.get(0);

                    // on below line we are creating a variable for our location
                    // where we will add our locations latitude and longitude.
                    LatLng latLng = new LatLng(address.getLatitude(), address.getLongitude());

                    // on below line we are adding marker to that position.
                    mMap.addMarker(new MarkerOptions().position(latLng).title(location));

                    // below line is to animate camera to that position.
                    mMap.animateCamera(CameraUpdateFactory.newLatLngZoom(latLng, 10));
                }
                return false;
            }

            @Override
            public boolean onQueryTextChange(String newText) {
                return false;
            }
        });
        // at last we calling our map fragment to update.
        mapFragment.getMapAsync(this);
    }

    @Override
    public void onMapReady(GoogleMap googleMap) {
        mMap = googleMap;
    }
}
```

现在运行您的应用程序，并查看应用程序的输出。

### **输出:**

<video class="wp-video-shortcode" id="video-552351-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210126163040/Screenrecorder-2021-01-26-16-21-59-991.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210126163040/Screenrecorder-2021-01-26-16-21-59-991.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210126163040/Screenrecorder-2021-01-26-16-21-59-991.mp4)</video>