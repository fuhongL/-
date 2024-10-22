1.网卡的文件配置和CentOS7大致一样

2.具体配置

![image](https://github.com/user-attachments/assets/2d1894d4-ef42-4328-8b34-e0d5a6a1d22d)


3.重启网卡

  方法 1：
    
    # 列出所有网络接口，找出需要重启的接口名称 
    nmcli device status 
    # 重启网卡
    nmcli device disconnect eth0  # 假设你要重启的接口名称为 eth0
    nmcli device connect eth0
    
 方法 2：
 
    # 使用 ifdown 和 ifup 命令
    ifdown eth0
    ifup eth0
    
方法 3：

    # 使用 systemctl 重启 NetworkManager
    systemctl restart NetworkManager
