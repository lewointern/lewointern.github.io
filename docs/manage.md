---
---

- 通过 kubectl 命令可以便捷的查看集群的状态，例如:
	
		kubectl get pods
		kubectl logs <pod名称>
		
- 您可以进入某个运行中的结点来查看状态，以hdfs的namenode为例：

		kubectl exec -ti hdfs-nn /bin/bash
		hdfs dfsadmin -report
		hdfs dfs -ls /
		
  或进入hawq master查看状态和测试：
  		
  		kubectl exec -it hawq-master-0 /bin/bash
  		source /usr/local/hawq/greenplum_path.sh
  		psql -d postgres
  		
  			create table test(a int);
  			insert into test values(1);

- 您还可以通过查看k8s dashboard的方法来查看某台机器的运行状态，通过浏览器查看dashboard只需在浏览器中访问<br>
  <br>亚马逊虚拟机：<对应机器公网ip>:30300
  <br>物理机(在对应机器访问)：localhost:30300
  
![13](/images/docs/13.png)
  