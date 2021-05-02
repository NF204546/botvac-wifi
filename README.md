# botvac-wifi
forked from HawtDogFlvrWtr/botvac-wifi

### 作为1个该软件框架的爱好者，在如下环境进行了测试
###As a fan of the software framework, the test was carried out in the following environment

编译环境：Arduino IDE 1.8.13 开发板管理器 Esp8266 v2.7.4 ...
Compiling environment: Arduino ide 1.8.13 development board manager esp8266 v2.7.4

为能在现行环境下正常编译并运行，参考 sstadlberger/botvac-wifi 修改了几处语句：
In order to compile and run normally in the current environment, several statements are modified with reference to sstadlberger/botvac-wifi

*1. 原 original：ESP8266WebServer server = ESP8266WebServer(80);  
    现 now：ESP8266WebServer server (80);  
	
*2. 去掉mDNS相关语句，同时修改setupEvent()中生成的网页，相关链接改用IP    
    Remove the mDNS related statements, modify the web pages generated in setupevent(), and change the related links to IP address

*3. 原项目中的rBase64语句，如 x=rbase64.encode(stringY)，经测试不能正常工作，改为：    
    The rbase64 statement in the original project, such as x = rbase64. Encode (string y),After testing, it can not work normally	
	
	rbase64.encode(stringY);    
	x = rbase64.result();      
	或者引用 Esp8266 v2.7.4所带 base64.h 
	Or refer to Base64. H in esp8266 v2.7.4
	x = base64::encode(stringY);   
