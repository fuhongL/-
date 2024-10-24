​
根据官方文档CentOS | Docker Docs进行分析安装

1. 绑定库文件（yum安装方式），CentOS其他版本同样适用

        #yum-utils:这是一个软件包，提供了一组有用的工具和扩展，用于增强 yum 的功能，比如更好的软件源管理
        sudo yum install -y yum-utils 
        sudo yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
      
2. 安装引擎

        #安装最新版本的docker
       
        sudo yum install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

3. 启动docker

    sudo systemctl start docker

4. 验证安装

    sudo docker run hello-world
   
    提示本地没有，拉取镜像后成功运行 
​​​​
 ​​![image](https://github.com/user-attachments/assets/aea3f17d-d64e-4843-a485-252924c5a473)



5.安装过程截图

![image](https://github.com/user-attachments/assets/9cc75238-16d0-49f5-bfbf-7579472a035c)


![image](https://github.com/user-attachments/assets/970e86a1-2a3f-4f21-8d14-3cb1ca724560)


 过程提示按y即可
 
![image](https://github.com/user-attachments/assets/1ff5362d-a3b7-4b88-b68a-61ecca442070)

![image](https://github.com/user-attachments/assets/401f076f-3e4c-4a18-a1e0-7bd1a2b6b021)







​
