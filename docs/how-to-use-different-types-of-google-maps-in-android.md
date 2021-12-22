# 如何在安卓系统中使用不同类型的谷歌地图？

> 原文:[https://www . geeksforgeeks . org/如何使用不同类型的安卓谷歌地图/](https://www.geeksforgeeks.org/how-to-use-different-types-of-google-maps-in-android/)

当我们使用谷歌地图的默认应用程序时，我们会在这个应用程序中看到不同类型的地图。我们将会看到卫星地图，地形地图，以及更多。我们已经看到在安卓应用程序中添加[谷歌地图。在这篇文章中，我们将看看不同类型的谷歌地图在安卓系统中的实现。](https://www.geeksforgeeks.org/google-maps-in-android/)

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，其中我们将简单地显示一个带有三个按钮的谷歌地图，我们将在这些按钮的帮助下更改地图。下面给出了一个示例视频，让我们了解一下在本文中要做什么。请注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-552368-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210126222633/Screenrecorder-2021-01-26-22-20-35-86.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210126222633/Screenrecorder-2021-01-26-22-20-35-86.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210126222633/Screenrecorder-2021-01-26-22-20-35-86.mp4)</video>

### **分步实施**

**第一步:创建新项目**

在安卓工作室创建新项目请参考 [<u>【如何在安卓工作室创建/启动新项目】</u>](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/) 。注意选择 **Java** 作为编程语言。创建新项目时，确保选择**映射活动**。

**第二步:生成使用谷歌地图的应用编程接口密钥**

要为地图生成应用编程接口密钥，您可以参考[<u>如何为在安卓系统中使用谷歌地图生成应用编程接口密钥</u>](https://www.geeksforgeeks.org/how-to-generate-api-key-for-using-google-maps-in-android/) 。在为谷歌地图生成你的应用编程接口密钥后。我们必须将这个密钥添加到我们的项目中。要在我们的应用程序中添加此密钥，请导航至**值文件夹> google_maps_api.xml** 文件，在第 23 行，您必须添加您的 api 密钥来代替 **YOUR_API_KEY** 。

**步骤 3:使用 activity_maps.xml 文件**

导航至**应用程序> res >布局> activity_maps.xml** 并添加以下代码。代码中添加了注释，以便更详细地了解。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent">

    <!--fragment to display our map-->
    <fragment xmlns:tools="http://schemas.android.com/tools"
        android:id="@+id/map"
        android:name="com.google.android.gms.maps.SupportMapFragment"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        tools:context=".MapsActivity" />

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_alignParentBottom="true"
        android:layout_margin="5dp"
        android:orientation="horizontal"
        android:padding="5dp"
        android:weightSum="3">

        <!--button for displaying hybrid map-->
        <Button
            android:id="@+id/idBtnHybridMap"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_margin="5dp"
            android:layout_weight="1"
            android:background="@color/purple_500"
            android:singleLine="false"
            android:text="Hybrid \n Map"
            android:textAllCaps="false"
            android:textColor="@color/white" />

        <!--button for displaying satellite map-->
        <Button
            android:id="@+id/idBtnSatelliteMap"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_margin="5dp"
            android:layout_weight="1"
            android:background="@color/purple_500"
            android:singleLine="false"
            android:text="Satellite \n Map"
            android:textAllCaps="false"
            android:textColor="@color/white" />

        <!--button for displaying terrain map-->
        <Button
            android:id="@+id/idBtnTerrainMap"
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_margin="5dp"
            android:layout_weight="1"
            android:background="@color/purple_500"
            android:singleLine="false"
            android:text="Terrain \n Map"
            android:textAllCaps="false"
            android:textColor="@color/white" />

    </LinearLayout>

</RelativeLayout>
```

**步骤 4:使用 MapsActivity.java 文件**

转到**文件，参考以下代码。以下是**MapsActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
import android.os.Bundle;
import android.view.View;
import android.widget.Button;

import androidx.fragment.app.FragmentActivity;

import com.google.android.gms.maps.CameraUpdateFactory;
import com.google.android.gms.maps.GoogleMap;
import com.google.android.gms.maps.OnMapReadyCallback;
import com.google.android.gms.maps.SupportMapFragment;
import com.google.android.gms.maps.model.LatLng;
import com.google.android.gms.maps.model.MarkerOptions;

public class MapsActivity extends FragmentActivity implements OnMapReadyCallback {

    private GoogleMap mMap;

    // below are the latitude and longitude
      // of delhi locations.
    LatLng delhi = new LatLng(28.644800, 77.216721);

    // creating a variable for button.
    private Button hybridMapBtn, terrainMapBtn, satelliteMapBtn;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_maps);

        // initialize our buttons
        hybridMapBtn = findViewById(R.id.idBtnHybridMap);
        terrainMapBtn = findViewById(R.id.idBtnTerrainMap);
        satelliteMapBtn = findViewById(R.id.idBtnSatelliteMap);

        // Obtain the SupportMapFragment and get notified when the map is ready to be used.
        SupportMapFragment mapFragment = (SupportMapFragment) getSupportFragmentManager().findFragmentById(R.id.map);
        mapFragment.getMapAsync(this);

        // adding on click listener for our hybrid map button.
        hybridMapBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // below line is to change 
                // the type of map to hybrid.
                mMap.setMapType(GoogleMap.MAP_TYPE_HYBRID);
            }
        });

        // adding on click listener for our terrain map button.
        terrainMapBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // below line is to change
                // the type of terrain map.
                mMap.setMapType(GoogleMap.MAP_TYPE_TERRAIN);
            }
        });
        // adding on click listener for our satellite map button.
        satelliteMapBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // below line is to change the
                // type of satellite map.
                mMap.setMapType(GoogleMap.MAP_TYPE_SATELLITE);
            }
        });
    }

    @Override
    public void onMapReady(GoogleMap googleMap) {
        mMap = googleMap;

        // adding marker to each location on google maps
        mMap.addMarker(new MarkerOptions().position(delhi).title("Marker in Delhi"));

        // below line is use to move camera.
        mMap.moveCamera(CameraUpdateFactory.newLatLng(delhi));
    }
}
```

**现在运行您的应用程序，并查看应用程序的输出。**

### ****输出:****

**<video class="wp-video-shortcode" id="video-552368-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210126222633/Screenrecorder-2021-01-26-22-20-35-86.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210126222633/Screenrecorder-2021-01-26-22-20-35-86.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210126222633/Screenrecorder-2021-01-26-22-20-35-86.mp4)</video>**