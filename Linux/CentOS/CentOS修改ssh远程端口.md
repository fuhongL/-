1.防止系统被爆破，或者其他安全隐患着想

2.修改ssh端口四步走

    1)关闭selinux ，将SELINUX=后面的内容改为SELINUX=disabled
        文件位置：/etc/selinux/config
        
![image](https://github.com/user-attachments/assets/a7068ae6-0e18-490b-923a-897448fb8529)

    2)修改ssh配置文件,将Port 后面的22改为你想放行的端口
        文件位置：/etc/ssh/sshd_config
![image](https://github.com/user-attachments/assets/73792d2c-7886-43dc-b171-83280c318298)

    3)修改防火墙配置
        firewall-cmd --zone=public --list-ports # 查看放行的端口
        firewall-cmd --zone=public --add-port=16345/tcp --permanent # 永久放行指定端口16345
        firewall-cmd --reload # 配置生效
    4)重启服务器的ssh和firewalld
        systemctl restart firewalld # 重启防火墙
        systemctl restart sshd # 重启sshd服务
        
具体操作参考链接  https://blog.csdn.net/m0_65482680/article/details/141897482?spm=1001.2014.3001.5501



