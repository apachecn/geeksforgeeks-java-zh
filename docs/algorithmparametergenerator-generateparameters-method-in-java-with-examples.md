# Java 中的算法参数生成器生成参数()方法，示例

> 原文:[https://www . geesforgeks . org/algorithm parameters generator-generate parameters-method-in-Java-with-examples/](https://www.geeksforgeeks.org/algorithmparametergenerator-generateparameters-method-in-java-with-examples/)

使用**Java . security . algorithm parameters generator**类的 **generateParameters()** 方法来生成参数。
**语法:**

```
public final AlgorithmParameters generateParameters()
```

**返回值:**该方法返回新的**算法参数**对象。
下面是举例说明 **generateParameters()** 方法:
**注意:**以下程序不会在联机 IDE 上运行。
**示例 1:** 对于算法 *DSA*

## Java 语言(一种计算机语言，尤用于创建网站)

```
// Java program to demonstrate
// generateParameters() method

import java.security.*;
import java.util.*;

public class GFG1 {
    public static void main(String[] argv)
    {
        try {
            // creating the object of
            // AlgorithmParameterGenerator
            // and getting instance
            // using getInstance() method
            AlgorithmParameterGenerator
                sr
                = AlgorithmParameterGenerator
                      .getInstance("DSA");

            // initializing the AlgorithmParameterGenerator
            // with 1024 using initialize() method
            sr.init(1024);

            // generating the Parameters
            // using generateParameters() method
            AlgorithmParameters param = sr.generateParameters();

            // printing the keypair
            System.out.println("AlgorithmParameters : " + param);
        }

        catch (NoSuchAlgorithmException e) {

            System.out.println("Exception thrown : " + e);
        }
        catch (ProviderException e) {

            System.out.println("Exception thrown : " + e);
        }
    }
}
```

**Output:** 

```
AlgorithmParameters :
        p:     bb0f976a a9984119 06cea3a8 cf608f99 8bbb5f00 83dc0c2b ab967a42 826f748e
    48a6f081 d86a8ee4 5d5102c0 e86e657b 8b7ab43d a34a70af 96654397 95eb22c9
    9ed614bc 862e10c8 d1cedf48 e84b6bd9 d3bd7027 c297fbb3 a134f282 989d4f0b
    4b103b44 89a43822 6938a4cc 2cf2cec4 5e2f368e 0adb16ac f63bce6d 50fb82fd
        q:     d0447f68 44751e8d 4fe4663b f2d66b6f 40f78285
        g:     ad51837b 7c01e880 013f7768 4244ba4a 79429086 44017899 88e8604a b2f5d2e8
    0c62070b 9793122f 38884ac8 5078d8db 3d0b4a18 71818d2c b10cb34e 388a4bc7
    c8613b26 2f06506b 9c178b21 efbe10ca 98eb8681 555fb56b 3961475f 3f76fa4c
    5abf694c b427b8f2 3b6ee737 d318f8d9 de19433f aa150e62 5931e24f c4dfcd9b
```