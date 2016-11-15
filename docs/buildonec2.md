---
---

上一节中，我们提到了如何配置您的aws虚拟机，如果您已经完成了上述步骤，就可以执行lava命令了，这一节主要用到的命令为——**lava create**

首先解压缩当前机器系统对应的压缩包
	
	tar xvf lewo-client-<当前机器系统>-1.0.0.tar.gz
	
	cd lewo/bin
	
	./lava create master --amazonec2-root-size 32 --no-software
	
	./lava create slave01 --amazonec2-root-size 32 --no-software
	
![11](/images/docs/11.png)
	
上述步骤之后，您就可以在aws控制面板看到新创建的机器 master、slave01

#### 在新创建的虚拟机上部署docker、k8s等资源
首先将 lewo-server 的压缩包放到 lewo/ 路径
	
	mv lewo-server-1.0.0.tar.gz lewo/

用当前的资源部署master

	cd lewo/bin
	
	./lava create --driver generic --generic-ssh-user ec2-user --generic-ip-address <master公网ip> --generic-ssh-key ~/.lava/machines/master/id_rsa master01


![12](/images/docs/12.png)
(slave的部署方法同master)
<br>
部署完成之后，可以登录到对应机器上查看状态
