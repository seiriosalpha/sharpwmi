
介绍：
&emsp;这是一个基于135端口来进行横向移动的工具,具有执行命令和上传文件功能。
&emsp;通过wmi来执行命令
&emsp;通过注册表来进行数据传输

原理
&emsp;执行命令：
&emsp;&emsp;&emsp;通过wmi来执行命令，server将命令结果存在本机注册表，然后client连接注册表进行读取命令结果
&emsp;上传文件:
&emsp;&emsp;&emsp;client将需要上传的文件放到server的注册表里面，然后server通过powershell来操作注册表方式来取文件然后释放到本地

<br>
优点：

&emsp;1、不依赖139和445端口

缺点：
&emsp;1、目前只支持上传512kb以下的文件，因为注册表每个值值长度不能超过512kb。
&emsp;2、执行命令和上传文件都依赖powershell

todo:
&emsp;1、用添加增加多个值的方式来实现上传任意大小文件
&emsp;2、去除powershell依赖

![](1.png)

![](2.png)
