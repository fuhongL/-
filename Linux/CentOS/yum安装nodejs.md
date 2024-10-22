1.利用yum install nodejs命令进行安装时提示错误No package nodejs available

![image](https://github.com/user-attachments/assets/11f8e72c-872b-44dd-a61c-a45910fb40f3)

2.安装nodejs默认yum官方仓库是没有的，这个情况需要先将资源下载到本地仓

#提供的命令用于在使用 RPM 包管理器的系统上

  curl --silent --location https://rpm.nodesource.com/setup_16.x | bash -

  curl: 这个命令行工具用于从服务器获取或发送数据。在这里，它用于下载 NodeSource 网站上的脚本。

  --silent: 此选项使 curl 在运行时保持静默，不显示进度或错误信息。

  --location: 此选项允许 curl 跟随任何发生的 HTTP 重定向。

  https://rpm.nodesource.com/setup_16.x: 这是 Node.js 16.x 版本的设置脚本的 URL。

  | bash -: 管道符 (|) 将 curl 命令的输出传递给 bash，后者将执行这个脚本

3.再利用yum install nodejs进行安装

![image](https://github.com/user-attachments/assets/9ef758ea-8ee2-4d13-a42c-6f516951d652)

4.检查版本 node -v

![image](https://github.com/user-attachments/assets/97a552df-9f35-4602-bdf0-fcf0194c0f48)
