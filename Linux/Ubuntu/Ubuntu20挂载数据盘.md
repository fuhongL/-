1.首先在已有的系统中挂载新数据盘需要新建一个目录 :mkdir /www,这里以www文件夹为例子，这样后续一般的网页文件都可以放到这里

2.利用lsblk查看是否存在当前磁盘,查看需要挂载的磁盘为vdb

![image](https://github.com/user-attachments/assets/7683dc73-ba6b-493a-8a0e-cbb0a0715542)


3.分区

fdisk /dev/vdb

![image](https://github.com/user-attachments/assets/02d9ea60-5794-403b-a655-cdb90c36be28)

  输入 n 创建新分区。
  
  输入 p 创建主分区。
  
  按照提示输入分区号和起始、结束扇区，或者直接使用默认设置。
  
  输入 w 保存更改并退出。
  
![image](https://github.com/user-attachments/assets/6b41c9ee-d877-4059-8085-970575bfe17f)


4.格式化分区

将新分区格式化为 ext4 文件系统（你可以根据需要选择其他文件系统）。 mkfs.ext4 /dev/vdb1

![image](https://github.com/user-attachments/assets/5f8daa5c-bee7-49cc-9aa6-a32d6be86a5e)

5创造挂载点

  新建目录 ：mkdir -p /www
  
  挂载分区 ：mount /dev/vdb1 /www
  
  验证挂载 ：df -h

![image](https://github.com/user-attachments/assets/68925540-a181-4798-a798-29625bfa7d93)


6.自动开机挂载
  备份 fstab 文件（以防止出错）：
  
  cp /etc/fstab /etc/fstab.bak
  
  输入内容到 /etc/fstab
  
  echo "/dev/vdb1   /www   ext4   defaults   0   2" >>/etc/fstab
  
7.测试挂载是否成功

  卸载：umount /www
  
  刷新：mount -a
  
  成功查看
  
![image](https://github.com/user-attachments/assets/ba969b5f-50dc-40df-be1f-96bc239f9a47)
