# JMS 中 PointToPoint 和发布/订阅模型的区别

> 原文:[https://www . geesforgeks . org/pointtopoint-and-publish-subscribe-model-in-JMS/](https://www.geeksforgeeks.org/differences-between-pointtopoint-and-publish-subscribe-model-in-jms/)之间的差异

**点对点消息模型**和**发布订阅消息模型**是 **[Java 消息服务(JMS)](https://www.geeksforgeeks.org/introduction-to-spring-framework/)** 支持的两类消息模块/类型/域。

这两个是支持异构系统之间异步消息传递的编程模型。

有一些重要的术语，将有助于我们更好地理解这两种消息模型类型之间的区别:

*   **JMS destination** is a transit area, which serves as the source of messages used by clients and the destination/destination of generated messages.
*   **JMS producer** is a JMS client that sends messages.
*   **JMS consumer** is a JMS client that receives messages.
*   A **JMS client** can be both a message producer and a message consumer.
*   **Time Dependence** Simply put, if the producer publishes the news of a certain topic and the consumer does not subscribe, then the consumer will not receive the news of the topic.

我们来看看这两种消息模型类型的区别:

| [T0】 PointToPoint Messaging-Model (P2P) | **Publish/subscribe model (pub sub)** |
| --- | --- |
| The JMS Destination here is the queue. | And JMS destinations in pubs are a topic. |
| The JMS producer here is the sender. | The JMS producer in Pub sub is a publisher. |
| The JMS consumer here is the receiver. | And JMS consumers in Pub sub are subscribers. |
| The message here is only received by one JMS consumer. | In Pub sub, a message can be received by multiple JMS consumers. |
| Here, the JMS consumer sends a confirmation to the producer when receiving the message. | In Pub sub, JMS consumers will not send any confirmation when they receive messages. |
| There is a time dependence of the receiver receiving the message. | In Pub sub, there is no time dependence between producers and consumers. |
| This model is pull-type, that is, the receiver is responsible for requesting the sender to send new messages. | Although this mode is based on push, it means that messages are automatically delivered to consumers, and they don't have to request new messages. |
| is ex. Send fax/voice messages. | is ex. Newspapers. |