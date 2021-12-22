# Javabeans 与企业 JavaBean s 的区别

> 原文:[https://www . geesforgeks . org/javabeans 与企业 JavaBean s 的区别/](https://www.geeksforgeeks.org/difference-between-javabeans-and-enterprise-javabeans/)

**JavaBeans:** JavaBeans 是 Java 的可回收软件组件，通过使用构建器工具，可以按照特定的约定进行可视化操作。JavaBeans 创建可以组合成小程序和应用程序的 Java 组件。为了作为单个 bean 对象传递，而不是作为多个相应的对象传递，它们用于将许多对象封装到单个对象(bean)中。

**企业 JavaBean s(EJB)**:EJB 是一般实现中间层业务性能的服务器端程序。企业 JavaBeans 旨在三向模型中处理诸如持久性、事务完整性和安全性等常见问题，这让程序员可以自由地专注于手头的特定问题。它通过 EJB 到 COBRA 的映射与 COBRA、COBRA-HOP 的兼容性紧密结合。

JavaBeans 和企业 JavaBean s(EJB)的区别如下:

| s No. | JavaBeans | Enterprise JavaBeans |
| --- | --- | --- |
| 1\. | Javabeans is a component technology to create general Java components. | Even though EJB is a component technology, it neither refactors nor enhances the original JavaBean specification. |
| 2。 | Beaninfo class, attribute editor or customizer can appear in Javabeans. | There is no awareness of Beaninfo class, attribute editor or customizer in enterprise JavaBeans, and no other information is provided except the information described in the deployment descriptor. |
| 3。 | JavaBean s gives an external interface named properties interface, which allows the builder tool to describe the functions of bean. | A deployment descriptor is given in enterprise JavaBeans, which is used to explain functions to external builder tools or IDE. |
| 4。 | There is no further classification of Java Beans. | Enterprise JavaBeans are divided into two types-session beans and entity beans. |
| 5。 | JavaBeans does not have any explicit support for transactions. | EJB may be transactional, and transactional support is provided by EJB server. |
| 6。 | JavaBeans is designed for a single process and localized | EJB is a component or business object that can be executed remotely. |
| 7。 | JavaBeans can be visible or invisible components. Visual user interface module (buttons, list boxes, graphics) is an example of JavaBeans. | EJB is a non-visual isolated object. |
| 8。 | JavaBeans has component bridges. A JavaBeans can also be arranged as an ActiveX control. | ActiveX controls are designed for desktop, so EJB cannot be deployed as ActiveX controls. |
| 9。 | JavaBeans is mainly designed to run on the client side, while JavaBeans on the server side can be developed. | EJB is only deployed on the server side. |