# 使用 Java 在 Excel 文件的特定位置创建单元格

> 原文:[https://www . geesforgeks . org/creating-a-cell-at-special-position-in-excel-file-use-Java/](https://www.geeksforgeeks.org/creating-a-cell-at-specific-position-in-excel-file-using-java/)

**[【阿帕奇 POI】](https://www.geeksforgeeks.org/apache-poi-introduction/)**可用于在给定 Excel 文件中特定位置创建单元格。Apache POI 是 Apache 基金会提供的一个 API。

**在给定的 Excel 文件中的特定位置创建单元格的步骤:**

1.  在 eclipse 或安装了 POI 库的 Java 项目中创建一个 maven 项目(Maven 是一个主要用于 Java 项目的构建自动化工具)
2.  在 pom.xml 文件

    ```
    <!-- https://mvnrepository.com/artifact/org.apache.poi/poi -->
    <dependency>
          <groupId>org.apache.poi</groupId>
          <artifactId>poi</artifactId>
          <version>3.12</version>
        </dependency>
        <dependency>
          <groupId>org.apache.poi</groupId>
          <artifactId>poi-ooxml</artifactId>
          <version>3.12</version>
        </dependency>
    ```

    中添加以下 maven 依赖项
3.  在 javaresource 文件夹

    ```
    import java.io.*;
    import org.apache.poi.hssf.usermodel.HSSFWorkbook;
    import org.apache.poi.ss.usermodel.Cell;
    import org.apache.poi.ss.usermodel.Row;
    import org.apache.poi.ss.usermodel.Sheet;
    import org.apache.poi.ss.usermodel.Workbook;

    public class CreateCellAtSpecificPosition {
        public static void main(String[] args) throws FileNotFoundException, IOException
        {
            // Create a workbook instances
            Workbook wb = new HSSFWorkbook();

            OutputStream os = new FileOutputStream("Geeks.xlsx");

            // Creating a sheet using predefined class provided by Apache POI
            Sheet sheet = wb.createSheet("Company Prepration");

            // Creating a row at specific position
            // using predefined class provided by Apache POI

            // Specific row number
            Row row = sheet.createRow(1);

            // Specific cell number
            Cell cell = row.createCell(1);

            // putting value at specific position
            cell.setCellValue("Geeks");

            // writing the content to Workbook
            wb.write(os);

            System.out.println("given cell is created at position (1, 1)");
        }
    }
    ```

    中编写 java 代码

**输出**

```
given cell is created at position (1, 1)
```

**极客 xlsx 文件**
![](img/ae7e5b1ff503c7ebd4cae663a6634439.png)中的输出