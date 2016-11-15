---
---

1. 获取当前系统对应压缩包
![05](/images/docs/05.png)
2. 配置SSH免密码登录（前提为装有SSH）
		
		ssh-keygen -t rsa -P ''
	
	将生成的公钥 id_rsa.pem 写入客户机的authorizedkeys里<br><br>
3. 解压当前系统对应的压缩包
		
		tar xvf lewo-client-<当前机器系统>-1.0.0.tar.gz
		
		
4. 用lava命令将资源传递到每一台物理机
		
		cd lewo/bin
		./lava scp lewo-server-1.0.0.tar.gz <目标机器>: <路径>