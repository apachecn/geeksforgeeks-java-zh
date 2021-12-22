# Java 中的方法类| getGenericParameterTypes()方法

> 原文:[https://www . geesforgeks . org/method-class-getgenericparametertypes-method-in-Java/](https://www.geeksforgeeks.org/method-class-getgenericparametertypes-method-in-java/)

方法类的 **[方法返回一个表示参数类型的类型对象数组，在编码时在方法中声明。这意味着 getGenericParameterTypes()方法返回属于方法对象的参数数组。如果方法对象没有参数，它将返回一个长度为 0 的数组。](https://www.geeksforgeeks.org/reflection-in-java/)**

如果形式参数类型是参数化类型，则为其返回的类型对象必须准确反映源代码中使用的实际类型参数。例如，对于方法 public void getValue(T value){}用参数化类型(即 List)替换类型参数 T，那么方法将返回“java.util.List”作为参数类型。

**语法:**

```
public Type[] getGenericParameterTypes()
```

**返回值:**这个方法按照声明顺序返回一个类型数组，代表方法对象的形式参数类型。

**异常:**该方法抛出以下异常:

*   **泛型签名格式错误**–如果泛型方法签名与 JVM 规范中指定的格式不同。
*   **类型不存在异常**–如果参数类型引用了不存在的类型声明。
*   **MalformedParameterizedTypeException** – if the underlying parameter types refers to a parameterized type that cannot be instantiated for any reason.

    下面的程序说明了方法类的 getGenericParameterTypes()方法:

    **程序 1:** 打印为方法声明的所有参数类型

    ```
    // Program Demonstrate how to apply getGenericParameterTypes() method
    // of Method Class.

    import java.lang.reflect.Method;
    import java.lang.reflect.Type;

    public class GFG {

        // Main method
        public static void main(String[] args)
        {
            try {
                // create class object
                Class classobj = demoClass.class;

                // get Method Object
                Method[] methods = classobj.getMethods();

                // iterate through methods
                for (Method method : methods) {

                    // only taking method defined in the demo class
                    if (method.getName().equals("setValue")
                        || method.getName().equals("getValue")
                        || method.getName().equals("setManyValues")) {

                        // apply getGenericParameterTypes() method
                        Type[] parameters = method.getGenericParameterTypes();

                        // print parameter Types of method Object
                        System.out.println("\nMethod Name : "
                                           + method.getName());
                        System.out.println("No of Parameters : "
                                           + parameters.length);
                        System.out.println("Parameter object details:");
                        for (Type type : parameters) {

                            System.out.println(type.getTypeName());
                        }
                    }
                }
            }
            catch (Exception e) {
                e.printStackTrace();
            }
        }
    }
    // a simple class
    class demoClass {

        // method containing two parameter
        public void setValue(String value1, String value2)
        {
            System.out.println("setValue");
        }

        // method containing no parameter
        public String getValue()
        {
            System.out.println("getValue");
            return "getValue";
        }

        // method containg many parameter
        public void setManyValues(int value1,
                                  double value2,
                                  String value3)
        {
            System.out.println("setManyValues");
        }
    }
    ```

    **Output:**

    ```
    Method Name : setManyValues
    No of Parameters : 3
    Parameter object details:
    int
    double
    java.lang.String

    Method Name : getValue
    No of Parameters : 0
    Parameter object details:

    Method Name : setValue
    No of Parameters : 2
    Parameter object details:
    java.lang.String
    java.lang.String

    ```

    **程序 2:** 检查方法对象是否包含参数

    ```
    // Program Demonstrate how to apply getGenericParameterTypes()
    // method of Method Class.
    import java.lang.reflect.Method;
    import java.lang.reflect.Type;

    public class GFG {

        // Main method
        public static void main(String[] args)
        {
            try {
                // create class object
                Class classobj = sample.class;

                Method[] methods = classobj.getMethods();

                /*check whether setManyValues() method contains 
                             int parameter or not
                    and print no of string parameter it contains*/

                for (Method method : methods) {
                    if (method.getName().equals("setValue")) {

                        int count = containsParameter(
                            method,
                            (Type)java.lang.String.class);
                        System.out.println("No of String"
                                           + " Parameters in setValue(): "
                                           + count);
                    }
                }

                // check whether setManyValues() method
                // contains int parameter or not
                // and print no of string parameter it contains

                for (Method method : methods) {

                    if (method.getName().equals("setManyValues")) {

                        int count = containsParameter(method,
                                                      (Type) int.class);

                        System.out.println("No of int Parameters"
                                           + " in setManyValues(): "
                                           + count);
                    }
                }
            }
            catch (Exception e) {
                e.printStackTrace();
            }
        }

        // count no of parameters contain by
        // method same as passed to method
        private static int
        containsParameter(Method method,
                          Type parameterName)
        {
            int count = 0;

            // get all parameter types list
            // using getGenericParameterTypes()
            Type parameters[] = method.getGenericParameterTypes();

            for (int i = 0; i < parameters.length; i++) {
                // check contains parameter or not
                if (parameters[i] == parameterName) {
                    count++;
                }
            }

            return count;
        }
    }
    // a simple class
    class sample {

        // method containing two parameter
        public void setValue(String value1,
                             String value2)
        {
            System.out.println("setValue");
        }

        // method containing many parameter
        public void setManyValues(int value1,
                                  double value2,
                                  String value3)
        {
            System.out.println("setManyValues");
        }
    }
    ```

    **Output:**

    ```
    No of String Parameters in setValue(): 2
    No of int Parameters in setManyValues(): 1

    ```

    **参考:**[https://docs . Oracle . com/javase/8/docs/API/Java/lang/reflect/method . html # getGenericParameterTypes–](https://docs.oracle.com/javase/8/docs/api/java/lang/reflect/Method.html#getGenericParameterTypes--)