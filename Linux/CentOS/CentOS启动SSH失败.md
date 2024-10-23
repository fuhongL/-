1.现象是利用systemctl restart sshd 显示一直失败

2.这个现象可能是sshd的配置问题或者缺少一些环境等

3.快速解决办法是重新安装sshd服务（因为SSH服务一般不会影响其他应用）

4.ssh重新安装教程

    yum remove openssh-server openssh-clients # 卸载当前的sshd服务
    
    yum install openssh-server openssh-clients # 安装sshd服务
  
    systemctl start sshd # 启动sshd服务
  
    systemctl enable sshd # 设置开机自动启动
  
    systemctl status sshd # 查看当前的sshd服务状态 显示active说明激活了
5.使用xshell 进行连接测试，如果不通可以安装之前的端口测试进行测试进行排查问题在哪里

6.如果为安装xshell等软件也可以用cmd进行连接测试，语法是 ssh root@1.1.1.1 -p 22,其中远程端口是22，用户名是root，1.1.1.1是IP地址
