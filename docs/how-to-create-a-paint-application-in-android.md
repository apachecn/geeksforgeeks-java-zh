# 如何在安卓系统中创建绘画应用？

> 原文:[https://www . geeksforgeeks . org/如何在安卓系统中创建油漆应用/](https://www.geeksforgeeks.org/how-to-create-a-paint-application-in-android/)

我们小时候都用过 MS-Paint，当这个系统从桌子转移到我们的手掌上时，我们开始在 Instagram Stories、Hike、WhatsApp 和更多类似的应用上涂鸦。但是你有没有想过这些功能是如何实现的？因此，在本文中，我们将讨论此类应用程序使用的基本方法，并将创建此类应用程序的基本副本。下面给出了一个示例视频，让我们了解一下在本文中要做什么。请注意，我们将使用 **Java** 语言来实现这个项目。

<video class="wp-video-shortcode" id="video-556875-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210203001411/InShot_20210203_000836577.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210203001411/InShot_20210203_000836577.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210203001411/InShot_20210203_000836577.mp4)</video>

### **接近**

1.  在日常生活中，如果我们想创作一幅画，我们首先需要一幅画布。因此，在我们的应用程序中，我们将首先创建一个画布，用户可以在其中绘制他的绘图。为此，我们需要创建一个自定义视图，用户可以简单地拖动手指来绘制笔画。为了实现这一点，我们创建了一个 DrawView 类，它从标准的 Android SDK 扩展了 View 类。
2.  然后我们将需要一个画笔，作为一个工具来帮助我们在画布上绘画。现在，由于我们需要不同颜色和不同笔画宽度的不同画笔，我们将创建一个蓝图，即一个名为 stroke 的类，它具有笔画颜色、笔画宽度、笔画可见性等属性。这个类的每个对象将代表一个独特的画笔，在画布上绘制一个独特的笔画。
3.  为了记录用户在画布上绘制的每一个笔画，我们将创建一个笔画类型的数组列表。这个数组列表将帮助我们撤销用户在画布上错误绘制的笔画。
4.  现在，当用户完成绘图后，他可能想要保存该绘画以供进一步使用。因此，我们提供了保存选项，它将允许用户以 PNG 或 JPEG 的形式保存当前画布。

### 方法列表

在跳到代码之前，我们将在构建应用程序时使用以下几种方法:

<figure class="table">

| 

类型

 | 

方法

 | 

描述

 |
| --- | --- | --- |
| gap | Setting jitter (Boolean jitter) | 抖动会影响属于 | Down-sampling of the color of |
| hollow | 七龙珠登场人物及译名列表 | antiasias 平滑了所绘制内容的边缘，但对形状的内部影响不大。 |
| hollow | setStyle(绘制)。679 维琪·维琪·维琪·维琪·维琪·维琪·维琪·维琪·维琪·维琪·维琪·维琪·维琪·维琪·维琪·维琪·维琪·维琪·维琪·维琪） | This method controls |
| become invalid | 设置 strokekcap(油漆.帽帽) | 此方法根据参数改变线端点的几何形状，例如 ROUND、SQUARE、BUTT。 |
| 空的 | void setStrokeJoin(Paint .加入加入) | This method sets the paint to be connected to any one of ROUND, slope and MITTER. |
| 空的 | setAlpha(内部 a) | 它是一种辅助方法，只分配颜色的

alpha 值，而保持其 r、g、b 值不变。如果α值在范围[0]之外，则结果未定义..255] |
| 空的 | 无效() | 此方法调用被覆盖的 onDraw()方法。每当我们想要更新屏幕时，在我们的例子中是 Canvas，我们调用 invalidate()方法，该方法进一步在内部调用 onDraw()方法。 |
| （同 Internationalorganizations）国际组织 | 帆布。保存() | 此方法保存 Canvas 的当前状态以便我们以后可以回到它上面 |
| 空的 | 帆布。还原() | 此方法将 Canvas 的调整还原回 |  |
| 空的 | 路径。四路至(浮点 x1、浮点 y1、浮点 x2、浮点 y2) | 此方法使用二次线平滑曲线。

(x1，y1)是二次曲线上的控制点，(x2，y2)是二次曲线上的端点。 |

</figure>

现在，让我们开始构建应用程序。此应用程序不需要任何特殊权限。所以保留 **AndroidManifest.xml** 为默认值。

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第二步:在 gradle.build** 中添加依赖项

这个库用来给我们的应用程序添加调色板，这样用户就可以选择他选择的任何颜色

> 实现' petrov . Kristi Yan:color picker-library:1 . 1 . 10 '

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
    tools:context=".MainActivity">

    <LinearLayout
        android:id="@+id/linear"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="vertical">

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="horizontal">

            <ImageButton
                android:id="@+id/btn_undo"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_weight="1"
                android:src="@drawable/ic_undo"
                android:text="Undo" />

            <ImageButton
                android:id="@+id/btn_save"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_weight="1"
                android:src="@drawable/ic_floppy_disk"
                android:text="Save" />

            <ImageButton
                android:id="@+id/btn_color"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_weight="1"
                android:src="@drawable/ic_colorpicker"
                android:text="Color" />

            <ImageButton
                android:id="@+id/btn_stroke"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:layout_weight="1"
                android:src="@drawable/ic_paint_brush"
                android:text="Stroke" />
        </LinearLayout>

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:orientation="vertical">

            <com.google.android.material.slider.RangeSlider
                android:id="@+id/rangebar"
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:visibility="gone" />

        </LinearLayout>

    </LinearLayout>

    <com.raghav.paint.DrawView
        android:id="@+id/draw_view"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:layout_below="@id/linear"
        android:layout_centerInParent="true" />

</RelativeLayout>
```

**第四步:创建笔画类**

参考[如何在安卓工作室](https://www.geeksforgeeks.org/how-to-create-classes-in-android-studio/)中创建类。并将班级命名为**笔画**。以下是**Stroke.java**文件的代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.graphics.Path;

public class Stroke {

    // color of the stroke
    public int color;

    // width of the stroke
    public int strokeWidth;

    // a Path object to
    // represent the path drawn
    public Path path;

    // constructor to initialise the attributes
    public Stroke(int color, int strokeWidth, Path path) {
        this.color = color;
        this.strokeWidth = strokeWidth;
        this.path = path;
    }
}
```

**第五步:** **创建绘图视图类**

同样，创建一个新的 java 类，并将该类命名为 **DrawView** 。以下是**DrawView.java**文件的代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.content.Context;
import android.graphics.Bitmap;
import android.graphics.Canvas;
import android.graphics.Color;
import android.graphics.Paint;
import android.graphics.Path;
import android.util.AttributeSet;
import android.view.MotionEvent;
import android.view.View;

import java.util.ArrayList;

public class DrawView extends View {

    private static final float TOUCH_TOLERANCE = 4;
    private float mX, mY;
    private Path mPath;

    // the Paint class encapsulates the color
    // and style information about
    // how to draw the geometries,text and bitmaps
    private Paint mPaint;

    // ArrayList to store all the strokes
    // drawn by the user on the Canvas
    private ArrayList<Stroke> paths = new ArrayList<>();
    private int currentColor;
    private int strokeWidth;
    private Bitmap mBitmap;
    private Canvas mCanvas;
    private Paint mBitmapPaint = new Paint(Paint.DITHER_FLAG);

    // Constructors to initialise all the attributes
    public DrawView(Context context) {
        this(context, null);
    }

    public DrawView(Context context, AttributeSet attrs) {
        super(context, attrs);
        mPaint = new Paint();

        // the below methods smoothens
        // the drawings of the user
        mPaint.setAntiAlias(true);
        mPaint.setDither(true);
        mPaint.setColor(Color.GREEN);
        mPaint.setStyle(Paint.Style.STROKE);
        mPaint.setStrokeJoin(Paint.Join.ROUND);
        mPaint.setStrokeCap(Paint.Cap.ROUND);

        // 0xff=255 in decimal
        mPaint.setAlpha(0xff);

    }

    // this method instantiate the bitmap and object
    public void init(int height, int width) {

        mBitmap = Bitmap.createBitmap(width, height, Bitmap.Config.ARGB_8888);
        mCanvas = new Canvas(mBitmap);

        // set an initial color of the brush
        currentColor = Color.GREEN;

        // set an initial brush size
        strokeWidth = 20;
    }

    // sets the current color of stroke
    public void setColor(int color) {
        currentColor = color;
    }

    // sets the stroke width
    public void setStrokeWidth(int width) {
        strokeWidth = width;
    }

    public void undo() {
        // check whether the List is empty or not
        // if empty, the remove method will return an error
        if (paths.size() != 0) {
            paths.remove(paths.size() - 1);
            invalidate();
        }
    }

    // this methods returns the current bitmap
    public Bitmap save() {
        return mBitmap;
    }

    // this is the main method where
    // the actual drawing takes place
    @Override
    protected void onDraw(Canvas canvas) {
        // save the current state of the canvas before,
        // to draw the background of the canvas
        canvas.save();

        // DEFAULT color of the canvas
        int backgroundColor = Color.WHITE;
        mCanvas.drawColor(backgroundColor);

        // now, we iterate over the list of paths
        // and draw each path on the canvas
        for (Stroke fp : paths) {
            mPaint.setColor(fp.color);
            mPaint.setStrokeWidth(fp.strokeWidth);
            mCanvas.drawPath(fp.path, mPaint);
        }
        canvas.drawBitmap(mBitmap, 0, 0, mBitmapPaint);
        canvas.restore();
    }

    // the below methods manages the touch
    // response of the user on the screen

    // firstly, we create a new Stroke
    // and add it to the paths list
    private void touchStart(float x, float y) {
        mPath = new Path();
        Stroke fp = new Stroke(currentColor, strokeWidth, mPath);
        paths.add(fp);

        // finally remove any curve
        // or line from the path
        mPath.reset();

        // this methods sets the starting
        // point of the line being drawn
        mPath.moveTo(x, y);

        // we save the current
        // coordinates of the finger
        mX = x;
        mY = y;
    }

    // in this method we check
    // if the move of finger on the
    // screen is greater than the
    // Tolerance we have previously defined,
    // then we call the quadTo() method which
    // actually smooths the turns we create,
    // by calculating the mean position between
    // the previous position and current position
    private void touchMove(float x, float y) {
        float dx = Math.abs(x - mX);
        float dy = Math.abs(y - mY);

        if (dx >= TOUCH_TOLERANCE || dy >= TOUCH_TOLERANCE) {
            mPath.quadTo(mX, mY, (x + mX) / 2, (y + mY) / 2);
            mX = x;
            mY = y;
        }
    }

    // at the end, we call the lineTo method
    // which simply draws the line until
    // the end position
    private void touchUp() {
        mPath.lineTo(mX, mY);
    }

    // the onTouchEvent() method provides us with
    // the information about the type of motion
    // which has been taken place, and according
    // to that we call our desired methods
    @Override
    public boolean onTouchEvent(MotionEvent event) {
        float x = event.getX();
        float y = event.getY();

        switch (event.getAction()) {
            case MotionEvent.ACTION_DOWN:
                touchStart(x, y);
                invalidate();
                break;
            case MotionEvent.ACTION_MOVE:
                touchMove(x, y);
                invalidate();
                break;
            case MotionEvent.ACTION_UP:
                touchUp();
                invalidate();
                break;
        }
        return true;
    }
}
```

**第 6 步:使用****MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import android.content.ContentValues;
import android.graphics.Bitmap;
import android.graphics.Color;
import android.net.Uri;
import android.os.Bundle;
import android.os.Environment;
import android.provider.MediaStore;
import android.view.View;
import android.view.ViewTreeObserver;
import android.widget.ImageButton;

import androidx.annotation.NonNull;
import androidx.appcompat.app.AppCompatActivity;

import com.google.android.material.slider.RangeSlider;

import java.io.OutputStream;

import petrov.kristiyan.colorpicker.ColorPicker;

public class MainActivity extends AppCompatActivity {

    // creating the object of type DrawView
    // in order to get the reference of the View
    private DrawView paint;

    // creating objects of type button
    private ImageButton save, color, stroke, undo;

    // creating a RangeSlider object, which will
    // help in selecting the width of the Stroke
    private RangeSlider rangeSlider;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // getting the reference of the views from their ids
        paint = (DrawView) findViewById(R.id.draw_view);
        rangeSlider = (RangeSlider) findViewById(R.id.rangebar);
        undo = (ImageButton) findViewById(R.id.btn_undo);
        save = (ImageButton) findViewById(R.id.btn_save);
        color = (ImageButton) findViewById(R.id.btn_color);
        stroke = (ImageButton) findViewById(R.id.btn_stroke);

        // creating a OnClickListener for each button,
        // to perform certain actions

        // the undo button will remove the most
        // recent stroke from the canvas
        undo.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                paint.undo();
            }
        });

        // the save button will save the current
        // canvas which is actually a bitmap
        // in form of PNG, in the storage
        save.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {

                // getting the bitmap from DrawView class
                Bitmap bmp = paint.save();

                // opening a OutputStream to write into the file
                OutputStream imageOutStream = null;

                ContentValues cv = new ContentValues();

                // name of the file
                cv.put(MediaStore.Images.Media.DISPLAY_NAME, "drawing.png");

                // type of the file
                cv.put(MediaStore.Images.Media.MIME_TYPE, "image/png");

                // location of the file to be saved
                cv.put(MediaStore.Images.Media.RELATIVE_PATH, Environment.DIRECTORY_PICTURES);

                // get the Uri of the file which is to be created in the storage
                Uri uri = getContentResolver().insert(MediaStore.Images.Media.EXTERNAL_CONTENT_URI, cv);
                try {
                    // open the output stream with the above uri
                    imageOutStream = getContentResolver().openOutputStream(uri);

                    // this method writes the files in storage
                    bmp.compress(Bitmap.CompressFormat.PNG, 100, imageOutStream);

                    // close the output stream after use
                    imageOutStream.close();
                } catch (Exception e) {
                    e.printStackTrace();
                }
            }
        });
        // the color button will allow the user
        // to select the color of his brush
        color.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                final ColorPicker colorPicker = new ColorPicker(MainActivity.this);
                colorPicker.setOnFastChooseColorListener(new ColorPicker.OnFastChooseColorListener() {
                    @Override
                    public void setOnFastChooseColorListener(int position, int color) {
                        // get the integer value of color
                        // selected from the dialog box and
                        // set it as the stroke color
                        paint.setColor(color);
                    }
                    @Override
                    public void onCancel() {
                        colorPicker.dismissDialog();
                    }
                })
                        // set the number of color columns
                        // you want  to show in dialog.
                        .setColumns(5)
                        // set a default color selected
                        // in the dialog
                        .setDefaultColorButton(Color.parseColor("#000000"))
                        .show();
            }
        });
        // the button will toggle the visibility of the RangeBar/RangeSlider
        stroke.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {
                if (rangeSlider.getVisibility() == View.VISIBLE)
                    rangeSlider.setVisibility(View.GONE);
                else
                    rangeSlider.setVisibility(View.VISIBLE);
            }
        });

        // set the range of the RangeSlider
        rangeSlider.setValueFrom(0.0f);
        rangeSlider.setValueTo(100.0f);

        // adding a OnChangeListener which will
        // change the stroke width
        // as soon as the user slides the slider
        rangeSlider.addOnChangeListener(new RangeSlider.OnChangeListener() {
            @Override
            public void onValueChange(@NonNull RangeSlider slider, float value, boolean fromUser) {
                paint.setStrokeWidth((int) value);
            }
        });

        // pass the height and width of the custom view
        // to the init method of the DrawView object
        ViewTreeObserver vto = paint.getViewTreeObserver();
        vto.addOnGlobalLayoutListener(new ViewTreeObserver.OnGlobalLayoutListener() {
            @Override
            public void onGlobalLayout() {
                paint.getViewTreeObserver().removeOnGlobalLayoutListener(this);
                int width = paint.getMeasuredWidth();
                int height = paint.getMeasuredHeight();
                paint.init(height, width);
            }
        });
    }
}
```