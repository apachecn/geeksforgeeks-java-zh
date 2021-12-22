# Java 中的控制抽象，示例

> 原文:[https://www . geesforgeks . org/control-abstraction-in-Java-with-examples/](https://www.geeksforgeeks.org/control-abstraction-in-java-with-examples/)

我们的目标是理解和实现 Java 中的控制抽象。在直接跳到控制抽象之前，让我们理解什么是抽象。

**抽象:**简单来说，抽象绝不是只向用户显示系统的基本特征，而不涉及其细节。例如，一辆汽车及其功能被描述给买方，司机也学习如何使用方向盘和加速器驾驶，但发动机的内部机制不会显示给买方。要阅读更多关于抽象的内容，请参考这里的。

***在抽象上，有两种类型:*** 数据抽象和控制抽象。

**数据抽象**，简单来说就是创建复杂的数据类型，但是只给出最基本的操作。

**控制抽象:**这是指抽象的软件部分，其中程序被简化，不必要的执行细节被移除。

以下是 ***关于控制抽象的要点:***

*   Control abstraction follows the basic rules of DRY code, which means don't repeat yourself. Using functions in programs is the best example of control abstraction.
*   Abstraction can be used to build new functions and combine control statements into a unit.
*   It is the basic feature of all high-level languages, not just java.
*   Higher-order functions, closures and lambdas are several prerequisites for controlling abstraction.
*   More emphasis is placed on how to realize specific functions, rather than describing every detail.
*   Constitute the main unit of structured programming.

**控制流的一个简单算法:**

*   Get resources first.
*   Then execute the block.
*   As soon as the control leaves the block, the resource is closed.

**示例:**

## Java

```
// Abstract class
abstract class Vehicle {
    // Abstract method (does not have a body)
    public abstract void VehicleSound();
    // Regular method
    public void honk() { System.out.println("honk honk"); }
}

// Subclass (inherit from Vehicle)
class Car extends Vehicle {
    public void VehicleSound()
    {
        // The body of VehicleSound() is provided here
        System.out.println("kon kon");
    }
}

class Main {
    public static void main(String[] args)
    {
        // Create a Car object
        Car myCar = new Car();
        myCar.VehicleSound();
        myCar.honk();
    }
}
```

**输出**

```
kon kon
honk honk
```

控制抽象最大的**优势**是它让代码更干净，也更安全。