# 如何用 Java 设置电子表格的打印区域？

> 原文:[https://www . geeksforgeeks . org/如何使用 java 设置电子表格的打印区域/](https://www.geeksforgeeks.org/how-to-set-the-print-area-of-a-spreadsheet-using-java/)

我们可以在电子表格中设置打印区域。这可以使用 Java 的 [**Apache POI**](https://jar-download.com/artifacts/org.apache.poi) 库来完成。我们使用兴趣点库的不同类和方法来设置电子表格的打印区域。通常，它从 Excel 电子表格的左上角到右下角。可以根据要求定制。我们可以打印整个电子表格中特定范围的单元格，自定义纸张大小，打开网格线打印内容，等等。

**创建新工作簿**

我们可以使用不同的兴趣点类创建一个新的工作簿和电子表格。首先，我们必须创建一个工作簿，然后在该工作簿中创建一个电子表格。这里我们使用 XSSFWorkBook 类创建一个名为“workbook”的工作簿对象。然后，我们使用 XSSFSheet 类的 **createSheet()** 函数创建了一个名为“打印区域”的电子表格。

**创建工作簿:**

```
// Create a Work Book
XSSFWorkbook workbook = new XSSFWorkbook();
```

**在工作簿中创建电子表格:**

```
// Create spreadsheet named "Print Area"
XSSFSheet spreadsheet = workbook.createSheet("Print Area");
```

**打印区域的设置**

现在我们使用**设置打印区域()**功能设置打印区域。在这个函数中，我们发送五个值。

```
workbook.setPrintArea(
           0, // sheet index
           0, // start column
           5, // end column
           0, // start row
           5 // end row
     );
```

我们可以使用**设置显示网格线()**功能在打印区域显示网格线。

```
// set display grid lines or not
spreadsheet.setDisplayGridlines(true);
```

要设置纸张尺寸，我们使用**设定纸张尺寸()**功能。

```
// set paper size
spreadsheet.getPrintSetup().setPaperSize(XSSFPrintSetup.A4_PAPERSIZE);
```

如果我们想打印网格线和我们的内容，我们可以通过**设置打印网格线()**功能来实现。

```
// set print grid lines or not
spreadsheet.setPrintGridlines(true);
```

下面是问题陈述的实现:

## 【Java】

```
// Java program to set the print area in spreadsheet

import java.io.*;
import org.apache.poi.xssf.usermodel.XSSFPrintSetup;
import org.apache.poi.xssf.usermodel.XSSFSheet;
import org.apache.poi.xssf.usermodel.XSSFWorkbook;

public class GFG {
    public static void main(String[] args) throws Exception
    {

        // Create a Work Book
        XSSFWorkbook workbook = new XSSFWorkbook();

        // Create spreadsheet named "Print Area"
        XSSFSheet spreadsheet
            = workbook.createSheet("Print Area");

        // Set print area with indexes
        workbook.setPrintArea(0, // Sheet index
                              0, // Start column
                              5, // End column
                              0, // Start row
                              5 // End row
        );

        // Set display grid lines or not
        spreadsheet.setDisplayGridlines(true);

        // Set paper size
        spreadsheet.getPrintSetup().setPaperSize(
            XSSFPrintSetup.A4_PAPERSIZE);

        // Set print grid lines or not
        spreadsheet.setPrintGridlines(true);

        // Enter file path/name here
        FileOutputStream out = new FileOutputStream(
            new File("GFGSpreadsheet.xlsx"));

        workbook.write(out);
        out.close();

        System.out.println(
            "GFGSpreadsheet.xlsx has been created");
    }
}
```