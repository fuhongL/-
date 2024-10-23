1.当发现系统有异常进程运行时需要进行杀死

2.前面说过可以用top命令进行查看负载，当发现不正确的进程后，需要利用具体命令查看和杀死

3.常用命令介绍

        1)ps 命令
          ps命令用于显示当前用户的活动进程。
          显示所有的进程（包括其他用户的进程） ps aux
          显示特定用户的进程 ps -u username
          显示进程树  ps -ejH
        2)top命令
          显示系统中的实时进程，并且可以动态更新。
          启动命令：top
          退出命令：按q
          安装命令：yum install htop
        3)pgrep命令
          用于根据名称查找进程的PID（进程标识符）： pgrep process_name
        4)杀死进程 kill命令
          kill命令用语终止进程，使用进程的PID: kill PID
          Kill命令强制杀死进程：kill -9 PID
        5)pkill命令
          使用进程名称来终止进程，不需要PID：pkill process_name
          强制杀死进程: pkill -9 process_name
        6)killall命令
          killall命令根据进程名称终止所有同名进程 ：killall  process_name
          killall命令强制杀死所有同名进程 ：killall -9 process_name
        实例
        kill 1234，kill -9 1234，pkill httpd，ps aux | grep httpd
注意事项

使用 kill -9 是强制杀死进程，可能会导致数据丢失，建议首先使用 kill 命令尝试正常终止进程。
