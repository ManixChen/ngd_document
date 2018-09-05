<blockquote class="success">
	什么是镜像
</blockquote> 
 
>    通过虚拟终端管理系统创建的虚拟磁盘，在服务器本地为一个稀疏格式的不可执行文件，文件大小为创建大小，占用空间为实际使用空间，用于映射到终端上存放虚拟操作系统与数据的文件，即为镜像文件；

</br>
1.如何备份与恢复镜像

>和信下一代云桌面系统目前不支持镜像备份与恢复，您可以手动进行备份和恢复； 
>
<blockquote class="info">
	手动备份镜像的方法：
</blockquote> 
> 1）在没有终端在线的情况下，停止服务器上所有的和信服务，包括VEMSBu、VEMSDaemon、VEMSEDiskServer、VEMSIO、VEMSServer Server edition几个服务；
2）找到需要备份的镜像文件，使用FastCopy等工具将镜像文件拷贝到目标设备中；
3）启动第1步中停止的服务。


<blockquote class="info">
	手动恢复镜像的方法：
</blockquote> 

> 1）在没有终端在线和没有超级管理员的情况下，停止服务器上所有的和信服务，包括VEMSBu、VEMSDaemon、VEMSEDiskServer、VEMSIO、VEMSServer Server edition几个服务；
> 	2）找到需要恢复的镜像文件，使用FastCopy等工具将镜像文件从目标设备拷贝过来；
> 	3）启动第1步中停止的服务。
> 注：1、VEMSBu服务在管理端与服务端安装到同一台机器上才会有。
> 2、如果镜像被设置成了重启不还原，则需要将镜像与客户机回写数据同时备份与恢复，否则会造成数据不一致的情况。
