1.SSH远程端口配置文件位置 /etc/ssh/sshd_config

2.利用vim编辑器打开 vi /etc/ssh/sshd_config,这里我修改的端口为22022

![image](https://github.com/user-attachments/assets/55bc8427-2010-481d-b752-69c54058f56b)

3.防火墙放行22022端口或者关闭防火墙

   关闭防火墙     systemctl stop   ufw
   永久关闭（设置开机不自启）systemctl disable ufw
   设置放行 ufw allow 2222/tcp
   
![image](https://github.com/user-attachments/assets/a834a247-e25a-462d-847f-38cd7e4ef0b5)


4.重启shhd服务 systemctl restart sshd

5.如果是云服务器还需要放行22022端口，不同厂商的位置不同

6.测试链接 ssh root@ip -p 22022

