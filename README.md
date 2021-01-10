# SuperRDP

[English](README_en.md)

众所周知，Windows家庭版无法使用远程桌面，`RDP Wrapper Library`就是用于恢复家庭版该部分阉割的功能。

本项目是基于[rdpwrap](https://github.com/stascorp/rdpwrap)修改的，在此感谢[stascorp](https://github.com/stascorp)的无私的工作。

rdpwrap主要包括安装器和服务dll。

原始版本安装器采用的Delphi(一门比较久远现在很少使用的语言)编写的，作为一个安全从业人员的本能，并不是非常信任使用别人编译的二进制文件。

另外下载版本无法在windows新版中（原版已经2年没有更新了）使用，本着探索技术本真的初心，我觉得研究一下rdpwrap的工作原理。

**所以用C语言重写了安装器，然后优化了服务模块的代码，最终产生了本项目。**

经过重写和研究，弄明白了rdpwrap的工作原理，原来需要对远程桌面服务模块（termsrv.dll)做patch，让其恢复专业版等拥有的功能。

另外termsrv.dll在不同版本中修复patch的位置和信息也会不同，所以需要持续更新配置文件中的信息。

由于我目前对远程桌面功能重度依赖，并且系统一直是正版Windows家庭版，所以会一直持续更新对新版本的功能支持。

所以，如果大家有需要，欢迎关注（star）并使用。

**使用方法：**

1. 可直接下载release发布文件，运行SuperRDP.exe(需管理员权限)
2. 根据提示选择1（安装）或者2（卸载）
3. 等待完成即可

```
--------------------------------------------------------
---------SuperRDP for Windows 10 Home Version-----------
-------------Copyright (c) 2021 anhkgg.com--------------
-------------anhkgg | 公众号：汉客儿 -------------------
--------------------------------------------------------

--------------------------------------------------------

[+] SuperRDP initialize...

[*] SuperRDP already installed? 【Yes!】

[+] SuperRDP initialize success...

--------------------------------------------------------

Please select option:
    1: Install SuperRDP to Program Files folder (default)
    2: Uninstall SuperRDP
    3: Force restart Terminal Services

>
```

**验证远程桌面服务是否启用成功的方法：**

1. Win+R，输入mstsc.exe启动远程桌面程序
2. 输入127.0.0.1，连接成功基本验证服务启用成功
3. 或者也可以使用原版的RDPCheck.exe进行验证

# update

目前支持最新Windows 10（X64）：

1. 系统：10.0.19042.685 | termsrv.dll：10.0.19041.662 | 更新时间：2021年1月10日

termsrv.dll 10.0.18362.657之后的版本都是由于加入，经过长时间实战验证，请放心使用。

**应该是兼容大部分老版本的，如果没有相应系统版本信息，可以联系我更新支持。**

# Support me

如果觉得对你有帮助，请我喝杯咖啡。

![img](pay.png)