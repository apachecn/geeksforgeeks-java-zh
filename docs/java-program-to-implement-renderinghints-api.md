# 实现渲染提示 API 的 Java 程序

> 原文:[https://www . geesforgeks . org/Java-程序到实现-呈现提示-api/](https://www.geeksforgeeks.org/java-program-to-implement-renderinghints-api/)

Graphics2D 类使用的图形属性是 **java.awt.RenderingHints** 。这个类是从一组呈现提示名称到一组呈现提示值的映射(java.util.Map)。与其他属性不同，Graphics2D 定义了多个方法来设置渲染提示属性。

*   **setRenderingHints()** 指定一组新的提示来替换旧的提示。
*   **addRenderingHints()** 向现有集合添加一组提示。
*   **setRenderingHint()** 设置当前提示集中单个提示的值。

渲染提示是对 Java 2D 如何执行渲染的建议。

**渲染提示类**定义了许多名称以 KEY_ 开头的常量。这些常量代表了你能给出的暗示。该类还定义了许多名称以 VALUE_ 开头的常数。这些是各种提示的法律价值。值常量的名称清楚地表明了每个值与哪个提示键常量相关联。提示的目的是允许您请求 Java 2D 打开或关闭特定功能，例如抗锯齿。此外，这些提示允许您建议 Java 2D 应该在速度和质量之间做出什么样的权衡。请记住，这些是对 Java 2D 的提示和建议，而不是命令。并非所有的 Java 2D 实现都支持所有的提示，不同的实现有不同的提示默认值。此外，提示的含义没有精确定义，因此不同的实现可能会以不同的方式解释提示。

RenderingHints 类定义并管理键和相关值的集合，这些键和相关值允许应用程序为执行渲染和图像操作服务的其他类所使用的算法的选择提供输入。

**实施:**

## Java 语言(一种计算机语言，尤用于创建网站)

```java
// Java Program to show the demonstration to 
// Implement RenderingHints API

import java.awt.RenderingHints;
import java.util.Collection;
import java.util.HashMap;
import java.util.Iterator;
import java.util.Map;
import java.util.Map.Entry;
import java.util.Set;

public class RenderingHintsImpl
{
    private RenderingHints renderingHints;

    // Constructs a new object with keys and values
    // initialized from the
    // specified Map object which may be null.

    public RenderingHintsImpl(Map<RenderingHints.Key, ?> init)
    {
        renderingHints = new RenderingHints(init);
    }

     // Constructs a new object with the specified key/value
     // pair. 
    public RenderingHintsImpl(RenderingHints.Key key,
                              Object value)
    {
        renderingHints = new RenderingHints(key, value);
    }

     // Adds all of the keys and corresponding values from
     // the specified
     // RenderingHints object to this RenderingHints object.
    public void add(RenderingHints hints)
    {
        renderingHints.add(hints);
    }

     // Clears this RenderingHints object of all key/value
     // pairs. 
    public void clear() { renderingHints.clear(); }

     // Creates a clone of this RenderingHints object that
     // has the same contents
     // as this RenderingHints object.

    public Object clone() { return renderingHints.clone(); }

     // Returns true if this RenderingHints contains a
     // mapping for the specified key. 

    public boolean containsKey(Object key)
    {
        return renderingHints.containsKey(key);
    }

     // Returns true if this RenderingHints maps one or more
     // keys to the specified value. 
    public boolean containsValue(Object value)
    {
        return renderingHints.containsValue(value);
    }

     // Returns a Set view of the mappings contained in this
     // RenderingHints
    public Set<Map.Entry<Object, Object> > entrySet()
    {
        return renderingHints.entrySet();
    }

     // Returns the value to which the specified key is
     // mapped. 
    public Object get(Object key)
    {
        return renderingHints.get(key);
    }

     // Returns true if this RenderingHints contains no
     // key-value mappings. 
    public boolean isEmpty()
    {
        return renderingHints.isEmpty();
    }

     // Returns a Set view of the Keys contained in this
     // RenderingHints. 
    public Set<Object> keySet()
    {
       return renderingHints.keySet();
    }

     // Maps the specified key to the specified value in
     // this RenderingHints object. 
    public Object put(Object key, Object value)
    {
        return renderingHints.put(key, value);
    }

     // Copies all of the mappings from the specified Map to
     // this RenderingHints. 
    public void putAll(Map<?, ?> m)
    {
        renderingHints.putAll(m);
    }

     // Removes the key and its corresponding value from
     // this RenderingHints object. 
    public Object remove(Object key)
    {
        return renderingHints.remove(key);
    }

     // Returns the number of key-value mappings in this
     // RenderingHints. 
    public int size() { return renderingHints.size(); }

     // Returns a Collection view of the values contained in
     // this RenderinHints. 
    public Collection<Object> values()
    {
        return renderingHints.values();
    }

    public static void main(String[] arg)
    {

        RenderingHintsImpl renderingHints  = new RenderingHintsImpl(
                RenderingHints.KEY_ALPHA_INTERPOLATION,

        RenderingHints.VALUE_ALPHA_INTERPOLATION_QUALITY);

        renderingHints.put(
            RenderingHints.KEY_TEXT_ANTIALIASING,
            RenderingHints.VALUE_TEXT_ANTIALIAS_ON);

        renderingHints.put(
            RenderingHints.KEY_FRACTIONALMETRICS,
            RenderingHints.VALUE_FRACTIONALMETRICS_ON);

        renderingHints.put(
            RenderingHints.KEY_COLOR_RENDERING,
            RenderingHints.VALUE_COLOR_RENDER_QUALITY);

        Map<Object, Object> anotherMap = new HashMap<Object, Object>();

        anotherMap.put(RenderingHints.KEY_STROKE_CONTROL,
                       RenderingHints.VALUE_STROKE_PURE);

        anotherMap.put(RenderingHints.KEY_DITHERING,
                       RenderingHints.VALUE_DITHER_ENABLE);

        renderingHints.putAll(anotherMap);

        System.out.println("the key set of the renderingHints is - ");

        Set<Object> keySet = renderingHints.keySet();

        Iterator<Object> itr = keySet.iterator();

        while (itr.hasNext())
        {
            System.out.println(itr.next());
        }

        System.out.println();

        System.out.println("the values of the renderingHints is -");

        Collection<Object> collectionValues = renderingHints.values();

        itr = collectionValues.iterator();

        while (itr.hasNext())
        {
            System.out.println(itr.next());
        }

        System.out.println();

        System.out.println("the entry set of the renderingHints is -");

        Iterator<Entry<Object, Object> > eitr;

        Set<Entry<Object, Object> > entrySet = renderingHints.entrySet();

        eitr = entrySet.iterator();

        while (eitr.hasNext())
        {
            System.out.println(eitr.next());
        }

        System.out.println(
            "the renderingHints contains Key  KEY_TEXT_ANTIALIASING :"
            + renderingHints.containsKey(RenderingHints.KEY_TEXT_ANTIALIASING));

        System.out.println(
            "the renderingHints contains Value VALUE_TEXT_ANTIALIAS_ON :"
            + renderingHints.containsValue(
                RenderingHints.VALUE_TEXT_ANTIALIAS_ON));

        System.out.println("the size of the renderingHints is :"
            + renderingHints.size());

        renderingHints.clear();

        if (renderingHints.isEmpty())

           System.out.println("The renderingHints is empty");

        else

           System.out.println("The renderingHints is not empty");
    }
}
```

**Output**

```java
the key set of the renderingHints is - 
Alpha blending interpolation method key
Fractional metrics enable key
Stroke normalization control key
Color rendering quality key
Dithering quality key
Text-specific antialiasing enable key

the values of the renderingHints is -
Highest quality alpha blending methods
Fractional text metrics mode
Pure stroke conversion for accurate paths
Highest quality color rendering mode
Dithered rendering mode
Antialiased text mode

the entry set of the renderingHints is -
Alpha blending interpolation method key=Highest quality alpha blending methods
Fractional metrics enable key=Fractional text metrics mode
Stroke normalization control key=Pure stroke conversion for accurate paths
Color rendering quality key=Highest quality color rendering mode
Dithering quality key=Dithered rendering mode
Text-specific antialiasing enable key=Antialiased text mode
the renderingHints contains Key  KEY_TEXT_ANTIALIASING :true
the renderingHints contains Value VALUE_TEXT_ANTIALIAS_ON :true
the size of the renderingHints is :6
The renderingHints is empty

```