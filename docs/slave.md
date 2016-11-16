---
---
### 初始化slave机器
初始化slave机器的方法与master基本相同
<br>
<br>亚马逊虚拟机：

	./lava create --driver generic --generic-ssh-user ec2-user --generic-ip-address <slave的公网ip> --generic-ssh-key ~/.lava/machines/slave01/id_rsa --join master slave01
	
<br>物理机：
	
	./lava create --driver generic --generic-ssh-user ec2-user --generic-ip-address <slave的私有ip> --generic-ssh-key ~/.lava/machines/slave01/id_rsa --join master slave01
	
### 在slave创建集群

方法与master一致