# 如何用 Java 中的记事本读写 CSV 格式的对象数据？

> 原文:[https://www . geesforgeks . org/how-to-read-write-objects-data-in-CSV-format-use-notepad-in-Java/](https://www.geeksforgeeks.org/how-to-read-write-objects-data-in-csv-format-using-notepad-in-java/)

CSV 代表逗号分隔值。CSV 文件几乎可以用于任何电子表格程序，如微软 Excel 或谷歌电子表格。它们不同于其他电子表格文件类型，因为在一个文件中只能有一个工作表，它们不能保存单元格、列或行。此外，您不能以这种格式保存公式。

现在，以固定格式存储或写入对象的数据成员值意味着文件中有固定长度的记录，我们可以使用 [FileWriter](https://www.geeksforgeeks.org/filewriter-class-in-java/) 、BufferedWriter 和 *String.format()* 的组合，其中 *String.format()* 方法返回给定区域设置、格式和参数的格式化字符串。 [*java 字符串格式()方法*](https://www.geeksforgeeks.org/java-string-format-examples/) 使用给定的区域设置、指定的格式字符串和参数返回格式化的字符串。我们可以使用这个方法连接字符串，同时，我们可以格式化输出的连接字符串。

**进场:**

**A.** 文件读取

1.  使用文件阅读器&缓存器打开一个文件(使用**文件的完全限定名)。**
2.  **使用 split()方法分割以逗号**–**分隔格式读取的数据。**
3.  **读取各个分割值。**
4.  **打印数值。**
5.  **关闭两个阅读器。**

****B.** 文件写入**

1.  **创建任何类对象，并为其数据成员赋值。**
2.  **使用 FileWriter & BufferedWriter 以追加模式创建并打开一个文件(使用文件的完全限定名)。**
3.  **使用 String.format()方法创建一个固定格式的字符串，该字符串包含要写入的对象的数据成员的值。(格式应包含" "，以 CSV 格式存储字符串)**
4.  **使用 BufferedWriter 类的 Write()方法将格式化的字符串写入文件。**
5.  **关闭两个编写器。**

****实现:**这里我们考虑一个客户类，它有两个数据成员，即“姓名”和“账号”。在读取时，我们需要读取文件&中以 CSV 格式写入的数据，分割读取的数据。*在编写 w* 时，我们需要将客户类型(CSV 格式)的每个对象的每个数据成员的值保存在一个名为“CustomerData.txt”的文件中。我们正在使用 String 类的 format()方法创建一个*字符串格式*，该格式包含 30 字节的客户名称文件&和 10 字节的客户账号(将每个对象的数据成员保存为*相同的格式)。例如:***

```java
*String.format("%30s ,%10d",name, acc_No);*
```

> *****注意:** replaceAll()方法用于从读取的数据中删除所有的空格(//s，Unicode)。***

*****示例:*****

## ***Java 语言(一种计算机语言，尤用于创建网站)***

```java
*// Java Program to Read Write Object's Data in CSV Format
// of FIxed Length Records using Notepad

// Importing input output classes
import java.io.*;
// Importing Scanner class to take input from user
import java.util.Scanner;

// Class 1
// Helper class
class Customer {

    // Member variables
    private String name = null;
    private long account_No;
    private static long auto_Generate_AccNo = 100;

    // Constructor of this class
    Customer(String nm)
    {
        account_No = auto_Generate_AccNo;
        auto_Generate_AccNo++;
        name = nm;
    }

    // Methods of this class
    public String getCustomerName() { return name; }
    public long getAccNo() { return account_No; }
}

// Class 2
// Main Class
public class Main {

    // Main driver method
    public static void main(String[] args)
    {
        // Custom input character
        char ch = 'y';
        int menuCh = 0;
        int exitStatus = 0;

        // Display commands
        System.out.println("Menu");
        System.out.println("1\. For Creating New Customer ");
        System.out.println(" And saving it to the file");
        System.out.println("2\. For Viewing File");
        System.out.println("3\. For Exitn\n");

        // Checking to erupt case sensativity of input
        // character
        while (ch == 'y' || ch == 'Y') {
            // Asking user to enter the choice
            System.out.println("Enter Your Choice");

            // Scanner class object to take users choice
            Scanner sc = new Scanner(System.in);

            menuCh = sc.nextInt();

            // Switch case
            switch (menuCh) {
            case 1:
                createNewCustomerAndSave();

                // Break statement will immediately hault
                // further execution
                break;
            case 2:
                viewFile();
                break;
            case 3:
                exitStatus = 1;
                break;

            // Case if above all cases do not hit
            default:
                System.out.println("Wrong Choice");
                break;
            }

            // Checking exit status
            if (exitStatus == 1) {
                break;
            }

            // Asking from user
            System.out.println("Wanna Work More??? Yes/No");

            // skip /n ie newline
            ch = sc.next().charAt(0);
            ;
        }
    }

    // Method
    // To view the file
    public static void viewFile()
    {

        // Try block to check for exceptions
        try {
            System.out.println("Customers are : ");

            // Creating object of File class to get file
            // path
            File myObj = new File("CustomerData.txt");

            myObj.createNewFile();

            if (myObj.length() != 0) {
                Scanner myReader = new Scanner(myObj);
                myReader.useDelimiter(",");

                while (myReader.hasNextLine()) {
                    String str = myReader.nextLine();

                    // trim spaces
                    str = str.replaceAll("\\s", "");
                    String[] splitString = str.split(",");
                    String name = splitString[0];
                    long acc_No
                        = Long.valueOf(splitString[1]);
                    System.out.print("Name : " + name);
                    System.out.println(
                        " And account no is : " + acc_No);
                }
                myReader.close();
            }
        }

        // Catch block to handle the exceptions
        catch (Exception e) {
            System.out.println("An error occurred." + e);
            e.printStackTrace();
        }
    }

    // Method
    public static void createNewCustomerAndSave()
    {
        String name = null;
        String date = null;

        Scanner sc = new Scanner(System.in);
        System.out.println("Enter Customer's Name");
        name = sc.nextLine();
        Customer c1 = new Customer(name);
        String dataToBeWriiten = null;
        try {
            File myObj = new File("CustomerData.txt");
            myObj.createNewFile();
            FileWriter myWriter1 = null;
            myWriter1
                = new FileWriter("CustomerData.txt", true);
            BufferedWriter myWriter
                = new BufferedWriter(myWriter1);
            long AccNo = c1.getAccNo();
            dataToBeWriiten
                = String.format("%30s ,%10d", name, AccNo);
            myWriter.write(dataToBeWriiten);

            myWriter.write(
                System.lineSeparator()); // to insert a new
                                         // line in file
            myWriter.close();
            System.out.println(
                "Successfully wrote to the file.\n");
        }
        catch (IOException e) {
            System.out.println("An error occurred.");
            e.printStackTrace();
        }
    }
}*
```

*****输出:**获得两个不同的输出***

*   ***输出 1:当我们第一次跑步时***
*   ***输出 2::当程序在第一次运行后再次运行时***

*****输出 1:** 我们第一次跑步的时候***

```java
*Menu
1\. For Creating New Customer and saving it to the file
2\. For Viewing File
3\. For Exitn

Enter Your Choice
1
Enter Customer's Name
Ramesh
Successfully wrote to the file.

Wanna Work More??? Yes/No
Y
Enter Your Choice
1
Enter Customer's Name
Rohan
Successfully wrote to the file.

Wanna Work More??? Yes/No
y
Enter Your Choice
2
Customers are : 
Name : Ramesh And account no is : 100
Name : Rohan And account no is : 101
Wanna Work More??? Yes/No
N*
```

***此外，在执行之后，创建了“customerdata . txt”&它包含以下内容:***

```java
*Ramesh ,       100
Rohan ,       101*
```

*****说明:*****

***正如您在上面看到的，为名称保留了 30 个字节(例如:24 个空格&为 Ramesh 保留了 6 个字节)，为每一行写的账号保留了 10 个字节，因为我们使用了 String.format()来实现这一点。***

***当您将这些行一个接一个地读取为字符串时，该字符串也将包含空格，为了删除这些空格，我们使用了 *replaceAll()* 方法来获得一个没有空格的新字符串。***

```java
*Eg: First line when read, str = " Ramesh, 100"*
```

***当我们使用 replaceAll()时，字符串变成***

```java
*str = “Ramesh,100”*
```

***字符串没有空格，现在有逗号分隔的值。为了单独获取这些值，我们使用 split()方法&获取单独的值并打印它们。***

```java
*Eg : After splitting the str according to ","  in our example we will had:

splitString[0] = Ramesh & splitString[1] = 100*
```

***因此，输出是根据这些分割值打印的***

*****输出 2:** 当程序第一次运行后再次运行时***

```java
*Menu
1\. For Creating New Customer 
And saving it to the file
2\. For Viewing File
3\. For Exitn

Enter Your Choice
1
Enter Customer's Name
Chetan
Successfully wrote to the file.

Wanna Work More??? Yes/No
y
Enter Your Choice
2
Customers are : 
Name : Ramesh And account no is : 100
Name : Rohan And account no is : 101
Name : Chetan And account no is : 100
Wanna Work More??? Yes/No
N*
```

*****输出说明:*****

***现在，在第二次执行之前，您已经拥有了包含两行数据的文件“CustomerData.txt”。***

```java
*Ramesh ,       100
Rohan ,       101*
```

***当您在追加模式下写入数据时，新数据将在文件中已经存在的数据之后写入。因此，文件“CustomerData.txt”将如下所示:***

```java
*Ramesh ,       100
Rohan ,       101
Chetan ,       100*
```

***然后，以与前面相同的方式读取文件&以相同的方式，文件的所有内容被逐行读取，空白被删除&分割完成&最后打印分割数据。***