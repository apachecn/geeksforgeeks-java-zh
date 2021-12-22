# 如何计算安卓系统中两个位置之间的距离？

> 原文:[https://www . geeksforgeeks . org/如何计算安卓系统中两个位置之间的距离/](https://www.geeksforgeeks.org/how-to-calculate-distance-between-two-locations-in-android/)

我们已经看到许多使用谷歌地图的应用程序。这些地图用于指示谷歌地图上的地点，我们也可以用它来计算两个地点之间的距离。在本文中，我们将看一下**计算安卓中两个位置之间的距离。**

### 我们将在本文中构建什么？

我们将构建一个简单的应用程序，其中我们将显示一个简单的地图，在我们的应用程序启动时，我们将显示一条带有地图上两个位置之间距离的[吐司](https://www.geeksforgeeks.org/android-what-is-toast-and-how-to-use-it-with-examples/)消息。下面是视频，我们将在其中看到我们将在本文中构建的内容。我们将计算悉尼和布里斯班之间的**距离**。注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-547046-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210118181455/Screenrecorder-2021-01-18-18-09-26-558.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210118181455/Screenrecorder-2021-01-18-18-09-26-558.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210118181455/Screenrecorder-2021-01-18-18-09-26-558.mp4)</video>

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。创建新项目时，确保选择**地图活动**。

**第二步:生成使用谷歌地图的应用编程接口密钥**

要为地图生成应用编程接口密钥，您可以参考[如何为在安卓系统中使用谷歌地图生成应用编程接口密钥](https://www.geeksforgeeks.org/how-to-generate-api-key-for-using-google-maps-in-android/)。在为谷歌地图生成你的应用编程接口密钥后。我们必须将这个密钥添加到我们的项目中。要在我们的应用程序中添加此密钥，请导航至**值文件夹> google_maps_api.xml** 文件，在第 23 行，您必须添加您的 api 密钥来代替 **YOUR_API_KEY** 。

**第三步:添加依赖项计算两个位置之间的距离**

导航到**应用程序>渐变脚本>构建.渐变**文件，并在“依赖项”部分添加下面的依赖项。

> 实现' com . Google . maps . Android:Android-maps-utils:0.4+'

添加以下依赖项后，现在同步您的项目。添加该依赖项后，现在移向显示敬酒信息的**MapsActivity.java**文件。

**步骤 4:使用 MapsActivity.java 文件**

转到**文件，参考以下代码。以下是**MapsActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。**

## **Java 语言(一种计算机语言，尤用于创建网站)**

```java
import android.os.Bundle;
import android.widget.Toast;

import androidx.fragment.app.FragmentActivity;

import com.google.android.gms.maps.GoogleMap;
import com.google.android.gms.maps.OnMapReadyCallback;
import com.google.android.gms.maps.SupportMapFragment;
import com.google.android.gms.maps.model.LatLng;
import com.google.maps.android.SphericalUtil;

public class MapsActivity extends FragmentActivity implements OnMapReadyCallback {

    private GoogleMap mMap;

    // below are the latitude and longitude 
    // of 2 different locations.
    LatLng sydney = new LatLng(-34, 151);
    LatLng Brisbane = new LatLng(-27.470125, 153.021072);
    Double distance;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_maps);
        // Obtain the SupportMapFragment and get notified 
        // when the map is ready to be used.
        SupportMapFragment mapFragment = (SupportMapFragment) getSupportFragmentManager().findFragmentById(R.id.map);
        mapFragment.getMapAsync(this);
    }

    /**
     * Manipulates the map once available.
     * This callback is triggered when the map is ready to be used.
     * This is where we can add markers or lines, add listeners or move the camera. In this case,
     * we just add a marker near Sydney, Australia.
     * If Google Play services is not installed on the device, the user will be prompted to install
     * it inside the SupportMapFragment. This method will only be triggered once the user has
     * installed Google Play services and returned to the app.
     */
    @Override
    public void onMapReady(GoogleMap googleMap) {
        mMap = googleMap;
        // on below line we are calculating the distance between sydney and brisbane
        distance = SphericalUtil.computeDistanceBetween(sydney, Brisbane);

        // in below line we are displaying a toast 
        // message with distance between two locations.
        // in our distance we are dividing it by 1000 to
        // make in km and formatting it to only 2 decimal places.
        Toast.makeText(this, "Distance between Sydney and Brisbane is \n " + String.format("%.2f", distance / 1000) + "km", Toast.LENGTH_SHORT).show();
    }
}
```

**添加此代码后。现在运行您的应用程序，并查看应用程序的输出。**

### ****输出:****

> *****注意:**在谷歌开发者控制台(*[](https://console.developers.google.com/)**)中，确保启用了“**谷歌地图安卓 API v2** ”。并确保您的应用编程接口密钥存在。****

***<video class="wp-video-shortcode" id="video-547046-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210118181455/Screenrecorder-2021-01-18-18-09-26-558.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210118181455/Screenrecorder-2021-01-18-18-09-26-558.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210118181455/Screenrecorder-2021-01-18-18-09-26-558.mp4)</video>***