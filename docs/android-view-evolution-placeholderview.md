# 安卓视图进化–place holder View

> 原文:[https://www . geesforgeks . org/Android-view-evolution-placeholder view/](https://www.geeksforgeeks.org/android-view-evolution-placeholderview/)

当**ListView****GridView****recycle view****讨厌的适配器**统治竞技场的日子已经一去不复返了。向 PlaceHolderView 问好？？？？向每个 RecyclerView 添加侦听器并实现动态内容是一项乏味的操作。咱们连动画都不谈；如果我们必须为嵌套的 Recyclers 执行它，那将是一场灾难。如果我们可以通过使用一个非常基本的接口来替换 ListView、GridView 和 RecyclerView，并且不需要适配器实现，会怎么样？

### PlaceHolderView 类的目的是什么？

PlaceHolderView 通过删除所有样板代码，自动执行配置视图适配器的过程。不可思议的是，不需要适配器。代码变得难以置信的模块化，并且向任何视图或方法添加注释的能力给了它很大的灵活性。没有像 findViewById 或 onClickListener 这样难看的代码。

*   It takes only one line of code to create amazing animation for the view object.
*   Memory management is easy.

### 如何在项目中介绍这个大景观？

答案很简单。PlaceHolderView 是一个视图，允许您查看正在发生的事情。PlaceHolderView 库中的一些视图基于 RecyclerView，而其他视图是从头开始创建的。为了生成绑定类，所有的注释都在构建过程中进行处理。有**两种不同的变体**可供选择。

1.  Java reflection was used in the old version (branch 1.x).
2.  The new version (branch 2.x) supports annotation processing.

要将此库添加到您的安卓项目中，只需在您的 Gradle(项目)中放上这一行，然后点击**“同步”**。

## 我的锅

```java
implementation 'com.mindorks.android:placeholderview:1.0.3'
implementation 'com.android.support:recyclerview-v7:27.1.0'
implementation 'com.mindorks.android:placeholderview:1.0.3'
kapt 'com.mindorks.android:placeholderview-compiler:1.0.3'
```

然后神奇的是，占位符视图被添加到你当前的安卓项目中

**步骤#1** :在 XML 布局中，创建一个 PlaceHolderView。之后，您需要调整您的 XML 文件并添加或替换当前视图，为此，只需遵循下面的代码片段

## XML

现在**步骤 2:** 在占位符视图

## XML

```java
<?xml version="1.0" encoding="utf-8"?> 
<LinearLayout 
  xmlns:android="http://schemas.android.com/apk/res/android"
  xmlns:app="http://schemas.android.com/apk/res-auto"
  android:orientation="vertical"
  android:layout_width="match_parent"
  android:layout_height="wrap_content"
  android:padding="10dp">

  <android.support.v7.widget.CardView
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    app:cardCornerRadius="8dp"
    app:cardElevation="10dp">
        <ImageView
             android:id="@+id/geekyImage"
             android:layout_width="match_parent"
             android:layout_height="200dp"
             android:scaleType="centerCrop"
            android:src="@android:color/holo_orange_dark"/>
  </android.support.v7.widget.CardView>

</LinearLayout>
```

中创建需要填充的项目视图

**步骤#3:** 现在在 MainActivity 或 Adapter Activity Java 文件中，只需绑定方法，以便在运行时可以识别它们

## Java

```java
@Animate(Animation.ENTER_RIGHT_DESC)
@NonReusable
@Layout(R.layout.gallery_item_big)
public class GeeksImage {
    @View(R.id.imageView) private ImageView imageView;
    private String mUrl;
    private Context mContext;
    private PlaceHolderView mPlaceHolderView;
    public ImageTypeBig(Context context,
                        PlaceHolderView placeHolderView,
                        String url)
    {
        mContext = context;
        mPlaceHolderView = placeHolderView;
        mUrl = url;
    }
    @Resolve private void onResolved()
    {
        Glide.with(mContext).load(mUrl).into(imageView);
    }
    @LongClick(R.id.imageView) private void onLongClick()
    {

        mPlaceHolderView.removeView(this);
    }
}
```