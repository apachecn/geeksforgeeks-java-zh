# Java 中的 CompoundName add()方法，示例

> 原文:[https://www . geesforgeks . org/compound name-add-method-in-Java-with-examples/](https://www.geeksforgeeks.org/compoundname-add-method-in-java-with-examples/)

一个 **javax.naming.CompoundName 类**的 **add()** 方法用于将组件添加到 CompoundName 对象中。
有两种不同的添加方法。

1.  **add(int, String)**: This method is used to add a single component at a specified position **posn** passed as a parameter within this compound name. The other components of this compound name object present at or after the position of the new component are shifted up by one position to accommodate the new component.

    **语法:**

    ```
    public Name add(int posn, String comp)
             throws InvalidNameException

    ```

    **参数:**该方法接受:

    *   **posn** 是添加新组件的索引，并且
    *   **comp** 是要添加到复合名称对象中的新组件。

    **返回值:**这个方法返回更新的 compoundName，而不是新的。返回值不能为空。

    **异常:**如果 posn 在指定范围之外并且 InvalidNameException 如果在指定位置添加 comp 将违反复合名称的语法，则此方法将引发**arrayindextofboundsexception**。

    下面的程序说明了 CompoundName.add()方法:
    **程序 1:**

    ```
    // Java program to demonstrate
    // CompoundName.add()

    import java.util.Properties;
    import javax.naming.CompoundName;
    import javax.naming.InvalidNameException;

    public class GFG {
        public static void main(String[] args)
            throws InvalidNameException
        {

            // need properties for CompoundName
            Properties props = new Properties();
            props.put("jndi.syntax.separator", "@");
            props.put("jndi.syntax.direction",
                      "left_to_right");

            // create compound name object
            CompoundName CompoundName1
                = new CompoundName(
                    "1@2@3@4@5@6@7",
                    props);

            // apply add() to add
            // new component at posn 0
            CompoundName newCompoundName
                = (CompoundName)
                      CompoundName1.add(0, "000");

            // print value
            System.out.println(
                "Updated CompoundName Object: "
                + newCompoundName);
        }
    }
    ```

    **Output:**

    ```
    Updated CompoundName Object: 000@1@2@3@4@5@6@7

    ```

    **程序 2:**

    ```
    // Java program to demonstrate
    // CompoundName.add() method

    import java.util.Properties;
    import javax.naming.CompoundName;
    import javax.naming.InvalidNameException;

    public class GFG {
        public static void main(String[] args)
            throws InvalidNameException
        {

            // need properties for CompoundName
            Properties props = new Properties();
            props.put("jndi.syntax.separator", "/");
            props.put("jndi.syntax.direction",
                      "left_to_right");

            // create compound name object
            CompoundName CompoundName1
                = new CompoundName(
                    "c/e/d/v/a/b/z/y/x/f",
                    props);

            // apply add() to add
            // new component at posn 9
            CompoundName newCompoundName
                = (CompoundName)
                      CompoundName1.add(
                          9, "zzzzz");

            // print value
            System.out.println(
                "Updated CompoundName Object: "
                + newCompoundName);
        }
    }
    ```

    **Output:**

    ```
    Updated CompoundName Object: c/e/d/v/a/b/z/y/x/zzzzz/f

    ```

2.  **add(String)**: Thie method is used to add a single component to the end of this compound name.
    **Syntax:**

    ```
    public Name add(String comp)
           throws InvalidNameException

    ```

    **参数:**此方法接受 **comp** ，这是要添加到复合名称对象末尾的新组件。

    **返回值:**这个方法返回更新的 compoundName，而不是新的。返回值不能为空。

    **异常:**如果在名称末尾添加 comp 会违反复合名称的语法，此方法将引发 **InvalidNameException** 。

    下面的程序说明了 CompoundName.add()方法:
    **程序 1:**

    ```
    // Java program to demonstrate
    // CompoundName.add()

    import java.util.Properties;
    import javax.naming.CompoundName;
    import javax.naming.InvalidNameException;

    public class GFG {
        public static void main(String[] args)
            throws InvalidNameException
        {

            // need properties for CompoundName
            Properties props = new Properties();
            props.put("jndi.syntax.separator", "@");
            props.put("jndi.syntax.direction",
                      "left_to_right");

            // create compound name object
            CompoundName CompoundName1
                = new CompoundName(
                    "1@2@3@4@5@6@7",
                    props);

            // apply add() to add
            // new component at end
            CompoundName newCompoundName
                = (CompoundName)
                      CompoundName1.add("9");

            // print value
            System.out.println(
                "Updated CompoundName Object: "
                + newCompoundName);
        }
    }
    ```

    **Output:**

    ```
    Updated CompoundName Object: 1@2@3@4@5@6@7@9

    ```

    **程序 2:**

    ```
    // Java program to demonstrate
    // CompoundName.add() method

    import java.util.Properties;
    import javax.naming.CompoundName;
    import javax.naming.InvalidNameException;

    public class GFG {
        public static void main(String[] args)
            throws InvalidNameException
        {

            // need properties for CompoundName
            Properties props = new Properties();
            props.put("jndi.syntax.separator", "/");
            props.put("jndi.syntax.direction",
                      "left_to_right");

            // create compound name object
            CompoundName CompoundName1
                = new CompoundName(
                    "c/e/d/v/a/b/z/y/x/f",
                    props);

            // apply add() to add
            // new component at end
            CompoundName newCompoundName
                = (CompoundName)
                      CompoundName1.add("ppp");

            // print value
            System.out.println(
                "Updated CompoundName Object: "
                + newCompoundName);
        }
    }
    ```

    **Output:**

    ```
    Updated CompoundName Object: c/e/d/v/a/b/z/y/x/f/ppp

    ```

参考文献:
[https://docs . Oracle . com/javase/10/docs/API/javax/naming/compound name . html # add(int，Java . lang . string)](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompoundName.html#add(int, java.lang.String))
[https://docs . Oracle . com/javase/10/docs/API/javax/naming/compound name . html # add(Java . lang . string)](https://docs.oracle.com/javase/10/docs/api/javax/naming/CompoundName.html#add(java.lang.String))