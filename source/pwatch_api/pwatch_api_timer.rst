=========================
可编程计时模块
=========================

SmartWatch具有可编程计时模块


设置倒计时
=========================
pwatch.timer.TickTime(hours,minutes,seconds)
 设置倒计时时间 参数hours、minutes和seconfs分别对应具体时间的小时、分和秒

倒计时启动
=========================
pwatch.timer.start()
 启动倒计时时钟


倒计时剩余时间
==========================
pwatch.timer.remainSeconds()
 获取倒计时剩余时间（秒）


倒计时是否结束
==========================
pwatch.timer.isTimeUp()
 查询是否到达倒计时时间点


时钟状态切换
==========================
pwatch.timer.controlStatus()
 控制时钟状态。暂停/继续功能


时钟运行时间
==========================
pwatch.timer.currentTimerValueS()
 查询运行时间(秒)，用于秒表功能