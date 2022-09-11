# SunloginRCE GUI

向日葵命令执行图形化利用工具

纯学习开发使用，大佬勿喷

# 工具界面

漏洞检测 

![1](https://user-images.githubusercontent.com/44337217/189516819-8066e2df-d3c0-4799-83ac-9dc4d6f1e395.png)


命令执行（主要是利用cmd去执行，powershell查杀比较严，故没有用powershell去执行命令）

![2](https://user-images.githubusercontent.com/44337217/189516955-4a0820eb-0a82-41e3-b1bc-1c700892c88f.png)


增加Bypass模式 （主要利用 /check?cmd=ping/../进行部分杀软的绕过）

目标环境开启某数字安全防护 采用命令执行会被直接拦截

![3](https://user-images.githubusercontent.com/44337217/189516958-12ed1e49-bec8-4228-9ec0-9c53f3a53783.png)

采用bypass模式可进行绕过 执行部分命令

![4](https://user-images.githubusercontent.com/44337217/189516960-55944df7-9270-4b69-92a7-a53a682d4f81.png)


# 参考链接

GUI框架部分代码及相关代码执行语句有参考如下师傅文章，感谢前辈的总结

https://github.com/yhy0/ExpDemo-JavaFX

https://mp.weixin.qq.com/s/417I9fuDHN53VGZcnZYS3g

https://mp.weixin.qq.com/s/7xgiLVx6Nq0F9eKxcCV8nw

# 存在BUG问题

1、采用虚拟机搭建漏洞环境时，发现执行如tasklist /svc、dir、netstat -ano等命令时，使用burpsuite会回显成功，但时间比较久，故在程序代码中将http请求的读取超时时间进行了延长，所以工具在执行该相关命令可能会有稍微的卡顿，可稍微等一会儿 ~~。

2、实战中测试，发现部分目标存在漏洞，但一执行任何命令就会卡死（采用Bypass模式也不行），推测是其他杀软或者防护进行拦截，导致卡死，后续在研究看看

3、可能使用中还有很多的bug问题，有时间在研究 研究，大佬勿喷

# 免责声明

1、本工具仅用于学习交流，请勿在未授权的情况下，进行非法攻击等一切违法行为，如您在使用本工具的过程中存在任何非法行为，您将自行承担所有后果，与本作者无关。
