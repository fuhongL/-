1.scp（Secure Copy Protocol）是一个用于在网络中的主机之间安全地复制文件和目录的命令行工具。它基于 SSH 协议，因此它提供加密传输。

2.基本语法：scp [options] source destination;

source: 要复制的文件或目录路径; destination: 目标路径，可以是本地路径或远程路径。

3.常用方法

    1) 从本地复制文件到远程主机
      scp /path/to/local/file username@remote_host:/path/to/remote/directory
    2) 从远程主机复制文件到本地
      scp username@remote_host:/path/to/remote/file /path/to/local/directory
    3) 递归复制整个目录到远程主机
      scp -r /path/to/local/directory username@remote_host:/path/to/remote/directory
    4) 从远程主机复制整个目录到本地
      scp -r username@remote_host:/path/to/remote/directory /path/to/local/directory
    5) 使用指定的 SSH 端口
      scp -P 2222 /path/to/local/file username@remote_host:/path/to/remote/directory
    6) 使用私钥文件进行身份验证
      scp -i /path/to/private_key /path/to/local/file username@remote_host:/path/to/remote/directory
      
注意事项： 

    确保你有远程主机的 SSH 访问权限；
    scp 在传输过程中会询问远程主机的密码（如果没有设置密钥认证）；
    传输速度会受到网络带宽的影响，复制大文件时可能需要一些时间。
