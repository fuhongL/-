1.感觉系统异常，需要查看系统登陆记录

2.查看日志文件

    cat /var/log/secure
    
    grep 'Accepted' /var/log/secure  # 只查看登陆成功的记录

3.对于部分系统差异参考此链接

https://cloud.baidu.com/article/2890880

