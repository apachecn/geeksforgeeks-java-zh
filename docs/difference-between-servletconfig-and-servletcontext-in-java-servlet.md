# Java Servlet 中 ServletConfig 和 ServletContext 的区别

> 原文:[https://www . geeksforgeeks . org/servlet config-and-servlet context-in-Java-servlet/](https://www.geeksforgeeks.org/difference-between-servletconfig-and-servletcontext-in-java-servlet/)之间的区别

**ServletConfig** 和 **ServletContext** ，都是在 [servlet](https://www.geeksforgeeks.org/introduction-java-servlets/) 初始化时创建的对象，用于向 servlet 提供一些初始参数或配置信息。但是，区别在于，ServletConfig 共享的信息是针对特定的 servlet 的，而 ServletContext 共享的信息对 web 应用程序中的所有 servlet 都是可用的。

<u>**ServletConfig:**</u>

*   servletConfig 是一个包含一些初始参数或配置信息的对象，由 Servlet 容器创建，并在初始化过程中传递给 Servlet。
*   ServletConfig 是针对特定的 servlet 的，这意味着应该在 web.xml 中存储 servlet 特定的信息，并使用这个对象来检索它们。
*   **示例:**
    假设，一个人正在构建一个工作门户，并希望与招聘人员和求职者共享不同的电子邮件 id(可能会随着时间的推移而改变)。
    于是，他决定编写两个 servlets，一个用于处理招聘人员的请求，另一个用于求职者。
    **在哪里存储电子邮件 id？**
    将 email-id 作为不同 servlet 的名称-值对放入 web.xml 中，可以使用 getServletConfig()进一步检索。servlet 中的 getInitParameter(“名称”)。

<u>**【servletcontext:**</u>

*   ServletContext 是 Servlet 容器创建的对象，用于向整个应用程序共享初始参数或配置信息。
*   **举例:**
    假设，一个人的工作门户的名字是“NewWebsite.tg”。在不同 servlet 提供的网页顶部显示网站名称，需要将网站名称存储在每个 servlet 中，以避免冗余。由于 ServletContext 共享的信息可以被每个 Servlet 访问，所以最好使用 ServletContext，并在需要时使用 getservlet context . getinitparameter(“名称”)检索网站名称。

<u>**servlet config 和 ServletContext 示例的实现如下所示。**T3】</u>

## web.xml

```java
<web-app>

<servlet>
    <servlet-name>recruiter</servlet-name>
    <servlet-class>Recruiter</servlet-class>
    <init-param>
      <param-name>Email</param-name>
      <param-value>forRecruiter@xyz.com</param-value>
    </init-param>
  </servlet>

  <servlet-mapping>
    <servlet-name>recruiter</servlet-name>
    <url-pattern>/servlet1</url-pattern>
  </servlet-mapping>

  <servlet>
    <servlet-name>applicant</servlet-name>
    <servlet-class>Applicant</servlet-class>
    <init-param>
      <param-name>Email</param-name>
      <param-value>forApplicant@xyz.com</param-value>
    </init-param>
  </servlet>

  <servlet-mapping>
    <servlet-name>applicant</servlet-name>
    <url-pattern>/servlet2</url-pattern>
  </servlet-mapping>

  <context-param>
    <param-name>Website-name</param-name>
    <param-value>NewWebsite.tg</param-value>
  </context-param>

</web-app>
```

## 招聘人员的 Servlet

```java
import java.io.*;
import javax.servlet.*;
import javax.servlet.http.*;

public class Recruiter extends HttpServlet {

    protected void doGet(HttpServletRequest request,
                         HttpServletResponse response)
        throws ServletException, IOException
    {
        String email
            = getServletConfig()
                  .getInitParameter("Email");
        String website
            = getServletContext()
                  .getInitParameter("Website-name");
        PrintWriter out = response.getWriter();
        out.println("<center><h1>" + website
                    + "</h1></center><br><p>Contact us:"
                    + email);
    }
}
```

## 申请人的 Servlet

```java
import java.io.*;
import javax.servlet.ServletException;
import javax.servlet.http.*;

public class Applicant extends HttpServlet {

    protected void doGet(HttpServletRequest request,
                         HttpServletResponse response)
        throws ServletException, IOException
    {

        String email
            = getServletConfig()
                  .getInitParameter("Email");
        String website
            = getServletContext()
                  .getInitParameter("Website-name");
        PrintWriter out = response.getWriter();
        out.println("<center><h1>" + website
                    + "</h1></center><br><p>Contact us:"
                    + email);
    }
}
```

*   **输出**:部署应用并在 localhost 上打开网址:
    1.  **/servlet 1**:
        [![](img/c0d52fda3d2d0b7b81b42d511501c993.png)](https://media.geeksforgeeks.org/wp-content/uploads/20190724210033/recruiter.jpg)
    2.  **/servlet2**:

        [![](img/346b1597334f86e5c46b7673e98e893a.png)](https://media.geeksforgeeks.org/wp-content/uploads/20190724210108/applicant.jpg)

*   如上图所示，不同的 servlet 由于在 web.xml.
    中附加了不同的值而获得了具有相同参数名“email”的不同的 email-id。每个 servlet 在包含 email-id 的< servlet >中都有自己的< init-param >。
*   两个 servlets 都获得了 ServletContext 参数“网站名称”的访问权限。因为在 web.xml 中，<context-param>在<servlet>之外，所以它独立于 servlet，可以从整个应用程序中访问。</servlet></context-param>

<u>**下面是两者的对照表:**</u>

| ServletConfig | ServletContext |
| --- | --- |
| ServletConfig 是特定于 servlet 的 | ServletContext 用于整个应用程序 |
| servletConfig 的参数以名称-值对的形式出现在<servlet>内的<init-param>中。</init-param></servlet> | servletContext 的参数在<servlet>外部和<web-app>内部的<context-param>中以名称-值对的形式出现</context-param></web-app></servlet> |
| ServletConfig 对象是通过 getServletConfig()方法获得的。 | ServletContext 对象是通过 getServletContext()方法获取的。 |
| 每个 servlet 都有自己的 ServletConfig 对象。 | ServletContext 对象只有一个，由应用程序的不同 servlets 使用。 |
| 当只有一个 servlet 需要共享信息时，使用 ServletConfig。 | 当整个应用程序需要共享信息时，使用 ServletContext |