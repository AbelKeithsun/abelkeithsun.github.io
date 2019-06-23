
## centos
### linux 的字母权限
r	100		读权限 		4
w	010		写权限		2
x	001		执行权限		1

分析日常权限表示

rwxrwxrwx	777

前三位表示用户（文件所有者）的权限
中间三位表示 Group 用户的权限
最后三位表示 Other

chown 

mv ./old_name ./new_name


检测那个软件包包含ping命令
yum provides "*/ping"
安装软件
yum install [softName]

安装x-window
yum groupinstall 'X Window System' -y
卸载x-window
yum groupremove "X Window System"


查看已安装软件
yum grouplist

列出所有可能安装的软件包
yum list

安装企业拓展包
sudo yum install epel-release

### centos7 网络文件配置

1. 在 nat 网络模式下，进入/etc/sysconfig/network-scripts目录，找到该接口的配置文件（ifcfg-enp0s3）；
2. 其中有 onboot=no 改成 yes 即为开启驱动
```
cd /etc/sysconfig/network-scripts
vim ifcfg-enp0s3
```

### 安装语言包

1.  yum groupinstall "fonts"

2.  最后进入  etc/locale  文件,将其中LANG=en_CN.UTF8改为 LANG=zh_CN.UTF8; 保存退出.

### 更改语系

1. 使用命令 locale -a 查看是否有将要切换的语系

2. 使用LANG=zh_CN.utf8 更改配置

3. 使用 export LC_ALL=zh_CN.utf8 将配置持久化

## vim 命令

[n] dd ：删除（剪切）（n）行

### 查看 ip 配置信息
ifconfig -a


### 查看 ssh 服务是否启动
netstat -anp|grep :22

### 更改时区
1. timedatectl 查看时间的各种状态
2. timedatectl list-timezones   列出所有时区
3. timedatectl set-local-rtc 1  将硬件时钟调整为与本地时钟一致，0为设置 UTC 时间
4. yum install ntp 安装时间校准软件
5. ntpdate us.pool.ntp.org  更新时间


### 查看 Linux 配置
 uname -a # 查看内核/操作系统/CPU信息
 
### centos 安装 vsftp服务

* 查看是否有端口占用
```
netstat -an |grep 21
```
* 修改 ftpuser 和 user_list 中的信息


### 打开特定的防火墙端口

```
firewall-cmd --zone=public --add-port=20/tcp --permanent
firewall-cmd --zone=public --add-port=21/tcp --permanent
```

### 赋权语句


-----------------

## ubuntu
