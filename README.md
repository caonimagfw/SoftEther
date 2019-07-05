
### 1、安装依懒软件
[root@localhost ~]# yum -y install gcc zlib-devel openssl-devel readline-devel ncurses-devel

### 2、下载SoftEther VPN安装包
[root@localhost ~]# wget  http://softether.fishinfo.cn/files/softether/v4.27-9666-beta-2018.04.21-tree/Linux/SoftEther_VPN_Server/64bit_-_Intel_x64_or_AMD64/softether-vpnserver-v4.27-9666-beta-2018.04.21-linux-x64-64bit.tar.gz 

### 3、安装vpn
    
[root@localhost opt]# tar xf softether-vpnserver-v4.27-9666-beta-2018.04.21-linux-x64-64bit.tar_2.gz
[root@localhost ~]# cd vpnserver
[root@localhost vpnserver]# make

    
    
     
Do you want to read the License Agreement for this software ?

 1. Yes
 2. No

Please choose one of above number:
 1            #选择1

Did you read and understand the License Agreement ?
 (If you couldn't read above text, Please read 'ReadMeFirst_License.txt'
 file with any text editor.)

 1. Yes
 2. No

Please choose one of above number:
 1           #选择1

Did you agree the License Agreement ?

 1. Agree
 2. Do Not Agree

Please choose one of above number:
 1          #选择1

make[1]: Leaving directory `/opt/vpnserver'

### 4、启动服务
[root@localhost vpnserver]# ./vpnserver start
[root@localhost vpnserver]# echo "/opt/vpnserver start" >> /etc/rc.local

### 5、配置vpn server
进入管理
[root@localhost vpnserver]# ./vpncmd

通过使用 vpncmd 程序，可以取得以下成果。

 1. VPN Server 或 VPN Bridge 的管理。
 2. VPN Client 的管理。
 3. 使用 VPN 工具 (证书创建和网络传输速度测试工具)

选择 1, 2 或 3: 1        #选择1

指定的主机名或目标 VPN Server 或 VPN Bridge 正在 运行的计算机 IP 地址。
 通过以 "主机名:端口号" 格式指定，您还可以指定端口号。
 (当没有指定端口号时，使用 443。)
 如果不输入任何内容并按下回车键，将连接到端口号为 443 的本地主机 (这台电脑)。
 目标 IP 地址的主机名:        回车键

如果通过虚拟 HUB 管理模式连接到服务器，请输入虚拟 HUB 的名称。
 如果通过服务器管理模式连接，无须输入任何内容请按回车键。
 指定虚拟 HUB 名称:           回车键

设置VPN管理员密码
VPN Server>serverpasswordse

ServerPasswordSet 命令 - 设置 VPN Server 管理员密码
 请输入密码。要取消，请按下 Ctrl + D 键。

密码 : ******
 确认输入: ******

创建虚拟HUB
VPN Server>hubcreate jiti       #名称自定义
VPN Server>exit

### 6、在windows下使用vpnsmgr管理vpn服务器


点击新设置



设置名可以随意填写，主机名为VPN服务器地址，端口号默认443端口，选择“虚拟HUB管理模式”，选择一个虚拟HUB 名jiti，管理的密码，点击确定即可。



管理界面点击连接



管理虚拟HUB



在管理虚拟HUB 中选择“管理用户”，“新建”—创建新用户，输入用户名，密码，确定




开启NAT地址转换和DHCP服务



##7、使用VPN client 连接


新建vpn连接和虚拟网卡



设置名称，主机名，HUB，用户名，密码


双击连接vpn


查看、测试
