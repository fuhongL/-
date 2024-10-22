适合于Linux（CentOS，Debian，Ubuntu，Fedora）

情景：默认系统已经安装，但是后期系统有加了新的磁盘

注意：新加的磁盘需要挂载到系统中的目录才能使用

1.创建一个新目录（为了不覆盖已经有的数据）
    mkdir -p 目录名 # 可以是多级目录名称
    
2.查看数据盘

    fdisk  -l
 ![image](https://github.com/user-attachments/assets/a72e5d7f-864c-4c76-9963-771b587b101d)
    
3.磁盘分区
        
        fdisk /dev/vdb
![image](https://github.com/user-attachments/assets/62d0001e-833c-47db-a0f5-7a9bd987a8f4)

4.格式化分区

    mkfs.ext4  /dev/vdb1
    
![image](https://github.com/user-attachments/assets/27d22c0f-8776-4eb7-9573-c27bf6cb479b)

5.将分区挂载到目录

    mount /dev/vdb1 /www
    lsblk #查看分区情况
    
![image](https://github.com/user-attachments/assets/46292d4b-b3a3-4bbf-a38a-49c7f58828ef)

6.写入磁盘启动信息

    echo "/dev/vdb1    /www    ext4    defaults    0    0" >>/etc/fstab # 将分区情况写入启动信息
    mount -a /www # 刷新 /www
    umount /www # 卸载 /www测试
    lsblk # 查看/www是否自动挂载
    
![image](https://github.com/user-attachments/assets/36341af4-013f-4fb4-8c81-e3f59b6f9b9c)

补充：

    进入 fdisk 后，可以使用以下常用命令：
    m：显示帮助信息。
    p：显示当前分区表。
    n：创建一个新的分区。
    d：删除一个分区。
    w：保存更改并退出。
    q：不保存更改并退出。
    t：更改分区的类型。
    a：设置活动分区。



