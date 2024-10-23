1.SSH远程端口配置文件位置，/etc/ssh/sshd_config

2.修改Port 22（默认22也有可能修改过Port num为准），Port +上你想修改的端口

![image](https://github.com/user-attachments/assets/cad4e35e-fd03-44ca-8033-d74671648255)


3.查看防火墙，firewalld iptables ufw，一般linux系统是自带这三种类型，分别放行远程端口22022， ufw allow 22022/tcp

4.重启ssh服务，systemctl restart sshd

5.查看服务状态，systemctl status sshd

![image](https://github.com/user-attachments/assets/29e5f568-0dcb-4721-81a1-a02a1ac099ce)


6.测试远程端口利用xshell，或者cmd, 命令格式 ssh 用户名@IP -p 远程端口号
