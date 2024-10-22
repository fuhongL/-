1.参考链接https://blog.csdn.net/qq_52545155/article/details/137229782

2.如果为新装机器，直接使用下面语句即可,注意按顺序执行即可

    cd /etc/yum.repos.d
    
    mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.backup  
    
    curl -o /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo
    
    yum clean all
    
    yum makecache

