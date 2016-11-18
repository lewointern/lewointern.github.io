---
---

1. 获取当前系统对应压缩包
![05](/images/docs/05.png)
2. 配置SSH免密码登录（前提为装有SSH）
		
		ssh-keygen -t rsa -P ''
	
	将生成的公钥 id_rsa.pem 写入客户机的authorizedkeys里
		
		sudo vi ~/.ssh/authorized_keys
		
3. 解压当前系统对应的压缩包
		
		tar xvf lewo-client-<当前机器系统>-1.0.0.tar.gz
		
		
4. 用lava命令将资源传递到每一台物理机
		
		cd lewo/bin
		./lava scp lewo-server-1.0.0.tar.gz <目标机器>: <路径>
		
5. 部署master
		
		./lava create --driver generic --generic-ssh-user <master的机器名> --generic-ip-address <master私有ip> --generic-ssh-key ~/.ssh/id_rsa master
		
6. 部署slave
		
		./lava create --driver generic --generic-ssh-user <slave的机器名> --generic-ip-address <slave的私有ip> --generic-ssh-key ~/.ssh/id_rsa --join master slave01