# 
## ubuntu重启、关机命令
#### 查看系统版本
```bash
# 1.
cat /proc/version
# 2.
lsb_release -a
```
#### 重启命令 ： 
1. reboot
2. shutdown -r now 立刻重启
3. shutdown -r 10 过10分钟自动重启
4. shutdown -r 20:35 在时间为20:35时候重启

    如果是通过shutdown命令设置重启的话，可以用shutdown -c命令取消重启 

#### 关机命令 ： 
1. halt   立刻关机（一般加-p 关闭电源）
2. poweroff 立刻关机 
3. shutdown -h now 立刻关机
4. shutdown -h 10 10分钟后自动关机 

    如果是通过shutdown命令设置关机的话，可以用shutdown -c命令取消关机


#### ssh命令
```bash
ssh-keygen -t rsa
ssh-keygen -b 4096 -t rsa

ssh-copy-id user@server
ssh-copy-id -i ~/.ssh/id_rsa.pub user@server
```
#### 由于Ubuntu重启之后，ip很容易改变，可以用以下方式固定ip地址

1.设置ip地址
```bash
sudo vim /etc/network/interface

# The loopback network interface
auto lo
iface lo inet loopback

# The primary network interface
auto ens32
iface ens32 inet static
address 192.168.159.130
netmask 255.255.255.0
gateway 192.168.2.1
```

2.设置dns
```
sudo vim /etc/resolvconf/resolv.conf.d/base
nameserver 8.8.8.8
nameserver 8.8.4.4
```
3.刷新配置文件

`resolvconf -u`

4.重启网络服务

`/etc/init.d/networking restart`
