# 如何在安卓中制作勾选/勾选和交叉动画

> 原文:[https://www . geeksforgeeks . org/如何在安卓中制作勾选勾选交叉动画/](https://www.geeksforgeeks.org/how-to-make-check-tick-and-cross-animations-in-android/)

**animated vectordrawinable**类在 **API 21** 中引入，用于将**Vector drawinable**制作成漂亮且轻松的动画。使用 AnimatedVectorDrawable，可以:

*   旋转、缩放、平移矢量图形
*   将矢量绘制成动画，如填充颜色等。
*   绘制路径并进行路径变形

一个**动画矢量可绘制元素**有一个**矢量可绘制属性**，以及一个或多个目标元素。目标元素可以通过**安卓:名称**属性指定其目标，并通过**安卓:动画**属性将目标与适当的对象动画器或动画器集链接。

<u>**绘制勾十字动画的方法:**</u>

1.  在**值目录**中创建新的 **tick_cross.xml 文件**，并添加以下矢量可绘制路径数据和路径命令:

    ## tick _ cross . XML

```
<?xml version="1.0" encoding="UTF-8"?>
<resources>

   <!-- geometry -->
   <integer name="viewport_width">24</integer>
   <integer name="viewport_height">24</integer>
   <integer name="viewport_center_x">12</integer>
   <integer name="viewport_center_y">12</integer>
   <string name="path_tick">M4.8, 13.4 L9, 
                            17.6 M10.4, 
                            16.2 L19.6, 7
   </string>
   <string name="path_cross">M6.4, 6.4 L17.6, 
                            17.6 M6.4, 
                            17.6 L17.6, 6.4
   </string>
   <integer name="stroke_width">2</integer>

   <!-- names -->
   <string name="tick">tick</string>
   <string name="cross">cross</string>
   <string name="groupTickCross">groupTickCross</string>

   <!-- drawing -->
   <color name="stroke_color">#999</color>
</resources>
```