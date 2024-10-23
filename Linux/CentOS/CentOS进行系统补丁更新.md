1.为了在当前版本的补丁最安全，减少系统本身的漏洞

    CentOS 9
    更新软件包索引（可选）：
    
    dnf check-update
    
    仅安装安全更新：
    
    dnf update --security

此命令将只应用安全补丁，而不会更新其他非安全相关的组件。确保在执行之前备份重要数据。

Centos7即以下

    yum check-update
    
    yum install yum-utils
    
    yum update --security
