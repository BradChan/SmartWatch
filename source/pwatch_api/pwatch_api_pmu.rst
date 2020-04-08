=========================
可编程电源模块
=========================

SmartWatch具有可编程电源管理，获取电源基本信息。

电源信息更新
=========================
pwatch.updateInfoPmu()  
 更新当前电源信息


检测USB是否连接
=========================
pwatch.pmu.isUSBInserted()
 获取USB连接状态 True--USB连接  False--USB未连接


电池电量信息
=========================
pwatch.pmu.infoPmu.batteryQuantity
 当前电池电量数值 0-100


电源充电信息
==========================
pwatch.pmu.infoPmu.onCharging
 当前是否正在充电， True--充电状态  False--未充电状态


电池连接信息
=========================
pwatch.pmu.infoPmu.battConnected
 当前电池是否连接， True--连接电池  False--未连接电池

