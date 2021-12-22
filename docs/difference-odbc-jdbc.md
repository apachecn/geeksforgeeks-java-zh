# 【ODBC 和 JDBC 的区别

> 原文:[https://www.geeksforgeeks.org/difference-odbc-jdbc/](https://www.geeksforgeeks.org/difference-odbc-jdbc/)

| 开放式数据库连接性 | JDBC |
| ODBC stands for open database connection. | JDBC stands for java database connection. |
| Launched by Microsoft in 1992. | Launched by SUN Microsystems in 1997. |
| We can use ODBC in any language, such as C, C++, Java, etc. | We can only use JDBC for Java language. |
| We can only choose the windows platform of ODBC. | We can use JDBC on any platform. |
| Most of them are ODBC drivers developed in native languages such as C and C++. | JDBC stands for java database connection. |
| For Java applications, ODBC is not recommended, because internal conversion will lead to performance degradation and applications will become platform-dependent. | For Java applications, JDBC is strongly recommended, because we have no performance-platform related problems. |
| ODBC is programmed. | JDBC is object oriented. |