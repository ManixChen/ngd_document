<blockquote class="info">
	VENGD Server端安装(Linux平台)
</blockquote> 

* * * * *

| 操作  |   须知 |
| --- | --- |
|1、全新安装环境，在解压安装包后，打开终端界面  |1)、定位到安装目录下，输入chmod a+x install.sh给脚本设置权限，<br>2)、接着输入脚本安装命令，运行脚本：sudo ./install.sh，脚本会自动下载安装下列依赖包apache2,php5,php5-mysql,mysql-server,phpmyadmin。 |
| 注意: | 安装过程中需正确配置MySQL密码，端口等相关设置，并正确配置服务端相关配置，按Y完成安装过程。如下图所示：|
|  | ![](../images/serverlinuxip.jpg =350x)|
| 2、  | 升级安装直接运行安装命令：sudo ./VEMSSetup –i，同样完成正确的服务端配置即可，同样需要先给VEMSSetup文件设置权限：chmod a+x VEMSSetup。 | 
| 3、 |服务端安装完毕后，需先初始化数据库：sudo ./VEMSSetup –initdb, 同样需要先给VEMSSetup文件设置权限：chmod a+x VEMSSetup。<blockquote class="warning">centos7上不用使用此命令升级数据库，终端登录数据库执行:<br>1)mysql -uroot -p123456  登录musql<br>2)source  ./vesystem.sql;</blockquote> |
| 4、mysql配置 |配置MySQL，服务端安装完成后需对mysql进行相关配置，系统才能正常连接到数据库。<br>1.	mysql默认只绑定127.0.0.1，可以在[/etc/mysql/my.cnf]文件中注释[bind]以使绑定所有IP。<br>2.	mysql默认只允许localhost登录，在mysql命令行中执行以下指令可允许所有主机使用root登录：<br>3、mysql>$mysql -uroot -p<br>4、mysql>GRANT ALL PRIVILEGES ON *.* TO 'root1'@'%' IDENTIFIED BY '123456' WITH GRANT OPTION;<br>5、mysql>flush privileges;  <br><blockquote class="warning">完成MySQL配置后，即可正常连接到系统管理端，进行系统配置。</blockquote> |
| 注： | <blockquote class="danger">系统对服务端在安装过程中所有集群名称一样的服务器自动加入到同一集群网络并受VEMS管理端的统一管理，同一通讯密钥下的服务器集群受上级服务器统一管理，下级集群名称不能相同，否则系统不能正常运行。</blockquote>|
|  | | 


<blockquote class="warning">
	注：Linux服务端与管理端集成在同一安装包内，可以在安装过程中选择是否安装管理端！
</blockquote> 