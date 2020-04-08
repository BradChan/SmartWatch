=========================
可编程闹钟模块
=========================

SmartWatch具有可编程闹钟。

设置闹钟时间
=========================
pwatch.clock.set_valid_daily_alarm(hours,minutes)
 参数hours和minutes分别为定时的小时和分钟


闹钟到时响应回调设置函数
=========================
pwatch.clock.set_alarm_callback(callback)
 参数callback为回调函数


当前时钟时间
=========================
pwatch.time()
 返回元祖数据 （years,month,day,hours,minutes,second） 如（2020，4，8，15，30，30）

示例1：

.. code-block:: python
    :linenos:

    import time
    from smartWatch import *

    def clock_alarm():
        print("clock up " + str(pwatch.time()))

    pwatch.clock.set_alarm_callback(clock_alarm)
    pwatch.clock.set_valid_daily_alarm(hours=20,minutes=36)

    while True:
        print(pwatch.time())
        time.sleep(30)