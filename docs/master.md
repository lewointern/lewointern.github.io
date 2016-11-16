---
---
### 初始化master机器
这一步骤会将现有资源拷贝并解压到master机器，包括所有镜像、rpm软件包和配置文件，拷贝完成后会在master上部署docker和kubernetes

	cd lewo/bin

亚马逊虚拟机：

	./lava create --driver generic --generic-ssh-user ec2-user --generic-ip-address <master的公网ip> --generic-ssh-key ~/.lava/machines/master/id_rsa master
	
物理机：
	
	./lava create --driver generic --generic-ssh-user ec2-user --generic-ip-address <master的私有ip> --generic-ssh-key ~/.lava/machines/master/id_rsa master
	
###在master创建集群
初始化磁盘

	cd /tmp/lewo/conf
	./initdisk.sh
	
创建演示版

	cd /tmp/lewo/conf/lava
	./init.sh create demo
	
创建产品版

	./init.sh create proc
	
如果想要删除节点群，请执行

	./init.sh delete <demo/proc>	