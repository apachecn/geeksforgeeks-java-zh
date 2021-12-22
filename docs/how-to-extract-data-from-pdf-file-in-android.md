# 如何在安卓系统中从 PDF 文件中提取数据？

> 原文:[https://www . geesforgeks . org/如何从安卓 pdf 文件中提取数据/](https://www.geeksforgeeks.org/how-to-extract-data-from-pdf-file-in-android/)

PDF 是一种便携式文档格式，用于表示图像、表格等数据。如今，PDF 在不同领域的使用迅速增加。许多应用程序已经改用 PDF 文件来表示数据。因此，一些应用程序要求从 PDF 文件中提取数据，并在我们的应用程序中显示这些数据。在本文中，我们将创建一个应用程序来从 PDF 文件中提取数据，并将其显示在我们的应用程序中。

### 我们要建造什么？

在本文中，我们将构建一个简单的应用程序，在该应用程序中，我们将通过单击按钮从 PDF 中提取数据，并在文本视图中显示提取的数据。

### **分步实施**

**第一步:创建新项目**

要在安卓工作室创建新项目，请参考[如何在安卓工作室创建/启动新项目](https://www.geeksforgeeks.org/android-how-to-create-start-a-new-project-in-android-studio/)。注意选择 **Java** 作为编程语言。

**第 2 步:向 build.gradle(模块:应用)添加依赖关系**

导航到**渐变脚本>构建.渐变(模块:应用)**，并在依赖项部分添加以下依赖项。

> 实现' com.itextpdf:itextg:5.5.10 '

添加依赖项后，单击“立即同步”选项并同步项目。添加依赖项后，让我们继续在应用程序中添加一个 PDF 文件。

**第三步:在你的 app 中添加 PDF 文件**

由于我们从 PDF 文件中提取数据，所以我们将在我们的应用程序中添加 PDF 文件。要将 PDF 文件添加到您的应用程序中，我们必须首先创建**原始**文件夹。请参考安卓工作室中的[资源原始文件夹，在安卓中创建一个原始文件夹。创建新的原始目录后，将您的 PDF 文件复制并粘贴到“原始”文件夹中。在您的应用程序中添加该 PDF 文件后，现在我们将在 XML 部分实现。](https://www.geeksforgeeks.org/resource-raw-folder-in-android-studio/)

**第 4 步:使用 activity_main.xml 文件**

转到 **activity_main.xml** 文件，参考以下代码。下面是 **activity_main.xml** 文件的代码。

## 可扩展标记语言

```java
<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity">

    <ScrollView
        android:layout_width="match_parent"
        android:layout_height="match_parent">

        <!--text view for displaying our extracted text-->
        <TextView
            android:id="@+id/idPDFTV"
            android:layout_width="match_parent"
            android:layout_height="match_parent" />

    </ScrollView>

    <!--button for starting extraction process-->
    <Button
        android:id="@+id/idBtnExtract"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentBottom="true"
        android:layout_centerHorizontal="true"
        android:layout_marginBottom="20dp"
        android:text="Extract Text from PDF"
        android:textAllCaps="false" />

</RelativeLayout>
```

在添加了 XML 代码之后，现在我们将转向 Java 部分。

**步骤 5:使用 MainActivity.java 文件**

转到**MainActivity.java**文件，参考以下代码。以下是**MainActivity.java**文件的代码。代码中添加了注释，以更详细地理解代码。

## Java 语言(一种计算机语言，尤用于创建网站)

```java
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.TextView;

import androidx.appcompat.app.AppCompatActivity;

import com.itextpdf.text.pdf.PdfReader;
import com.itextpdf.text.pdf.parser.PdfTextExtractor;

public class MainActivity extends AppCompatActivity {

    // creating variables for
    // button and text view.
    private Button extractPDFBtn;
    private TextView extractedTV;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        // initializing variables for button and text view.
        extractedTV = findViewById(R.id.idPDFTV);
        extractPDFBtn = findViewById(R.id.idBtnExtract);

        // adding on click listener for button
        extractPDFBtn.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                // calling method to extract
                // data from PDF file.
                extractPDF();
            }
        });
    }

    private void extractPDF() {
        try {
            // creating a string for 
            // storing our extracted text.
            String extractedText = "";

            // creating a variable for pdf reader 
            // and passing our PDF file in it.
            PdfReader reader = new PdfReader("res/raw/amiya_rout.pdf");

            // below line is for getting number
            // of pages of PDF file.
            int n = reader.getNumberOfPages();

            // running a for loop to get the data from PDF
            // we are storing that data inside our string.
            for (int i = 0; i < n; i++) {
                extractedText = extractedText + PdfTextExtractor.getTextFromPage(reader, i + 1).trim() + "\n";
                // to extract the PDF content from the different pages
            }

            // after extracting all the data we are 
            // setting that string value to our text view.
            extractedTV.setText(extractedText);

            // below line is used for closing reader.
            reader.close();
        } catch (Exception e) {
            // for handling error while extracting the text file.
            extractedTV.setText("Error found is : \n" + e);
        }
    }
}
```

添加完这段代码后，现在运行您的应用程序并查看代码的输出。

### **输出:**

运行该应用程序后，单击从 PDF 中提取数据按钮，您将看到文本是从 PDF 文件中提取的。

<video class="wp-video-shortcode" id="video-539225-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210101160721/Screenrecorder-2021-01-01-16-05-30-25.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210101160721/Screenrecorder-2021-01-01-16-05-30-25.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210101160721/Screenrecorder-2021-01-01-16-05-30-25.mp4)</video>