1.sshd配置文件的位置 

    /etc/ssh/shhd_config

2.修改Port字段后的数字即可

![image](https://github.com/user-attachments/assets/6cf3084c-da54-4c9b-8360-1b2ab864044e)

3.修改防火墙规则（如果系统防火墙已关闭请忽略，此处以firewalld防火墙为例）

    systemctl status firewalld # 查看防火墙状态,显示runing表示已经激活

    ![image](https://github.com/user-attachments/assets/d90c3eb0-0170-45fe-bd84-ff797b3604a1)

    firewall-cmd --permanent --add-port=12009/tcp # 设置放行12009
    
    firewall-cmd --reload  # 使防火墙配置生效
    
    firewall-cmd --list-all # 查看当前的配置

![image](https://github.com/user-attachments/assets/307be2b0-8fb6-4145-85ef-e586c89c59f9)
    
4.重启sshd服务

    systemctl restart sshd

5.链接测试即可。（xshell、cmd命令行等）
