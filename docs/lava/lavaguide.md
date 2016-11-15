---
---

### 配置亚马逊AWS虚拟机
1. 用浏览器访问https://console.amazonaws.cn/iam/home#/users前提为拥有亚马逊aws公司账户）
2. 点击对应用户
![01](/images/docs/01.png)
3. 点击创建访问密钥
![02](/images/docs/02.png)
4. 点击下载凭证
![03](/images/docs/03.png)
5. 查看下载的csv文件并写入aws配置文件（使用vim、文本编辑器等均可）
![04](/images/docs/04.png)

		vim ~/.aws/credentials
		
		[default]
		aws_access_key_id = <上图中"用户名"后的第一个字段>
		aws_secret_access_key = <上图中"用户名"后的第二个字段>
		
