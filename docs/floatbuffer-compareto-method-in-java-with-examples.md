# Java 中的 FloatBuffer compareTo()方法示例

> 原文:[https://www . geeksforgeeks . org/float buffer-compare to-method-in-Java-with-examples/](https://www.geeksforgeeks.org/floatbuffer-compareto-method-in-java-with-examples/)

类的 **compareTo()** 方法用于比较一个缓冲区和另一个缓冲区。两个浮动缓冲区通过按字典顺序比较剩余元素的序列来进行比较，而不考虑每个序列在其相应缓冲区内的起始位置。除了-0.0 和 0.0 被认为是相等的之外，对浮点元素的比较就像调用 Float.compare(float，float)一样。漂浮。该方法认为 NaN 等于其自身，并且大于所有其他浮点值(包括 float。正数 _ 无穷大)。浮动缓冲区无法与任何其他类型的对象相比较。

**语法:**

```
public int compareTo(FloatBuffer that)
```

**参数:**该方法将一个**浮动缓冲对象**作为参数，与该缓冲区进行比较。

**返回值:**该方法返回一个**负整数、零或一个正整数**，因为该缓冲区小于、等于或大于给定的缓冲区。

下面是说明 compareTo()方法的示例:

**例 1:** 当两个浮动缓冲器相等时。

```
// Java program to demonstrate
// compareTo() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the fb
        int capacity1 = 3;

        // Creating the FloatBuffer
        try {

            // creating object of floatbuffer fb
            // and allocating size capacity
            FloatBuffer fb = FloatBuffer.allocate(capacity1);

            // putting the value in fb
            fb.put(9.56F);
            fb.put(7.61F);
            fb.put(4.61F);

            // revind the float buffer
            fb.rewind();

            // print the FloatBuffer
            System.out.println("FloatBuffer fb: "
                               + Arrays.toString(fb.array()));

            // creating object of floatbuffer fb1
            // and allocating size capacity
            FloatBuffer fb1 = FloatBuffer.allocate(capacity1);

            // putting the value in fb1
            fb1.put(9.56F);
            fb1.put(7.61F);
            fb1.put(4.61F);

            // revind the float buffer
            fb1.rewind();

            // print the FloatBuffer
            System.out.println("FloatBuffer fb1: "
                               + Arrays.toString(fb1.array()));

            // compare both buffer and store the value into integer
            int i = fb.compareTo(fb1);

            // if else condition
            if (i == 0)
                System.out.println("\nboth buffer are lexicographically equal");
            else if (i >= 0)
                System.out.println("\nfb is lexicographically greater than fb1");
            else
                System.out.println("\nfb is lexicographically less than fb1");
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception throws : " + e);
        }

        catch (ReadOnlyBufferException e) {
            System.out.println("Exception throws : " + e);
        }
    }
}
```

**Output:**

```
FloatBuffer fb: [9.56, 7.61, 4.61]
FloatBuffer fb1: [9.56, 7.61, 4.61]

both buffer are lexicographically equal

```

**示例 2:** 当该浮动填充大于传递的浮动填充时

```
// Java program to demonstrate
// compareTo() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the fb
        int capacity1 = 3;

        // Creating the FloatBuffer
        try {

            // creating object of floatbuffer fb
            // and allocating size capacity
            FloatBuffer fb = FloatBuffer.allocate(capacity1);

            // putting the value in fb
            fb.put(9.56F);
            fb.put(7.61F);
            fb.put(4.61F);

            // revind the float buffer
            fb.rewind();

            // print the FloatBuffer
            System.out.println("FloatBuffer fb: "
                               + Arrays.toString(fb.array()));

            // creating object of floatbuffer fb1
            // and allocating size capacity
            FloatBuffer fb1 = FloatBuffer.allocate(capacity1);

            // putting the value in fb1
            fb1.put(8.56F);
            fb1.put(7.61F);
            fb1.put(4.61F);

            // revind the float buffer
            fb1.rewind();

            // print the FloatBuffer
            System.out.println("FloatBuffer fb1: "
                               + Arrays.toString(fb1.array()));

            // compare both buffer and store the value into integer
            int i = fb.compareTo(fb1);

            // if else condition
            if (i == 0)
                System.out.println("\nboth buffer are lexicographically equal");
            else if (i >= 0)
                System.out.println("\nfb is lexicographically greater than fb1");
            else
                System.out.println("\nfb is lexicographically less than fb1");
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception throws : " + e);
        }

        catch (ReadOnlyBufferException e) {
            System.out.println("Exception throws : " + e);
        }
    }
}
```

**Output:**

```
FloatBuffer fb: [9.56, 7.61, 4.61]
FloatBuffer fb1: [8.56, 7.61, 4.61]

fb is lexicographically greater than fb1

```

**示例 3:** 当该浮动填充小于传递的浮动填充时

```
// Java program to demonstrate
// compareTo() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the fb
        int capacity1 = 3;

        // Creating the FloatBuffer
        try {

            // creating object of floatbuffer fb
            // and allocating size capacity
            FloatBuffer fb = FloatBuffer.allocate(capacity1);

            // putting the value in fb
            fb.put(8.56F);
            fb.put(7.61F);
            fb.put(4.61F);

            // revind the float buffer
            fb.rewind();

            // print the FloatBuffer
            System.out.println("FloatBuffer fb: "
                               + Arrays.toString(fb.array()));

            // creating object of floatbuffer fb1
            // and allocating size capacity
            FloatBuffer fb1 = FloatBuffer.allocate(capacity1);

            // putting the value in fb1
            fb1.put(9.56F);
            fb1.put(7.61F);
            fb1.put(4.61F);

            // revind the float buffer
            fb1.rewind();

            // print the FloatBuffer
            System.out.println("FloatBuffer fb1: "
                               + Arrays.toString(fb1.array()));

            // compare both buffer and store the value into integer
            int i = fb.compareTo(fb1);

            // if else condition
            if (i == 0)
                System.out.println("\nboth buffer are lexicographically equal");
            else if (i >= 0)
                System.out.println("\nfb is lexicographically greater than fb1");
            else
                System.out.println("\nfb is lexicographically less than fb1");
        }

        catch (IllegalArgumentException e) {
            System.out.println("Exception throws : " + e);
        }

        catch (ReadOnlyBufferException e) {
            System.out.println("Exception throws : " + e);
        }
    }
}
```

**Output:**

```
FloatBuffer fb: [8.56, 7.61, 4.61]
FloatBuffer fb1: [9.56, 7.61, 4.61]

fb is lexicographically less than fb1

```