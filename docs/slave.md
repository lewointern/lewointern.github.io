---
---
### 初始化slave机器
初始化slave机器的方法与master基本相同
<br>
<br>亚马逊虚拟机：

	./lava create --amazonec2-instance-type c3.xlarge --join <对应master的机器名> --label zone=analysis --label role=hadoopslave <slave的机器名>

	
<br>物理机：
	
	./lava create --driver generic --generic-ssh-user ec2-user --generic-ip-address <slave的私有ip> --generic-ssh-key ~/.lava/machines/slave01/id_rsa --join <对应master的机器名> <slave的机器名>
	
### 在slave创建集群

在master创建集群之后，节点会自动分配到slave上去部署。