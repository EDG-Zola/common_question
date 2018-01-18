##此文件记录在日常操作过程中遇到的一些问题
###一、Linux系统问题
####1.文件及文件夹重命名命令
+ **mv 原文件（夹） 新文件（夹）**
####2.删除文件（夹）
+ **rm -rf 文件（夹）** 此命令时彻底删除命令，不能在垃圾箱找到
####3.忘记root密码的修改方法，具体可以查看[这个网址](http://www.cnblogs.com/xuyingying/archive/2008/10/16/1312584.html)
+ 在终端输入命令**sudo passwd**，然后输入当前用户的密码,终端会提示我们输入新的密码并确认，此时的密码就是root新密码。
+ 修改成功后，输入命令**su root**，再输入新的密码就ok了。
####4.U盘出现不能访问KINSTON的问题
+ 安装ntfs-3g包**sudo apt-get install ntfs-3g**
+ 运行**sudo ntfsfix /dev/sdb1**修复U盘，其中/dev/sdb1为U盘所在的设备文件
###二、python问题
####1.'range' object doesn't support item deletion
+ m = **list**(range(4))
###三、tensorflow问题

###四、conda的一些命令
####1.创建一个名为tensorflow的python3.5的环境
+ **conda create -n tensorflow python=3.5**
####2.启动与关闭tensorflow环境
+ **source activate tensorflow**
+ **source deactivate tensorflow**
####3.删除环境变量
+ **conda remove --name tensorflow --all**
####4.查看环境变量的信息
+ **conda info --envs**
####5.查看环境安装包
+ **激活环境source activate tensorflow**
+ **conda list**

###五、github的一下配置
####1.安装git
+ **sudo apt-get install git**
####2.初次运行 Git 前的配置,Git 自带一个 git config 的工具来帮助设置控制 Git 外观和行为的配置变量
+ 配置用户名**git config --global user.name "Xavier"**
+ 配置用户的github帐号**git config --global user.email wellzengwei@163.com**
+ note: 如果使用了 --global 选项,那么该命令只需要运行一次
####3.检查配置信息
+ **git config --list**
####4.获取帮助
+ **git help < verb >**
+ git help config
#####5.生成SSH公钥，与github仓库创建链接
+ 通过运行**ssh-keygen**程序来创建**id_rsa和id_rsa.pub**文件，在~/.ssh/文件夹内
+ 在github网站上的setting -> SSH and GPG keys -> new ssh key
+ 把第一步生成的**id_rsa.pub**文件中的内容添加到第二部的位置中
+ 测试是否链接成功**ssh -T git@github.com**，出现一个问题，点击yes，然后出现Hi EDG-Zola! You've successfully authenticated, but GitHub does not provide shell access.表示配置SSH成功！