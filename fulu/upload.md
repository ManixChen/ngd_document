<blockquote class="success">
上传问题
</blockquote>   

|  步骤  | 问题   |
| --- | --- |
|   1、 |为什么上传前格式化虚拟盘，一直显示正在格式化？ |
|  |  <blockquote class="default">出现这个问题后从以下几个方面入手检查：</br>1，出现这个现象可能是网卡或网络问题，在保证网络正常的情况，请尝试在客户机网卡【属性】中【高级】设置里面的双工模式更改为“全双工”，或关闭“流控”等属性；大部分网卡需关闭的高级设置:Flow Control、Jumbo Frame、Offload Checksum、Offload TCP_LargeSemnd ；</br>2，检查服务端进程监控功能是否开启，如果开启请关闭或者把uploader.exe进程加入到白名单；</br>3，更换交换机进行测试；
</blockquote>|
| 2、 | 终端上传操作系统后，由虚拟系统启动时提示“因计算机磁盘硬件的配置问题，Windows无法启动”是什么原因？ |
|  |  <blockquote class="default">这个现象是因为windows的启动配置文件boot.ini出错引起的，将它改成如下格式即可：</br>[boot loader]</br>  timeout=3</br>default=multi(0)disk(0)rdisk(0)partition(1)/WINDOWS</br>[operating systems]</br>multi(0)disk(0)rdisk(0)partition(1)/WINDOWS="Microsoft Windows XP" /fastdetect /NoExecute=OptIn</blockquote>|
|  3、| 为什么在终端上传操作系统后，由虚拟系统启动时运行Office等软件时会提示“正在安装…”甚至无法使用？ |
|  |  <blockquote class="default">Office等常用软件在安装后会生成一些无法上传的文件，所以我们需要先上传操作系统，然后再安装常用软件。</blockquote>|
| 4、|  为什么用第一台INTEL机器上传后，第二台AMD机器网络启动后蓝屏       （0X00000007E）？ |
|  |  <blockquote class="default">这个现象的原因是INTEL和AMD的驱动不兼容，安装过INTEL的CPU驱动后， AMD启动会出现蓝屏现象，一般情况出现蓝屏代码为0X00000007E．解决方案：在 INTEL机器上开超级管理员找到注册表HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\services\intelppm相应的位置， 把START值改为“3”。</blockquote>|
|5、  |为什么上传WIN7系统后，普通用户能进虚拟系统，超级管理员用户一直停在WIN7启动画面？  |
|  |  <blockquote class="default">请检查终端机器的网卡是否为Athreos系列的，如果是请在服务端网卡PNP管理里面把相关的网卡属性(硬件校验和、巨型帧、流控制等等)关闭。</blockquote>|
|  6、|为什么终端按正常流程设置了硬盘启动模式和超级管理员模式，进去本地系统后，通过客户端上传器无法上传，也无法对虚拟盘进行格式化？  |
|  |  <blockquote class="default">检查虚拟盘是否为活动分区，如果不是请手动激活即可。</blockquote>|
| 7、 |为什么客户机安装客户端准备上传，在服务端设置该机器为硬盘启动模式和超级管理员模式，PXE启动编号后终端在获取IP地址之后出现”Load Nbp Real disk...”提示，进入系统终端显示普通用户且虚拟盘也无法正常出盘？   |
|  |  <blockquote class="default">检查终端之前是否己缓存过虚拟系统，如果有请恢复MBR即可。出现该情况是因为终端通过PXE启动后实际是通过本地VBS引导启动，使用的是以前保存在本地的配置信息，所以会出现获取不了当前的虚拟盘和超级管理员信息。</blockquote>|
|  |  |