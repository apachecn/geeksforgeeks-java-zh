# 旋转图像的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序旋转图像/](https://www.geeksforgeeks.org/java-program-to-rotate-an-image/)

问题陈述是将图像顺时针旋转 90 度，在这里我们将使用 BufferedImage 类和 Color c 的一些内置方法

执行操作所需的类如下:

*   To read and write image files, we must import the file class. This class usually represents file and directory pathnames.
*   In order to handle errors, we use the IOException class.
*   In order to save the image, we used the BufferedImage class to create the BufferedImage object. This object is used to store images in memory.
*   To read and write images, we will import the ImageIO class. This class has static methods for reading and writing images.
*   This Graphics2D class extends the Graphics class to provide more complex control over geometry, coordinate transformation, color management and text layout. This is the basic class for presenting 2D shapes, texts and images on Java TM platform.

**例:**

## 爪哇

```java
// Java program to rotate image by 90 degrees clockwise

// Importing classes from java.awt package for
// painting graphics and images
import java.awt.Graphics2D;
import java.awt.image.BufferedImage;
// Importing input output classes
import java.io.File;
import java.io.IOException;
import javax.imageio.ImageIO;

// Main class
public class GFG {

    // Method 1
    // To return rotated image
    public static BufferedImage rotate(BufferedImage img)
    {

        // Getting Dimensions of image
        int width = img.getWidth();
        int height = img.getHeight();

        // Creating a new buffered image
        BufferedImage newImage = new BufferedImage(
            img.getWidth(), img.getHeight(), img.getType());

        // creating Graphics in buffered image
        Graphics2D g2 = newImage.createGraphics();

        // Rotating image by degrees using toradians()
        // method
        // and setting new dimension t it
        g2.rotate(Math.toRadians(90), width / 2,
                  height / 2);
        g2.drawImage(img, null, 0, 0);

        // Return rotated buffer image
        return newImage;
    }

    // Method 2
    // Main driver method
    public static void main(String[] args)
    {
        // try block to check for exceptions
        try {

            // Reading original image
            BufferedImage originalImg = ImageIO.read(
                new File("D:/test/Image.jpeg"));

            // Getting and Printing dimensions of original
            // image
            System.out.println("Original Image Dimension: "
                               + originalImg.getWidth() + "x"
                               + originalImg.getHeight());

            // Creating a subimage of given dimensions
            BufferedImage SubImg = rotate(originalImg);

            // Printing Dimensions of new image created
            // (Rotated image)
            System.out.println("Cropped Image Dimension: "
                               + SubImg.getWidth() + "x"
                               + SubImg.getHeight());

            // Creating new file for rotated image
            File outputfile
                = new File("D:/test/ImageRotated.jpeg");

            // Writing image in new file created
            ImageIO.write(SubImg, "jpg", outputfile);

            // Printing executed message
            System.out.println(
                "Image rotated successfully: "
                + outputfile.getPath());
        }

        // Catch block to handle the exception
        catch (IOException e) {

            // Print the line number where exception
            // occurred
            e.printStackTrace();
        }
    }
}
```