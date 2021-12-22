# 如何在 Java 中调用返回其他方法的方法

> 原文:[https://www . geeksforgeeks . org/how-to-call-a-method-at-return-some-other-method-in-Java/](https://www.geeksforgeeks.org/how-to-call-a-method-that-returns-some-other-method-in-java/)

一个[方法](https://www.geeksforgeeks.org/methods-in-java/)是执行一些特定任务并将结果返回给调用者的语句的集合。一个方法也可以在不返回任何东西的情况下执行一些特定的任务。在本文中，我们将了解如何在 Java 中调用返回其他方法的方法。

在 Java 中，有两种类型的方法。它们是:

1.  **[[static method]](https://www.geeksforgeeks.org/static-methods-vs-instance-methods-java/) :** A static method is a method that can be called in Java without creating a class object. They are referenced by the class name itself or a reference to the class object.
2.  **[Instance method](https://www.geeksforgeeks.org/static-methods-vs-instance-methods-java/) :** Instance method is a method whose class object needs to be created before calling. To call an instance method, we must create an object in which its class is defined.

**调用一个静态方法返回一些其他静态方法:**由于静态方法与它们所在的类相关联(即它们可以被调用，即使没有创建类的实例)，我们可以通过调用方法的定义直接定义一个调用方法的方法。让我们通过以下示例来了解如何做到这一点:

*   **Example 1:** In this example, let's imagine a car. The car must be started before driving. Therefore, the car has the starting function of starting the car. In order for the car to start, its engine must be started first, and other entities must be started, so that the car is finally ready to run. Therefore, this *carstart ()* function needs a signed engineStart () to start the engine. That is,

    ```
    // Java program to visualize the Car

    // A class Car
    public class CarFunc {

        // A method engineStart() which
        // simply starts the engine
        public static void engineStart()
        {
            System.out.println("Engine Started!");
        }

        // A method carStart() which starts
        // the engine and other entities
        // required
        public static void carStart()
        {
            // Calling the function
            // engineStart() inside the
            // definition of function
            // carStart()
            engineStart();

            // Definitions of starting
            // various other entities
            // can be defined here

            // Finally, the car is
            // started
            System.out.println("Car Started!");
        }

        public static void main(String[] args)
        {

            carStart();

            // When the car is started,
            // we are ready to drive
            System.out.println("Let's Drive!");
        }
    }
    ```

    **Output:**

```
Engine Started!
Car Started!
Let's Drive!

```