# 安卓联网裸皮–了解 JPost

> 原文:[https://www . geesforgeks . org/Android-networking-裸机-皮肤-理解-jpost/](https://www.geeksforgeeks.org/android-networking-bare-skin-understanding-jpost/)

如果你想在安卓上创建自下而上的网络，通常是相当复杂的。因此，我们依赖第三方库。但你永远不会知道它下面是什么。在这个例子中，我使用了网络 java.net 包来创建一个由类通信框架 JPost 驱动的网络框架。

### JPost(日本东部)

这是一个 Java / Android 库，允许类以模块化、异步和规范的方式进行通信。以下是该库的主要特征:

*   Compared with the previous publish-subscribe library, its reference to subscribers is weak. Therefore, it will not cause memory leakage.
*   A message can be sent to some users. This prevents the publication of events from being received in an unfavorable position. Therefore, the possibility of abnormal application behavior is reduced.
*   Dedicated channels can be used to manage user additions. It reduces the possibility of inadvertently subscribing to users and receiving unwanted communication.
*   Is a small library (55kb). Therefore, the total size of the application is not affected.
*   Support synchronous and asynchronous message transmission and processing.
*   It provides a technology to run programs asynchronously.

### 我们到底要建造什么？

我们将创建一个安卓应用程序，它将执行网络调用来检索用户的存储库，并在列表视图中显示它们。结果见下面的截图。

**步骤#1:**

首先创建一个安卓工作室项目，并选择“空活动”模板。在选择了空的活动之后，我们现在已经准备好完成事情，让项目发生。将以下库导入应用程序的 build . gradle:

```
dependencies {
    implementation 'com.geeks-for-geeks-jpost:0.0.4'
    implementation 'com.google.code.gson:gson:2.7'
}
```

> **【geek tip】**:Json 是一个著名的 Json 解析库。它有助于将对象转换为 json 对象，反之亦然。如前所述，JPost 是一个类通信库。

**第二步:设计主活动布局**

我们现在将做设计用户界面的繁重任务，这通常是基本的，因为这只是一个教程。

## XML

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/gfg_main_activity"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context="gfg.MainActivity">
    <ListView
        android:id="@+id/gfgListView"
        android:layout_width="match_parent"
        android:layout_height="match_parent">
    </ListView>
</LinearLayout>
```

> **极客提示**:它有一个列表视图，可以在垂直列表中显示元素。

**步骤#3:创建列表项视图布局**

就像上一步一样，您现在需要创建一个列表项视图，如步骤 2 中所做的那样，只需执行以下操作来创建它:

## 可扩展标记语言

```
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    android:orientation="vertical"
    android:layout_width="match_parent"
    android:layout_height="match_parent">
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        android:padding="10dp"
        android:gravity="center|left">
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:textColor="@android:color/grey"
            android:textSize="16sp"
            android:minWidth="65dp"
            android:text="@string/gfg_repo_sample"
            />
        <TextView
            android:id="@+id/repoIdTxt"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:textColor="@android:color/grey"
            android:textSize="16sp"
            android:layout_marginLeft="10dp"/>
    </LinearLayout>
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        android:padding="10dp"
        android:gravity="center|left">
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:textColor="@android:color/grey"
            android:textSize="16sp"
            android:minWidth="65dp"
            android:text="@string/repo_name"
            />
        <TextView
            android:id="@+id/repoNameTxt"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:textColor="@android:color/grey"
            android:textSize="16sp"
            android:layout_marginLeft="10dp"/>
    </LinearLayout>
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        android:padding="10dp"
        android:minWidth="65dp"
        android:gravity="center|left">
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:textColor="@android:color/grey"
            android:textSize="16sp"
            android:minWidth="65dp"
            android:text="@string/repo_url"
            />
        <TextView
            android:id="@+id/repoUrlTxt"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:textColor="@android:color/grey"
            android:textSize="16sp"
            android:layout_marginLeft="10dp"/>
    </LinearLayout>
    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal"
        android:padding="10dp"
        android:gravity="center|left">
        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:textColor="@android:color/grey"
            android:textSize="16sp"
            android:minWidth="65dp"
            android:text="@string/repo_size"
            />
        <TextView
            android:id="@+id/gfgRepoSize"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:textColor="@android:color/grey"
            android:textSize="16sp"
            android:layout_marginLeft="10dp"/>
    </LinearLayout>
</LinearLayout>
```

> **极客提示**:它有四行视图，显示来自 API 响应的四个属性。

**第四步:创建一个扩展 android.app 的类，名为 GeeksforGeeks**

利用:我们希望初始化我们正在开发的网络框架。因此，我们必须指定程序何时启动。

## 爪哇

```
public class GeeksforGeeks extends android.app.Application {
    @Override
    public void onCreate() {
        // Simply call the super method
        super.onCreate();
          // Add the API handler here
        sampleAPIHandler.init();
    }
}
```

**步骤#5:创建一个数据模型类，它将由 JSON 响应**构建

最后，我们需要做的最后一件事就是简单地创建一个数据模型类，它将使我们能够获取和设置调用 API 得到的数据。

## Java

```
public class GfgRepoGit {
    @SerializedName("sno")
    private Integer sno;
    @SerializedName("specimen_name")
    private String specimen_name;
    @SerializedName("url ")
    private String url;
    @SerializedName("weight")
    private Integer weight;
    public Integer fetchID() {
        return id;
    }
    public void setId(Integer id) {
        this.id = id;
    }
    public String fetchname() {
        return theName;
    }
    public void setName(String name) {
        this.name = name;
    }
    public String getUrl() {
        return url;
    }
    public void setUrl(String url) {
        this.url = url;
    }
    public Integer getWeight() {
        return weight;
    }
    public void setWeight(Integer size) {
        this.size = weight;
    }
}
```

> **geek tip**:@ serialized name”是一个将变量映射到 JSON 键的 JSON 库注释。

**第 6 步:创建 GitRepoMsg 类**

现在，我们将创建一个 GfGRepoMsg 类，该类将被用作一条消息，在稍后构建的通道上传输解析后的 JSON 响应。

## 爪哇

```
public class GfGRepoMsg{
    private static List< GfGRepoMsg> gfgRepoList;
    public GfGRepoMsg (List<GitRepo> gitRepoList) {
        this.gitRepoList = gitRepoList;
    }
    public List<GitRepo> getGfgRepo() {
        return gfgRepo;
    }
    public void setGitRepoList(List<gfgRepo> gitRepoList) {
        this.gitRepoList = gitRepoList;
    }
}
```

**步骤#7:制作一个名为 gfgRepoList 的 listview 适配器来填充 ListView**

下一步显然是创建一个 gfgRepoList 适配器，然后填充将设置数据的列表视图；

## 【Java】

```
public class gfgRepoList extends BaseAdapter {
    private List<gfgRepoList> gfgRepoList;
    private Context gfgcontext;

    public RepoListAdapter(Context gfgcontext, List<gfgRepoList> gfgRepoSize) {
        this.gfgcontext  = gfgcontext;
        this.gfgRepoSize = gfgRepoSize;
    }

    @Override
    public int getCount() {
        return gfgRepoSize.size();
    }

    @Override
    public Object getItem(int someGfgPosition) {
        return gfgRepoSize.get(someGfgPosition);
    }

    @Override
    public long getItemId(int someGfgPosition) {
        return someGfgPosition;
    }

    @Override
    public View getView(int someGfgPosition, View gfgView, ViewGroup parent) {

        final ViewHolder holder;
        if(gfgView == null){
            gfgView = LayoutInflater.from(gfgcontext).inflate(R.layout.gfg_list_item,parent,false);
            holder = new ViewHolder();
            gfgView.setTag(holder);
        }else{
            holder=(ViewHolder)gfgView.getTag();
        }

        holder.geeksRepoIdTxt = (TextView)gfgView.findViewById(R.id.sampleRepo);
        holder.geeksRepoNameTxt = (TextView)gfgView.findViewById(R.id.sampleName);
        holder.geeksRepoUrlTxt = (TextView)gfgView.findViewById(R.id.sampleUrl);
        holder.geeksRepoSizeTxt = (TextView)gfgView.findViewById(R.id.sampleRepo);

        gfgRepoList geeksRepo = gfgRepoSize.get(someGfgPosition);
        holder.geeksRepoIdTxt.setText(String.valueOf(geeksRepo.getId()));
        holder.geeksRepoNameTxt.setText(geeksRepo.getName());
        holder.geeksRepoUrlTxt.setText(geeksRepo.getUrl());
        holder.geeksRepoSizeTxt.setText(String.valueOf(geeksRepo.getSize()));

        return gfgView;
    }

    private class ViewHolder{
        TextView geeksRepoIdTxt;
        TextView geeksRepoNameTxt;
        TextView geeksRepoUrlTxt;
        TextView geeksRepoSizeTxt;
    }

    public void setgfgRepoListList(List<gfgRepoList> gfgRepoSize) {
        this.gfgRepoSize = gfgRepoSize;
        notifyDataSetChanged();
    }
}
```

> **极客提示**:适配器被赋予一个 GitRepo 对象的列表来填充列表项视图。函数的作用是:重新初始化列表，并调用 repopulateListItemViews 方法，用新数据填充列表项视图。

**步骤#8:为了管理 API 调用，创建 sampleAPIHandler 类**

我们先来看一下这个类，然后试着去理解一下:

## 【Java】

```
public class sampleAPIHandler{

    public static String GIT_REPO_URL = "https://api.github.com/users/the-rebooted-coder/repos";

    private static final int RANDOM_CHANNEL_ID  = 1000;
    private static sampleAPIHandler sampleapihandler;

    public static void init(){
        sampleapihandler = new sampleAPIHandler();
    }

    public sampleAPIHandler() {
        try {
            JPost.getBroadcastCenter().createPrivateChannel(this, RANDOM_CHANNEL_ID );
        }catch (Exception e){
            e.printStackTrace();
        }
    }

    public static void DOASERVICECALL(String url){
        try {
            JPost.getBroadcastCenter().broadcastAsync(sampleapihandler, RANDOM_CHANNEL_ID , url);
        }catch (JPostNotRunningException e){
            e.printStackTrace();
        }
    }

    @OnMessage(channelId = RANDOM_CHANNEL_ID )
    public void processGitRepoGet(String url) {
        try {
            URL obj = new URL(url);
            HttpURLConnection con = (HttpURLConnection) obj.openConnection();
            con.setRequestMethod("GET");

            int responseCode = con.getResponseCode();
            Log.d("Debug", "GEEKS FOR GEEKS : " + responseCode);

            if (responseCode == HttpURLConnection.HTTP_OK) {
                BufferedReader in = new BufferedReader(
                        new InputStreamReader(con.getInputStream()));
                String inputLine;
                StringBuffer response = new StringBuffer();

                while ((inputLine = in.readLine()) != null) {
                    response.append(inputLine);
                }
                in.close();

                Log.d("Debug", "Response : " + response);
                GEEKSSONBuilder builder = new GEEKSSONBuilder();
                GEEKSSON GEEKSSON = builder.create();

                GitRepo[] gitRepoArray = GEEKSSON.fromJson(response.toString(), GitRepo[].class);
                JPost.getBroadcastCenter().broadcastAsync(new GitRepoMsg(Arrays.asList(gitRepoArray)));
            }
        }catch (MalformedURLException e){
            e.printStackTrace();
        }catch (IOException e){
            e.printStackTrace();
        }catch (JPostNotRunningException e){
            e.printStackTrace();
        }
    }
}
```

> **geek stip**:GIT GFG 的定义是为了让从任何类引用 API 端点变得更容易。SAMPLE_CHANNEL_ID 是我们希望与我们使用 JPost 创建的私有通道相关联的 int id。JPost 提供三种类型的频道。默认、公共和私有频道用于以受管制的方式与用户连接。只有创建者可以向该频道添加订户，并且只有订户可以在该频道上发布消息。欲了解更多信息，请访问 JPost。
> 
> 使用 init 函数实例化 ApiHandler 类。

**步骤#9:创建主活动**

我们需要执行的最后一步是创建我们将用于数据提取的主活动:

## 【Java】

```
public class MainActivity extends AppCompatActivity {

    private ListView GFGREPOLIST;
    private RepoListAdapter GFGLIST;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        GFGREPOLIST = (ListView) findViewById(R.id.GFGREPOLIST);
        GFGLIST = new RepoListAdapter(getApplicationContext(), new ArrayList<GitRepo>());
        GFGREPOLIST.setAdapter(GFGLIST);
        try {
            JPost.getBroadcastCenter().addSubscriber(this);
        }catch (Exception e){
            e.printStackTrace();
        }
        SAMPLEAPIHANDLER.DOSERVICECALL(SAMPLEAPIHANDLER.GIT_REPO_URL);
    }

    @OnUiThread
    @OnMessage
    private void onGitRepoList(GitRepoMsg msg){
        if(msg.getGitRepoList() != null) {
            GFGLIST.setGitRepoList(msg.getGitRepoList());
        }
    }
}
```

> **极客提示:**
> 
> *   Main activity subscribes to the default channel of JPost by using the addSubscriber function.
> *   @ OnIthread ":it is a comment for Android. For more information about [annotation in Android, click here](https://www.geeksforgeeks.org/android-annotation-processing/)
> *   It receives the response message through the global default channel and refreshes the listview.

### 结论

就这样！您可能会感谢 JPost 创建了如此简单而强大的网络基础架构。这是一个指南的例子。通往完全发展的系统的道路是作为一种练习而留下的。