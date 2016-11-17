---
---

首先进入工作路径

	cd ~/conf
	
可以看到目录结构如下：

	ls
	
	hadoop  hawq   lava
	
不同文件夹对应不同应用的配置文件
<br><br>想要启动我们的应用，请执行：

	cd lava
	./init.sh create proc
	
![14](/images/docs/14.png)
<br>可以看到集群正在创建，大约一分钟之后，创建过程完毕
<br>尝试运行我们的应用：
![15](/images/docs/15.png)