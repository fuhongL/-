1.需要自己配置网卡信息【注意如果为云服务器使用vpc网络请不要顺便修改网卡】

2.常用命令

    ip a，查看当前的网卡配置（ifconfig也可以，但是某些未安装这个命令）

3.网卡文件目录

    /etc/sysconfig/network-scripts/下，具体情况需要cd 到这个目录后查看

    cd /etc/sysconfig/network-scripts/

    ls ，查看需要修改的网卡名文件，ip a看到的名称

4.打开网卡文件

    vi 网卡名文件

5.具体详细配置介绍情况参考链接，主要修改 IP，网关，掩码，DNS。

    配置详解 :https://blog.csdn.net/VickHUC/article/details/82562017
