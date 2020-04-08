=========================
可编程物联模块
=========================

SmartWatch具有可编程物联模块


创建连接MQTT服务客户端
=========================
mqttConnect(server[,clientId,user,password,port])
 创建mqtt客户端，返回客户端对象。

参数server： mqtt服务器地址

可选参数clientId：   客户端id

可选参数user：       用户名

可选参数password：   密码

可选参数port：       mqtt服务端口，默认1883



初始化mqtt客户端
=========================
mqttClient.initMqtt()
 对mqtt客户端初始化


订阅主题及回调
==========================
mqttClient.subscribe_top(topic,callback)
 订阅相关主题和设置收到对应主题消息的回调

topic为主题，callback为对应收到对应主题消息产生的回调


mqtt客户端的启动
==========================
mqttClient.start()
 启动客户端

发布消息
==========================
mqttClient.publish_message(topic,message)
 对主题发布消息

topic为主题，message为发布的消息内容


.. note:: 需要引用mqttConnect。"from lbMqtt import mqttConnect"


示例1：

.. code-block:: python
    :linenos:

    import time
    from smartWatch import *
    import wifiConfig
    from lbMqtt import mqttConnect

    def sub_top_func(message):
        print("message:"+message)

    def sub_top_func1(message):
        print("message:"+message)
    
    def sub_top_func2(message):
        print("message:"+message)
    
    if wifiConfig.connect_wifi("home","12345678"):
        print("Connected to wifi")
        mqttClient = mqttConnect("www.hiibotiot.com")
        mqttClient.initMqtt()
        mqttClient.subscribe_top("/hello",sub_top_func)
        mqttClient.subscribe_top("/hello1",sub_top_func1)
        mqttClient.subscribe_top("/hello2",sub_top_func2)
        mqttClient.start()
    else:
        print("Connect to wifi unsuccessfully")