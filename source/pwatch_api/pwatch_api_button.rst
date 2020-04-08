=========================
可编程Button模块
=========================

SmartWatch具有四个可编程按钮：buttonA、buttonB、buttonC、buttonD


按钮按下状态
=========================
pwatch.buttonA.wasPressed()
 方法返回按钮当前是否按下


pwatch.buttonA.wasReleased()
 方法返回按钮是否释放状态即未按下状态


示例1：

.. code-block:: python
    :linenos:

    import time
    from smartWatch import *

    while True:
        if pwatch.buttonA.wasPressed():
            print("Button A was pressed")
        
        if pwatch.buttonA.wasReleased():
            print("Button A was Released")

        utime.sleep(0.1)


按钮回调方法
===========================

示例2：

.. code-block:: python
    :linenos:

    import time
    from smartWatch import *

    def on_wasPressed():
        print("Button A was pressed")
    
    def on_wasReleased():
        print("Button A was Released")

    pwatch.buttonA.wasPressed(on_wasPressed)
    pwatch.buttonA.wasReleased(on_wasReleased)