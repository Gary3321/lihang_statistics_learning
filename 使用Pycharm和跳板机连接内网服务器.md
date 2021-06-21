the followings are from [here](https://blog.csdn.net/witnessai1/article/details/89217498)

配置跳板机和服务器的免密登录，实现方式有多，这里只列出了一种方式。

在本地配置

vim ~/.ssh/config
在config文件中输入以下内容

Host *
    ControlPersist yes
    ControlMaster auto
    ControlPath ~/.ssh/master-%r@%h:%p
完成配置后在本地登录一次跳板机.

登录跳板机，并在跳板机配置

vim ~/.ssh/config
在config文件中输入以下内容

Host *
    ControlPersist yes
    ControlMaster auto
    ControlPath ~/.ssh/master-%r@%h:%p
完成配置后在跳板机上登录一次内网服务器。

步骤二 设置ssh隧道
在本地命令行输入如下命令即可：

ssh -N -f -L 6000:<内网服务器ip>:22 -p <跳板机端口> username@<跳板机ip>

ssh -N -f -L 6000:lobstick.cs.ualberta.ca:22 -p 22 hongchan@innisfree.cs.ualberta.ca -o TCPKeepAlive=yes

-o TCPKeepAlive=yes
上述命令各个参数的含义如下：
-N 告诉SSH客户端，这个连接不需要执行任何命令。仅仅做端口转发
-f 告诉SSH客户端在后台运行
-L 做本地映射端口
关于SSH建立管道参考

此时，登录本地的6000端口就相当于登录内网服务器了。

ssh -p 6000 服务器用户名@localhost

ssh -p 6000 hongchan@localhost

步骤三
配置pycharm
这里只需配置ip为127.0.0.1, 端口为6000，并输入内网服务器的账号密码即可看到服务器安装的python.
具体配置方式[参考](https://www.cnblogs.com/xiongmao-cpp/p/7856596.html)

Reference
关于SSH建立管道
https://www.cnblogs.com/fbwfbi/p/3702896.html

PyCharm 配置远程python解释器和在本地修改服务器代码
https://www.cnblogs.com/xiongmao-cpp/p/7856596.html
