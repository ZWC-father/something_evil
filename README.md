# something-evil——恶意小程序合集
## 键盘记录器
#### KeyLogger_v1.0.cpp
+ 自动隐藏
+ 记录所有常用按键
+ 将键盘记录伪装在图片文件末尾并含有时间戳
+ 自动注册成开机自启（此功能可能会报毒）
+ 可扩展记录鼠标和窗口标题

#### KeyLogger_Client_v2.0.cpp
+ tcp实时发送键盘记录（只能在低延迟低丢包网络环境下使用，没有做任何粘包拆包的处理）
+ tcp可自动重连
+ 使用低级键盘钩子和消息循环，记录准确
+ 增加实时状态输出，便于调试

#### KeyLogger_Client_v2.1.cpp
+ 在2.0基础上少量优化

#### KeyLogger_Server_v2.0.cpp
+ 同时兼容v2.0和v2.1的服务端
+ 实时从Client获取键盘消息
+ 可记录到日志中，含时间戳

**TODO:使用更加隐蔽的记录方式，以避免被杀毒软件查杀；制作日志解析器**

## 远程命令执行
#### RCE_Client_v1.0.cpp/RCE_Server_v1.0.cpp
+ 客户端为被控端，可一定程度上避免被防火墙拦截（首次运行不会有Windows Defender的提示）
+ 使用system()执行命令，并传回进程返回值（不能进行命令交互）

#### RCE_Client_v2.0.cpp/RCE_Server_v2.0.cpp
+ 优化tcp传输
+ 使用popen()执行命令，支持回显（只能得到进程的stdout，得不到stderr）
