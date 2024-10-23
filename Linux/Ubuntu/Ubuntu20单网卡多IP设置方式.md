1.一般服务器会扩容IP，这个时候会多添加一些IP的

2.网卡配置文件位置 ，/etc/netplan/

![image](https://github.com/user-attachments/assets/5a0c6c1d-4b62-4522-9f0c-16404139cb9c)



3.修改配置文件，vi ，提加一个IP，但是还是一个网关，可以设置多个按照顺序对应即可

原

![image](https://github.com/user-attachments/assets/8b44fa88-1243-466b-9770-5c7a5cf45032)



新

![image](https://github.com/user-attachments/assets/0e8eccf9-44a2-41cc-b52c-3457873a06e0)


参考：https://blog.csdn.net/qq_44740145/article/details/126222236
