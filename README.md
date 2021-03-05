# botvac-wifi
forked from HawtDogFlvrWtr/botvac-wifi

作为1个该软件框架的爱好者，在如下环境中进行了测试。

编译环境：Arduino IDE 1.8.13 开发板管理器 Esp8266 v2.7.4 ...

为能在现行环境下正常编译并运行，参考 sstadlberger/botvac-wifi 修改了几处语句：

*1. 原：ESP8266WebServer server = ESP8266WebServer(80);
    现：ESP8266WebServer server (80);
*2. 去掉mDNS相关语句，同时修改setupEvent()中生成的网页，相关链接改用IP
*3. 原项目中的rBase64语句，如 x=rbase64.encode(stringY);
    经测试不能正常工作，改为：
    rbase64.encode(stringY);
    x = rbase64.result();
    
    或者引用 Esp8266 v2.7.4所带 base64.h
    x = base64::encode(stringY);
  
  
