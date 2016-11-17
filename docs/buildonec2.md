---
---

上一节中，我们提到了如何配置您的aws虚拟机，如果您已经完成了上述步骤，就可以执行lava命令了，这一节主要用到的命令为——**lava create**

首先解压缩当前机器系统对应的压缩包
	
	tar xf lewo-client-<当前机器系统>-1.0.0.tar.gz
	
	cd lewo/bin

	./lava create --amazonec2-root-size 32 --amazonec2-instance-type c3.xlarge --label zone=analysis --label role=hadoopmaster master
	
	./lava create --amazonec2-root-size 32 --amazonec2-instance-type c3.xlarge --label zone=analysis --label role=hadoopslave --join master slave<1...n>
	
注：目前已测试可运行的实例类型为c3.xlarge，其他实例不确保能mount成功。
	
![12](/images/docs/12.png)
	
上述步骤之后，您就可以在aws控制面板看到新创建的机器 master和所有slave


