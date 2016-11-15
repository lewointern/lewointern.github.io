---
---

	./lava create slave01_n --amazonec2-root-size 32 --no-software
	./lava create --driver generic --generic-ssh-user ec2-user --generic-ip-address 54.223.101.116 --generic-ssh-key ~/.lava/machines/slave01/id_rsa --join master01 slave01