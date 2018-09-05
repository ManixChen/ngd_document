<blockquote class="success">
	1、 多硬件配置常见问题
</blockquote>  

|  步骤  | 现象   |
| --- | --- |
|   1、 |WIN7系统上传后用工具激活，做多硬件配置无效    |
|  |  解决方法</br><blockquote class="info"> WEB版以及二合一版请在系统上传前使用我们提供的专用激活工具；标准版请在系统上传后用专用工具激活 </blockquote>    |
|   2、 | 在管理员模式下保存了一个硬件配置，切换普通用户后把终端加入到新保存的硬件配置中，开机会提示“BOOTMGR is missing”   |
|  原因  |出现该问题是因为当前终端不是最新状态，可从以下几个方面解决</br> <blockquote class="info"> 1） 把终端先加入到默认硬件配置中，进入系统后让终端更新到最新状态</br>2)   把全局配置中的镜像变更后启动模式改成“网络镜像优先”即可</blockquote></br>|
|  ---  |-----   |
|  3、  |不同型号的硬件配置加入到同一种硬件配置策略中后，安装好其中一台硬件驱动，再安装另一台硬件驱动后，之前一台终端更新后出现蓝屏或进不去的情况   |
|    |   出现该问题一般情况可能是由于两种硬件配置驱动不兼容。</br> 解决办法：</br><blockquote class="info"> 把进不去的终端加入到默认硬件配置中，重新保存一个硬件配置策略 </blockquote>| 



</br></br>
<blockquote class="success">
	2、显卡PNP问题
</blockquote> 
<blockquote class="info"> </blockquote>

|  步骤  | 现象   |
| --- | --- |
|   1、 |为什么用INTEL G31显卡的机器上传安装好显卡驱动后，把INTEL HD显卡的机器加入到此系统中安装好显卡驱动后出现感叹号  |
|   |此现象属于显卡驱动冲突才会出现，原因是他们驱动文件名和注册表名相同。可使用显卡PNP功能解决  |
| 2、  |  为什么终端用显卡PNP功能把显卡驱动驱起来后，重启后为感叹号|
|   |出现这个问题后从以下几个方面入手检查：</br><blockquote class="info">1、如果终端使用的机器是笔记本，请检查该笔记本是否为双显卡且系统是否为WINXP，如果是很有可能是因为该笔记本不支持WINXP。</br>2、请检查选择的驱动是否和当前显卡匹配。建议使用官方提供的驱动，第三方驱动可能带来未知问题。</blockquote>  |
|   |  |
|   |  |


</br></br>
<blockquote class="success">
	3、个性化迁移问题
</blockquote> 


|  步骤  | 现象   | 
| --- | --- |
| 1、  | 为什么本地硬盘有分区的情况，做SAM迁移、文件以及注册等个性化迁移到本地硬盘不还原分区上后,都无法正常使用 |
|   |  <blockquote class="info">请检查服务端控制台是否开启磁盘保护功能 </blockquote>|
| 2、  | 为什么做过个性化迁移后，进入虚拟终端系统桌面无法访问“XXXXX桌面。系统无法辨别文件名 |
|   |<blockquote class="info">请检查之前是否做过迁移，如果有请手动删除之前的迁移目录后再做迁移。</blockquote>  |
|   |  |
|   |  |