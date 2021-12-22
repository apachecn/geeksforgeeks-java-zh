# JSF | Java 服务器面临

> 原文:[https://www.geeksforgeeks.org/jsf-java-server-faces/](https://www.geeksforgeeks.org/jsf-java-server-faces/)

JSF 技术包括一组应用编程接口，它们代表不同的用户界面组件，并帮助管理它们的状态。这些应用编程接口进一步帮助处理用户界面组件上的事件，并通过用户界面组件验证用户输入。JSF 框架提供了创建简单和复杂应用程序的灵活性，因为该技术使用最流行的 Java 服务器技术(Servlet 和 Java 服务器页面)，并且不将开发人员限制在特定的标记语言或客户端设备上。与 JSF 应用编程接口捆绑的用户界面组件类包含各种组件功能的逻辑实现，并且没有任何特定于客户端的呈现逻辑。因此，JSF 用户界面组件可以为不同的客户端设备呈现。目前，SF 提供了一个自定义渲染器和 Java 服务器页面(JSP)自定义标记，用于为 HTML 客户端渲染 UI 组件。

JSF 是一个健壮的 Web 应用程序框架，它实现了一个事件编程模型来处理客户端在不同 UI 组件上执行的不同事件和操作。为了处理每个事件，应该在服务器端注册一个侦听器。开发 Web 应用程序时，开发人员必须在源代码中编写导航规则，以便从一个网页导航到另一个网页。JSF 提供了一种简单的方法来定义配置文件中的导航规则，并向客户端显示不同的错误消息，显示错误的真正原因。这些消息是在根据某些验证规则验证用户输入时生成的，可以显示在包含用户界面组件的同一页面上。

有不同的 Web 应用程序框架来实现一种或多种 MVC 设计模式。JSF 是基于 MVC2 模式的，这个模式是基于组件类型开发的。在这种模式中，开发人员只需专注于他们各自的组件，引入独立的层，如模型视图和控制器，并通过使网络应用程序易于维护来帮助开发人员专注于单一类型的组件。组件的不同类别(如模型视图和控制器)是为不同的功能(如使用文本字段、对话框简单标签和颜色选择器)创建的，可以单独使用

#### 解读 JSF 的特色

Java 技术提供了各种框架来开发网络应用程序。其中一些框架，如 Struts，比 JSF 更受欢迎，但 JSF 丰富而简单的特性使其成为设计和管理网络应用程序中用户界面组件的首选之一。

以下是 JSF 的各种特性:

*   Provides an easy-to-use environment, which is the Integrated Development Environment (IDE), for developing Web applications using JSF UI components. It has extensive tool support from companies such as Sun, IBM and Oracle.
*   Through its own set of tags, it is convenient to create complex user interface module in web pages. These tags are provided as JSP custom tag library. For JSF, it is easy to design a user interface module because it is based on MVC design pattern, which clearly separates presentation from business logic.
*   Provides methods for managing all UI components in a web page. Management of user interface module includes verifying user input, component status, page navigation and event handling.
*   Provides an extensible architecture, which means that you can add other functions on top of JSF, and you can easily customize and reuse JSF UI components.
*   Support multiple client devices. There are different renderers to render or display similar user interface module for different client devices. Various component classes can be extended to create custom component tag libraries to support specific types of clients.
*   Contains components that support internationalization, and supports displaying localized messages according to the specified locale.
*   Support standard Rapid Application Development (RAD) Java Web application framework, through a set of reusable components
*   Powerful applications can be developed quickly, which provides a method for developers to link visual components to controller or model components without destroying layers.
*   Provides an expression language (EL) for JSF pages. Because JSF pages use JSP tags, it is difficult to embed individual ELs into a JSF page. One of the key concerns of the Java specification is to maintain the consistency of its different Web layer technologies, such as ISP, JSF and JSP standard tag library (JSTL). This agreement led to the creation of unified EL, which integrated JSP 2.0 EL and JSF 1.1 EL. JSP 2.1 and JSF 1.2 support this unified EL. In other words, you can use JSTL tags for JSF components.
*   Help build Web 20 applications using asynchronous JavaScript and XML technology (AJAX), and further reduce the complexity involved in creating UI components.
*   Use the element in the faces-config.xml file to configure the application-wide resource bundle as EL.