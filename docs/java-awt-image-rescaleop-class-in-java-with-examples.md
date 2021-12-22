# Java . awt . image . rescalop Java 中的类，带示例

> 原文:[https://www . geesforgeks . org/Java-awt-image-rescalopo-class-in-Java-with-examples/](https://www.geeksforgeeks.org/java-awt-image-rescaleop-class-in-java-with-examples/)

**rescalop**是 **java.awt.image 包**中的一个类，实现**bufferedmageop**和 **RasterOp** 接口。此类通过将每个像素的样本值乘以一个比例因子，然后加上一个偏移量，对源图像中的数据执行逐个像素的重新缩放。缩放后的样本值被裁剪为目标图像中的最小/最大表示。这个类用于图片处理。

*   对于**栅格**，对波段进行重新缩放。缩放常数集的数量可以是一个，在这种情况下，相同的常数将应用于所有波段，或者它必须等于源栅格波段的数量。
*   对于**buffer dimages**，重新缩放对颜色进行操作。缩放常数集的数量可以是一个，在这种情况下，相同的常数被应用于所有颜色分量。
*   带有**索引颜色模型**的图像不能重新缩放。
*   如果在构造函数中指定了一个**渲染提示**对象，当需要颜色转换时，可以使用颜色渲染提示和抖动提示。

**语法:**

```
public class RescaleOp
extends Object
implements BufferedImageOp, RasterOp
```

**施工人员:**

*   **公共重缩放(float[] scaleFactors，float[]offset，RenderingHints 提示):**具有所需的 scaleFactors 和 offset 的构造函数。提示可以为空。
*   **公共缩放因子(浮点缩放因子，浮点偏移，渲染提示提示):**带有 singlt 缩放因子和偏移的构造函数。提示可以为空。

**方法:**

*   **BufferedImage createcompatibledestinimage？(BufferedImage src，ColorModel destCM):** 此方法创建一个带区大小和数量正确的归零目标图像。
*   **WritableRaster createCompatibleDestRaster？(栅格 src):** 在给定该源的情况下，该方法创建具有正确大小和波段数的零目标栅格。
*   **BufferedImage 滤镜？(BufferedImage src，BufferedImage dst):** 此方法重新缩放源 BufferedImage。
*   **可写光栅滤波器？(栅格 src，可写栅格 dst):** 此方法重新调整源栅格中的像素数据。
*   **Rectangle2D getbound2d？(BufferedImage src):** 此方法返回重新缩放的目标图像的边界框。
*   **Rectangle2D getbound2d？(栅格 src):** 此方法返回重新缩放后的目标栅格的边界框。
*   **int getNumFactors？():**此方法返回此重缩放中使用的缩放因子和偏移量的数量。
*   **float[]getoffset？(float[]offset):**此方法返回给定数组中的偏移量。
*   **点 2D getPoint2D？(Point2D srcPt，Point2D dstPt):** 此方法返回源中给定点的目标点的位置。
*   **渲染提示 getRenderingHints？():**此方法返回此操作的渲染提示
*   **float[] getScaleFactors？(float[] scaleFactors):** 此方法返回给定数组中的比例因子。

**示例 1:** 在给定的示例中，我们将使用单个比例因子和偏移来设置图片的对比度。以下代码将亮度降低 25%，像素暗 3.6 倍。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.awt.image.*;
import java.net.*;
import java.awt.*;
import java.io.*;
import javax.imageio.*;

public class DemoonRescaleop {

    public static void main(String[] args) throws Exception
    {
        // picking the image from the url
        URL url
            = new URL("https:// media.geeksforgeeks.org"
                      + "/wp-content/uploads/geeksforgeeks-9.png");

        // Reading the image from url
        Image image = ImageIO.read(url);

        // Setting up the scaling and
        // the offset parameters for processing
        RescaleOp rop = new RescaleOp(.75f, 3.6f, null);

        // applying the parameters on the image
        // by using filter() method, it takes the
        // Source and destination objects of buffered reader
        // here our destination object is null
        BufferedImage bi
            = rop.filter((BufferedImage)image, null);
        ImageIO.write(bi, "png",
                      new File("processed.png"));
    }
}
```

**Input:**![Original Image](img/c6e0a168008bc4a43314f9fb895e5c7c.png)

原象

**输出:**

![processed.png](img/696fdbdde7bb7125cfde7daf66b9e469.png)

processed.png

使用的方法**过滤器(BufferedImage src，BufferedImage dst)** 将源 BufferedImage 重新缩放到目标 BufferedImage，并返回相同的值。在这里，我们没有提到任何目的地图像，并写空来代替它。这里，我们已经为 BufferedImage 对象分配了重新缩放的结果。

**示例 2:** 在给定的示例中，我们将使用比例因子和偏移量的数组来设置图片的对比度。
每个阵列的大小为 3，表示每个像素的红色、绿色和蓝色分量。在下面的代码中，整体亮度增加了 45%，所有像素颜色都向绿色偏移。偏移 150 会将每个像素的绿色分量增加 58.6%(150/256)。请记住，偏移会添加到颜色值中，因此必须是 0 到 255 之间的值，而不是比例因子，比例因子是百分比。

## Java 语言(一种计算机语言，尤用于创建网站)

```
import java.awt.image.*;
import java.net.*;
import java.awt.*;
import java.io.*;
import javax.imageio.*;
public class DemoonRescaleop {

    public static void main(String[] args) throws Exception
    {
        // picking the image from the URL
        URL url
            = new URL("https:// media.geeksforgeeks.org"
                      + "/wp-content/uploads/geeksforgeeks-9.png");

        // Reading the image from url
        Image image = ImageIO.read(url);

        // Setting up the scaling and
        // the offset parameters for processing
        float[] factors = new float[] {

            // RGB each value for 1 color
            1.45f, 1.45f, 1.45f
        };

        float[] offsets = new float[] {
            0.0f, 150.0f, 0.0f
        };

        RescaleOp rop
            = new RescaleOp(factors, offsets, null);

        // applying the parameters on the image
        // by using filter() method, it takes the
        // Source and destination objects of buffered reader
        // here our destination object is null
        BufferedImage bi
            = rop.filter((BufferedImage)image, null);
        ImageIO.write(bi, "png",
                      new File("processed.png"));
    }
}
```

**Input:**![Original Image](img/c6e0a168008bc4a43314f9fb895e5c7c.png)

原象

**输出:**

![](img/7a9ca0d9fd976d82705cd2779eed2722.png)

processed.png

使用的方法**过滤器(BufferedImage src，BufferedImage dst)** 将源 BufferedImage 重新缩放到目标 BufferedImage，并返回相同的值。在这里，我们没有提到任何目的地图像，并写空来代替它。这里，我们已经为 BufferedImage 对象分配了重新缩放的结果。

**参考:**[https://docs . Oracle . com/javase/9/docs/API/Java/awt/image/rescalopo . html](https://docs.oracle.com/javase/9/docs/api/java/awt/image/RescaleOp.html)