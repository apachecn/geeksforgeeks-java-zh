# Java 中状态和策略设计模式的区别

> 原文:[https://www . geesforgeks . org/state-and-strategy-design-pattern-in-Java/](https://www.geeksforgeeks.org/difference-between-state-and-strategy-design-pattern-in-java/)

对于一个 java 开发人员来说，清楚地理解核心 Java 应用程序中状态和策略设计模式之间的区别是很重要的，以便正确地使用它们。

*   Although the state and strategy design patterns have similar structures and are based on the open and closed design principle, representing the "O" from the SOLID design principle, their intentions are completely different.
*   The policy design pattern in Java is used to encapsulate a set of related algorithms, providing the flexibility of the client at runtime. The client can choose any algorithm at runtime without changing the context class that uses the policy object.
*   Some popular examples of patterns are coding, which uses algorithms such as encryption, compression or sorting algorithms.

人们现在可以清楚地看到战略和国家模式之间的区别，它们的意图是不同的。状态模式帮助对象管理状态，而策略模式允许客户端选择不同的行为。另一个不容易看出来的区别是，谁推动了行为的改变。

在策略模式的情况下，它的客户端为上下文提供了不同的策略，在状态模式下，状态转换由上下文或状态本身管理。此外，如果您在 state 对象本身中管理状态转换，它必须保存上下文的引用，以便它可以调用 *setState()* 方法来更改上下文的当前状态。自动售货机是最受欢迎的例子之一。

到目前为止，我们注意到《国家》和《战略》在结构上相似，但意图不同。因此，下面是 Java 中状态和策略设计模式之间的主要区别，它们在类中都很相似，都执行开放封闭设计原则并封装行为。使用策略设计模式，封装在运行时提供给上下文的算法或策略，可以作为参数或组合对象，并使用状态模式来管理 Java 中的状态转换。

<figure class="table">

| 状态模式 | 策略模式 |
| --- | --- |
| 在状态模式中，一个单独的状态可以包含上下文的引用，以实现状态转换。 | 但是《战略》并没有提到使用它们的语境。 |
| 状态封装对象的状态。 | 而策略模式封装了算法或策略。 |
| 状态模式帮助一个类在不同的状态下表现出不同的行为。 | Strategy Pattern 封装了一组相关的算法，允许客户端在运行时通过组合和委托来使用可互换的行为。 |
| 状态是上下文对象本身的一部分，随着时间的推移，上下文对象从一种状态过渡到另一种状态。 | 它可以作为参数传递给使用它们的对象，例如 *Collections.sort()* 接受比较器，这是一种策略。 |
| 状态模式定义了对象的“什么”和“什么时候”部分。例子:物体处于某种状态时会发生什么。 | 策略模式定义了对象的“如何”部分。示例:排序对象如何对数据进行排序。 |
| 状态转换的顺序在状态模式中定义明确。 | 战略模式没有这样的要求。客户可以自由选择他选择的任何战略实施。 |
| 状态的改变可以通过上下文或者状态对象本身来完成。 | 战略变更由客户完成。 |
| 策略模式的一些常见示例是封装算法，例如排序算法、加密算法或压缩算法。 | 另一方面，识别 State 设计模式的使用相当容易。 |
| 如果看到，你的代码需要使用不同种类的相关算法，那么就想到使用一个 Strategy 模式。 | 如果需要管理状态和状态转换，没有大量嵌套的条件语句，状态模式就是要使用的模式。 |

</figure>