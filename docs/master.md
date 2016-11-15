---
---

	./lava create master_n --amazonec2-root-size 32 --no-software
	./lava create --driver generic --generic-ssh-user ec2-user --generic-ip-address 54.223.159.241 --generic-ssh-key ~/.lava/machines/master/id_rsa master