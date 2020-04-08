=========================
可编程Lcd模块
=========================

SmartWatch具有可编程Lcd，可实现画点、线、矩形、圆等基本图像。


Colors
=========================
在Lcd编程中会使用颜色，可以使用24位整型数值，每种颜色8位。例如，0xFF0000就是红色，0xFF00就是绿色。

定义了一些颜色常量供快捷选择使用：

====================  ===============  ==============
   常量                  颜色              数值
====================  ===============  ==============
TFT_BLACK               黑色              0
TFT_NAVY                海蓝色            128
TFT_BLUE                蓝色              255
TFT_DARKGREEN           深绿色            32768
TFT_DARKCYAN            深青色            32896
TFT_GREEN               绿色              62580
TFT_CYAN                青色              65535
TFT_MAROON              栗色              8388608
TFT_PURPLE              紫色              8388736
TFT_OLIVE               橄榄绿            8421376
TFT_DARKGREY            深灰色            8421504
TFT_GREENYELLOW         黄绿色            11336748
TFT_LIGHTGREY           亮灰色            12632256
TFT_RED                 红色              16515072
TFT_MAGENTA             洋红色            16515327
TFT_ORANGE              橙色              16557056
TFT_PINK                粉红色             16564426
TFT_YELLOW              黄色              16579584
TFT_WHITE               白色              16579836
====================  ===============  ==============

Fonts
===========================

字体常量: 
**TFT_DEFAULT_FONT**, **TFT_DEJAVU18_FONT**, **TFT_DEJAVU24_FONT**, **TFT_UBUNTU16_FONT**, **TFT_COMIC24_FONT**,
**TFT_MINYA24_FONT**, **TFT_TOONEY32_FONT**, **TFT_SMALL_FONT**, **TFT_DEF_SMALL_FONT**, **TFT_FONT_7SEG**

Lcd Methods
============================

画像素点
++++++++++++++++++++++++++++
**pwatch.Lcd.pixel(x, y [,color])**

设置坐标点(x, y)的像素颜色，
颜色参数color为颜色值，选填参数。

画直线段
++++++++++++++++++++++++++++
**pwatch.Lcd.line(x, y, x1, y1 [, color])**

画坐标点(x, y)到坐标点(x1, y1)的直线，
颜色参数color为线条颜色值，选填参数。

画三角形
++++++++++++++++++++++++++++
**pwatch.Lcd.triangle(x, y, x1, y1, x2, y2 [,color,fillcolor])**

画坐标(x, y), (x1, y1)和 (x2, y2)三点相连的三角形，
颜色参数color和fillcolor选填，分别为三角形颜色和填充颜色。

画矩形
++++++++++++++++++++++++++++
**pwatch.Lcd.rect(x, y, width, height [,color, fillcolor])**

以坐标(x, y)为左上角顶点，width作为宽，height作为高，画矩形，
颜色参数color和fillcolor选填，分别为矩形颜色和填充颜色。

画圆形
++++++++++++++++++++++++++++
**pwatch.Lcd.circle(x, y, r [, color, fillcolor])**

以坐标(x, y)为圆心，r为圆半径画圆，
颜色参数color和fillcolor选填，分别为圆形的颜色和填充颜色。

画椭圆形
++++++++++++++++++++++++++++
**pwatch.Lcd.ellipse(x, y, rx, ry [,color, fillcolor])**

以坐标(x, y)为圆心，x方向半径为rx，y方向半径为ry画椭圆，
颜色参数color和fillcolor选填，分别为椭圆颜色和填充颜色。

画多边形
++++++++++++++++++++++++++++
**pwatch.Lcd.polygon(x,y,r,steps,[,color,fillcolor])**

以坐标（x,y）为中心，r为半径，steps为多边形边数画多边形
颜色参数color和fillcolor选填，分别为多边形边框颜色和填充颜色。


显示图片
++++++++++++++++++++++++++++
**pwatch.Lcd.image(x, y, file[, scale])**

以坐标（x,y）作为图片左上角显示图片。
参数file为待显示图片的文件路径，参数scale为图像的缩放比例，默认为0

显示预置图片
++++++++++++++++++++++++++++
**showImageRes(x,y,name[,scale,color])**

以坐标（x,y）作为图片左上角显示图片。
参数name为内置资源名称，参数scale为缩放比例，默认为1，color为图像颜色

====================  ===============  
   图像名称                  描述              
====================  ===============  
downarrow               下箭头              
exclamation             感叹号            
leftarrow               左箭头              
love                    爱心            
rightarrow              右箭头           
sad                     伤心            
smile                   笑脸            
star                    五角星     
uparrow                 上箭头              
wth_cloudy              阴天            
wth_haze                雾霾            
wth_mcloud              多云            
wth_rain                下雨            
snow                    下雪              
sun                     晴                        
====================  ===============

示例1：

.. code-block:: python
    :linenos:

    import machine, utime
    from smartWatch import *

    pwatch.Lcd.showImageRes(0,0,'love')#爱心

显示文本
++++++++++++++++++++++++++++
**pwatch.Lcd.text(x, y, text [, color])**

显示屏输入文本显示，以(x, y)坐标为文本起点，text为文本内容，
颜色参数color选填，为文本颜色。

设置字体
++++++++++++++++++++++++++++
**pwatch.Lcd.font(font)**

设置显示屏文本字体，参数font选用Fonts字体常量。

设置背景色
++++++++++++++++++++++++++++
**pwatch.Lcd.setbg(color)**

设置显示屏背景颜色。

清屏
++++++++++++++++++++++++++++
**pwatch.Lcd.clear()**

清空显示屏显示内容

设置屏幕方向
++++++++++++++++++++++++++++
**pwatch.Lcd.setRotation(value)**

设置屏幕显示方向，使用默认常量设置。方向常量：**TFT_PORTRAIT** ，**TFT_LANDSCAPE**， **TFT_PORTRAIT_FLIP**，**TFT_LANDSCAPE_FLIP** 。 




示例2：

.. code-block:: python
    :linenos:

    import machine, utime
    from smartWatch import *



    def rotateScreen():
        if pwatch.accX > 9.0:
            pwatch.Lcd.setRotation(TFT_LANDSCAPE)
        elif pwatch.accX < -9.0:
            pwatch.Lcd.setRotation(TFT_LANDSCAPE_FLIP)
        elif pwatch.accY > 9.0:
            pwatch.Lcd.setRotation(TFT_PORTRAIT_FLIP)
        elif pwatch.accY < -9.0:
            pwatch.Lcd.setRotation(TFT_PORTRAIT)


    def on_wasPressed():
        print("button A pressed")

    pwatch.buttonA.wasPressed(on_wasPressed)

    while True:
        rotateScreen()
        
        if pwatch.wasShaked:
            print("shaked")
    
        pwatch.Lcd.clear()
        pwatch.Lcd.text(0,0,str(pwatch.accX), TFT_GREEN)
        pwatch.Lcd.text(0,25,str(pwatch.accY), TFT_BLUE)
        pwatch.Lcd.text(0,50,str(pwatch.accZ), TFT_PURPLE)
        pwatch.Lcd.text(0,75,str(pwatch.anglePitch), TFT_RED)
        pwatch.Lcd.text(0,100,str(pwatch.angleRoll), TFT_YELLOW)

        utime.sleep_ms(200)