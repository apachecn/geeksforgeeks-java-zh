# DoubleBuffer put()方法在 Java 中的示例| Set 1

> 原文:[https://www . geesforgeks . org/double buffer-put-methods-in-Java-with-examples-set-1/](https://www.geeksforgeeks.org/doublebuffer-put-methods-in-java-with-examples-set-1/)

### 放(双 f)

**java.nio.DoubleBuffer** 类的 **put(double f)** 方法用于将给定的 double 写入当前位置新创建的 DoubleBuffer 中，然后递增该位置。

**语法:**

```
public abstract DoubleBuffer put(double f)
```

**参数:**该方法将双值 **f** 作为参数写入双缓冲区。

**返回值:**此方法返回**此缓冲区**，其中插入了双精度值。

**异常:**该方法抛出以下异常:

*   **缓冲区溢出异常**–如果该缓冲区的当前位置不小于其极限
*   **只读缓冲区异常**–如果该缓冲区是只读的

以下是举例说明放(双 f)法:
 **例 1:**

```
// Java program to demonstrate
// put() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the DoubleBuffer
        int capacity = 3;

        // Creating the DoubleBuffer
        try {

            // creating object of Doublebuffer
            // and allocating size capacity
            DoubleBuffer db = DoubleBuffer.allocate(capacity);

            // putting the value in Doublebuffer using put() method
            db.put(8.56D);
            db.put(9.61D);
            db.put(7.86D);
            db.rewind();

            // print the DoubleBuffer
            System.out.println("Original DoubleBuffer:  "
                               + Arrays.toString(db.array()));
        }

        catch (BufferOverflowException e) {

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
Original DoubleBuffer:  [8.56, 9.61, 7.86]

```

**示例 2:** 演示 BufferOverflowException。

```
// Java program to demonstrate
// put() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the DoubleBuffer
        int capacity = 3;

        // Creating the DoubleBuffer
        try {

            // creating object of Doublebuffer
            // and allocating size capacity
            DoubleBuffer db = DoubleBuffer.allocate(capacity);

            // putting the value in Doublebuffer using put() method
            db.put(8.56F);
            db.put(9.61F);
            db.put(7.86F);

            System.out.println("Trying to put the Double at the "
                               + "position more than its limit");
            db.put(7.86F);

            // rewind the Doublebuffer
            db.rewind();

            // print the DoubleBuffer
            System.out.println("Original DoubleBuffer:  "
                               + Arrays.toString(db.array()));
        }

        catch (BufferOverflowException e) {

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
Trying to put the Double at the position more than its limit
Exception throws : java.nio.BufferOverflowException

```

**示例 3:** 演示 ReadOnlyBufferException。

```
// Java program to demonstrate
// put() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of theDoubleBuffer
        int capacity = 3;

        // Creating theDoubleBuffer
        try {

            // creating object ofDoublebuffer
            // and allocating size capacity using allocate() method
            DoubleBuffer db = DoubleBuffer.allocate(capacity);

            // Creating a read-only copy ofDoubleBuffer
            // using asReadOnlyBuffer() method
            DoubleBuffer db1 = db.asReadOnlyBuffer();

            System.out.println("Trying to put theDouble value"
                               + " in read only buffer");

            // putting the value in readonlyDoublebuffer
            // using put() method
            db1.put(8.56F);
        }

        catch (BufferOverflowException e) {

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
Trying to put theDouble value in read only buffer
Exception throws : java.nio.ReadOnlyBufferException

```

### put(int index，double f)

**java.nio.DoubleBuffer** 类的 **put(int index，double f)** 方法用于将给定的 double 写入给定索引处的缓冲区。

**语法:**

```
public abstract DoubleBuffer put(int index, double f)
```

**参数:**该方法采用以下参数作为参数:

*   **索引**:将写入双精度的索引
*   **f** :要写入的双精度值

**返回值:**这个方法返回**这个缓冲区。**

异常:此方法引发以下异常:

*   **indexout of boundsexception**–如果索引为负或不小于缓冲区的限制
*   **只读缓冲区异常**–如果该缓冲区是只读的

下面是举例说明 put(int index，double f)方法的例子:

**例 1:**

```
// Java program to demonstrate
// put() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the DoubleBuffer
        int capacity = 3;

        // Creating the DoubleBuffer
        try {

            // creating object of Doublebuffer
            // and allocating size capacity
            DoubleBuffer db = DoubleBuffer.allocate(capacity);

            // putting the value in Doublebuffer using put() at  index 0
            db.put(0, 8.56F);

            // putting the value in Doublebuffer using put() at  index 2
            db.put(2, 9.61F);

            // putting the value in Doublebuffer using put() at  index 1
            db.put(1, 7.86F);

            // rewinding the Doublebuffer
            db.rewind();

            // print the DoubleBuffer
            System.out.println("Original DoubleBuffer:  "
                               + Arrays.toString(db.array()));
        }

        catch (IndexOutOfBoundsException e) {

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
Original DoubleBuffer:  [8.5600004196167, 7.860000133514404, 9.609999656677246]

```

**示例 2:** 演示 IndexOutOfBoundsException。

```
// Java program to demonstrate
// put() method

import java.nio.*;
import java.util.*;

public class GFG {

    public static void main(String[] args)
    {

        // Declaring the capacity of the DoubleBuffer
        int capacity = 3;

        // Creating the DoubleBuffer
        try {

            // creating object of Doublebuffer
            // and allocating size capacity
            DoubleBuffer db = DoubleBuffer.allocate(capacity);

            // putting the value in Doublebuffer
            // using put() at  index 0
            db.put(0, 8.56F);

            // putting the value in Doublebuffer
            // using put() at  index 2
            db.put(2, 9.61F);

            // putting the value in Doublebuffer
            // using put() at  index -1
            System.out.println("Trying to put the value"
                               + " at the negative index");
            db.put(-1, 7.86F);
        }

        catch (IndexOutOfBoundsException e) {

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
Trying to put the value at the negative index
Exception throws : java.lang.IndexOutOfBoundsException

```

**示例 3:** 演示 ReadOnlyBufferException。

```
// Java program to demonstrate
// put() method

import java.nio.*;
import java.util.*;

public class GFG {
    public static void main(String[] args)
    {

        // Declaring the capacity of the DoubleBuffer
        int capacity = 3;

        // Creating the DoubleBuffer
        try {

            // creating object of Doublebuffer
            // and allocating size capacity using allocate() method
            DoubleBuffer db = DoubleBuffer.allocate(capacity);

            // Creating a read-only copy of DoubleBuffer
            // using asReadOnlyBuffer() method
            DoubleBuffer db1 = db.asReadOnlyBuffer();

            System.out.println("Trying to put the Double value"
                               + " in read only buffer");

            // putting the value in readonly Doublebuffer
            // using put() method
            db1.put(0, 8.56F);
        }

        catch (BufferOverflowException e) {

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
Trying to put the Double value in read only buffer
Exception throws : java.nio.ReadOnlyBufferException

```