# Java 中 ObjectInputStream 和 ObjectOutputStream 的区别

> 原文:[https://www . geeksforgeeks . org/objectinputstream-和-objectoutputstream-in-Java/](https://www.geeksforgeeks.org/difference-between-objectinputstream-and-objectoutputstream-in-java/)之间的区别

在一个软件项目中，在很多情况下，都需要传输数据，可以使用 Java IO 包中的 [ObjectOutputStream](https://www.geeksforgeeks.org/java-io-objectoutputstream-class-java-set-1/) 和 [ObjectInputStream](https://www.geeksforgeeks.org/java-io-objectinputstream-class-java-set-2/) 进行处理。通常，数据以二进制格式写入，因此我们无法查看其内容。[序列化](https://www.geeksforgeeks.org/serialization-in-java/)是将对象写入输出流的过程。我们可以编写一个类对象本身，它包含 Java 对象的原始数据类型和图形的组合。反序列化是从输入流重建对象的过程。

**实现:**让我们看到带有插图的对象输出流，为此我们创建了一个名为“车辆规格”的 [POJO 类](https://www.geeksforgeeks.org/pojo-vs-java-beans/)。

> **注意:**应该实现 Serializable，否则会抛出 Java . io . notserializableexception。

**例 1:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java Program simply illustrating POJO / Model class

// Importing input output class
import java.io.Serializable;

// Class 1
// Implements Serializable  for POJO class to aavoid
// NotSerializableException will be thrown
public class VehicleSpecifications implements Serializable {

    // Member variables of this class
    private String color;
    private String type;
    private String name;
    private double price;

    // Constructors of this class

    // Constructor- 1
    // Default constructor
    public VehicleSpecifications() {}

    // Constructor- 2
    // Parameterized constructor accepting all attributes and
    // helps to create a VehicleSpecifications class
    public VehicleSpecifications(String color, String type,
                                 String name, double price)
    {

        // This keyword refers to current object itself
        this.color = color;
        this.type = type;
        this.name = name;
        this.price = price;
    }

    // Methods of this class
    // Specfically  Getter and Setter methods

    // Method 1
    public double getPrice() { return price; }

    // Method 2
    public void setPrice(double price)
    {
        this.price = price;
    }

    // Method 3
    public String getName() { return name; }

    // Method 4
    public void setName(String name) { this.name = name; }

    // Method 5
    public String getColor() { return color; }

    // Method 6
    public void setColor(final String color)
    {
        this.color = color;
    }

    // Method 7
    public String getType() { return type; }

    // Method 8
    public void setType(final String type)
    {
        this.type = type;
    }
}
```

> 没有输出，因为到目前为止，我们只实现了构造函数和定义的方法体，包括 getters 和 setters。
> 
> 现在让我们创建几个车辆规格，并将它们写入一个文件中。当 VehicleSpecifications 实现 Serializable 功能时，数据可以以二进制格式写入文件。为此，我们将使用“writeObject”函数，通过使用该函数，我们可以使用 ObjectOutputStream 提供的写方法来写类属性。

**例 2:**

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Class 2
// Java Program to Create Few VehicleSpecifcation and
// Writing in a File

// Importing required classes from packages
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.ObjectOutputStream;
import java.util.ArrayList;
import java.util.List;

// Main class
public class VehicleSpecificationsSerializer {

    // main driver method
    public static void main(String[] args)
    {

        // Output file been passed in a string
        String sampleOutputFile = "VehicleSpecifcation.db";

        // Try block to check for exceptions
        try {

            // Create a objectoutputstream accepting the
            // file name as VehicleSpecifcation.db
            ObjectOutputStream vehicleObjectOutput
                = new ObjectOutputStream(
                    new FileOutputStream(sampleOutputFile));

            // Create a list of VehicleSpecifications class
            List<VehicleSpecifications> listSpecifications
                = new ArrayList<VehicleSpecifications>();

            // Add the necessary data using standard add()
            // method Custom input
            listSpecifications.add(
                new VehicleSpecifications("Radiant Red",
                                          "SUV", "WR-V",
                                          1700000f));

            listSpecifications.add(
                new VehicleSpecifications("Metallic Blue",
                                          "SUV", "WR-V",
                                          1800000f));

            listSpecifications.add(
                new VehicleSpecifications(
                    "Black", "SUV", "WR-V", 1900000f));

            // We are writing the whole object into the file
            // which is a list item of VehicleSpecifications
            // object
            vehicleObjectOutput.writeObject(
                listSpecifications);

            // Closing the connection to release memory
            vehicleObjectOutput.close();
        }

        // Catch block to handle the exceptions
        catch (IOException ex) {

            // Print the exceptions along with line number
            // using printStackTrace() method
            ex.printStackTrace();
        }
    }
}
```