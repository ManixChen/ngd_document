<blockquote class="success">
三层交换机DHCP Relay配置
</blockquote> 

>说明：实际环境中大多数网络存在Vlan，而DHCP本身是无法跨Vlan，所以需要三层交换机来配置DHCP 中继转发，从而实现DHCP跨Vlan；
>


 </br>
 </br>

<blockquote class="success">
场景
</blockquote> 

> 注：本场景以H3C S5500 系列三层交换机来进行实例配置，其他品牌（如锐捷、思科等）交换机请详细参考配置说明文档或与官方联系；
> 

|序号|操作|操作|
|---|---|---|
|服务器|	分配Vlan 100 机器连接端口：E0/2|vlan IP地址：192.168.100.254|
|客户机A|分配Vlan 10 机器连接端口：E0/1| vlan IP地址：192.168.10.254|
|客户机B|分配Vlan 20 机器连接端口：E0/2| vlan IP地址：192.168.20.254|
|交换机：|IP地址 192.168.100.253-| 



<blockquote class="success">
操作步骤
</blockquote> 

|序号|操作|
|---|---|
|1）|	在与交换机连通的任意机器上用命令行执行”telnet 192.168.100.253”命令登录交换机；|
|2）|	输入用户密码后执行”system-view”命令进入系统配置视图；|
|3）|	开启全局DHCP功能（缺省状态下该功能关闭）；[switchA]dhcp enable|
|4）|	进行vlan100的创建并进入；[switchA]vlan 100|
|5）|	将端口E0/24加入vlan100；加入完毕后退出；[switchA]port GigabitEthernet 0/24|
|6）|	进入vlan100接口  [switchA] interface vlan-interface 100|
|7）|	创建vlan100 IP地址并退出 [switchA] ip address 192.168.100.254 255.255.255.0[switchA]quit|
|8）|	进行vlan10的创建并进入；[switchA] vlan 10|
|9）|	将端口E0/1加入vlan10；加入完毕后退出；[switchA] port GigabitEthernet 0/1|
|10）|进入vlan 10 接口    [switchA] interface vlan-interface 10|
|11）|创建vlan 10 IP地址并退出  [switchA] ip address 192.168.10.254 255.255.255.0 [switchA]quit| |
|12）|进行vlan20的创建并进入；[switchA] vlan 20|
|13）|将端口E0/2加入vlan20；加入完毕后退出； [switchA] port GigabitEthernet 0/2|
|14）|进入vlan 10 接口    [switchA] interface vlan-interface 20|
|15）|创建vlan 10 IP地址并退出 [switchA] ip address 192.168.20.254 255.255.255.0  [switchA]quit|
|16）|新建dhcp 服务器组并添加服务器IP地址 [switchA]dhcp-server 1 ip 192.168.100.253|
|17）|进入vlan 10 接口开启中继模式并指定dhcp服务器  [switchA]interface vlan-interface 10  [switchA]dhcp select relay [switchA]dhcp relay server-select 1 |
|18）|进入vlan 20 接口开启中继模式 并指定dhcp服务器 [switchA] interface vlan-interface 20  [switchA]dhcp select relay   [switchA]dhcp relay server-select 1|
|19）|配置完毕后退出并执行save保存配置|



<blockquote class="success">
配置完毕后，在vlan 100中的服务器即能收到来自vlan 10和vlan 20中的dhcp请求；即完成在三层环境下和信下一代云桌面系统的通信；
</blockquote> 