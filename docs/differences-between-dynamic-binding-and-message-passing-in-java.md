# Java 中动态绑定和消息传递的区别

> 原文:[https://www . geesforgeks . org/Java 中动态绑定和消息传递的区别/](https://www.geeksforgeeks.org/differences-between-dynamic-binding-and-message-passing-in-java/)

**[动态绑定](https://www.geeksforgeeks.org/static-vs-dynamic-binding-in-java/) :** 在动态绑定中编译器不决定要调用的方法。[覆盖](https://www.geeksforgeeks.org/overriding-in-java/)是动态绑定的完美例子。在重写时，父类和子类都有相同的方法。动态绑定也叫**后期绑定**。

**[消息传递](https://www.geeksforgeeks.org/message-passing-in-java/) :**
就计算机而言，消息传递就是进程之间的通信。它是面向对象编程和并行编程中使用的一种通信形式。Java 中的消息传递就像发送一个对象，即从一个线程到另一个线程的消息。当线程没有共享内存，无法共享监视器、信号量或任何其他共享变量来进行通信时，就会使用它。假设我们考虑一个生产者和消费者的例子，同样生产者会生产什么，消费者只能消费什么。我们主要使用队列来实现线程之间的通信。

**我们来看看动态绑定和消息传递的区别:**

| 动态绑定 | 信息传递 |
| --- | --- |
| 绑定指的是将过程调用链接到要响应调用而执行的代码。 | 涉及通信的编程过程称为消息传递。 |
| 它允许在运行时使用同一对象执行不同的代码。 | 它允许开发对象之间的通信。 |
| 使用动态绑定允许在运行时使用同一对象执行不同的代码。 | 它包括三个基本步骤。它们是: |

*   创建类*   创建对象*   Establishing communication happening objects. This is a method of linking procedure calls to related code, which will only be executed at runtime. Message passing is a method of exchanging messages between objects in object-oriented programming. Before the program is executed, the code related to the process is unknown. This process is called late binding. Messaging involves the name of the object, the name of the function and the information to be sent. The function call associated with a polymorphic reference depends on the dynamic type of the reference. As long as an object is alive, it is feasible to communicate with it. In dynamic binding, the code matching the object under the current reference will be called only at runtime. The message of the object is a request to execute the process, so call the function in the receiving object to generate the required result. In short, dynamic binding occurs at runtime. Message transmission occurs between two processes. Dynamic binding is also called dynamic scheduling, late binding or runtime binding. Messaging is also called message exchange. Object-based programming does not support dynamic binding. Object-based programming supports message passing. Object-oriented programming supports dynamic binding. Object-oriented programming also supports message passing.