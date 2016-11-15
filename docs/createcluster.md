---
---
### 本地安装测试
local端：

	cd lava/bin
	./lava create client --amazonec2-root-size 32
	tar cvf lava.tar.gz lava
	lava scp lava.tar.gz client:~/
	lava ssh client
	
---

client端：

	tar xvf lava.tar.gz 
	cd lava
	make build-server
