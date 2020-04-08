=========================
可编程加速度传感器模块
=========================

SmartWatch具有加速度传感器，可以获取姿态X 、Y、Z方向的数值和检测是否摇晃状态。

X Y Z方向加速度数值
=========================

pwatch.accX
 accX属性返回当前X方向加速度数值

pwatch.accY
 accY属性返回当前Y方向加速度数值

pwatch.accZ
 accZ属性返回当前Z方向加速度数值

示例1：

.. code-block:: python
    :linenos:

    import time
    from smartWatch import *

    while True:
        print("x = " + str(pwatch.accX))
        print("y = " + str(pwatch.accY))
        print("z = " + str(pwatch.accZ))
        utime.sleep(0.3)


俯仰角（Pitch angle）和翻滚角（Roll angle）
===========================

pwatch.anglePitch
 anglePitch属性返回俯仰角角度

pwatch.angleRoll
 angleRoll属性返回翻滚角角度

示例2：

.. code-block:: python
    :linenos:

    import time
    from smartWatch import *

    while True:
        print("Pitch angle = " + str(pwatch.anglePitch))
        print("Roll angle = "  + str(pwatch.angleRoll))
        utime.sleep(0.2)


振动状态
=============================

pwatch.wasShaked
 wasShaked属性返回当前是否振动

示例3：

.. code-block:: python
    :linenos:

    import time
    from smartWatch import *

    while True:
        if pwatch.wasShaked:
            print("Shaked")
        utime.sleep(0.1)