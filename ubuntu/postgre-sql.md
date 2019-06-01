# postgresql

## 安装
```bash
sudo apt-get install postgresql

# 系统会提示安装所需磁盘空间，输入"y"，安装程序会自动完成。 
# 安装完毕后，系统会创建一个数据库超级用户“postgres”, 
# 密码为空。这个用户既是不可登录的操作系统用户，也是数据库用户。

# You can now start the database server using:

/usr/lib/postgresql/10/bin/pg_ctl -D /var/lib/postgresql/10/main -l logfile start
```
  
2、切换到Linux的postgres用户下

sudo su postgres



```
sudo passwd -d postgres  # 清除原有 postgres 用户密码

sudo -u postgres passwd
sudo -u postgres psql


postgres=# ALTER USER postgres WITH PASSWORD 'yourpassword';  # 输入你的新密码，要和前面的密码一致，有；才会运行
ALTER ROLE
postgres=# \q  # 退出
```

3、登陆postgresql
psql postgres

你可以看到如下提示：


这个时候说明安装成功了，看到了登陆成功的界面。

只是安装成功还不够，还需要做一些配置，此时登陆的数据库用户（postgres）还没有密码，需要设置个密码，在当前界面做如下操作：

ALTER USER postgres with PASSWORD 'postgres'
就会把密码修改成postgres，然后退出postgresql
执行如下命令退出：

\q


第二步：配置Postgresql

接下来是配置postgresql

由于目前为止，只能本机登陆到数据库，但实际情况是会选择远程登录，所以需要做如下配置：

打开vim /etc/postgresql/9.1/main/postgresql.conf

1、监听任何地址访问，修改连接权限

`#listen_addresses = ‘localhost’改为 listen_addresses = ‘*’`
2、启用密码验证
`#password_encryption = on 改为 password_encryption = on`

打开vim /etc/postgresql/9.1/main/pg_hba.conf，并在文档末尾加上以下内容

3、可访问的用户ip段
```
# to allow your client visiting postgresql server
  host all all 0.0.0.0 0.0.0.0 md5
```

也可以是如下格式：
 host all all 0.0.0.0/0 md5  #0.0.0.0为地址段，0为多少二进制位

例如：192.168.0.0/16代表192.168.0.1-192.168.255.254


4、重启PostgreSQL数据库
sudo service postgres restart

5、本地登录数据库
psql -U postgres -h 127.0.0.1

6、远程登录
psql -U postgres -h 172.16.155.158

显示如下界面：


我本机的postgresql的版本是9.3.9，Ubuntu的是9.1.20，登录成功。



第三步：安装pgAdmin3



1、键入如下命令安装pgAdmin3

sudo apt-get install pgadmin3


2、键入如下命令运行pgAdmin3
pgadmin3




# postgre数据库

## 导入导出


1.导出数据库：方式一：pg_dump  -U  postgres  -f  c:\db.sql postgres

            方式二：pg_dump  -U postgres postgres> c:\db.sql

2.导入数据库：方式一：psql  -d postgres  -f  c:\db.sql  postgres

3.导出具体表：方式一：pg_dump -Upostgres -t mytable -f  dump.sql  postgres

4.导入具体表：方式一：psql  -d postgres  -f  c:\ dump.sql postgres


#### 导出成csv
```bash
psql --dbname=postgres --host=127.0.0.1 --username=postgres -c"COPY (select * from caffeine_info order by product_id)TO STDOUT with csv header" > /home/ice-melt/disk/document/caffeeine_info_20190530.csv
```
#### 从csv导入
```bash
COPY products FROM '/path/to/input.csv' WITH csv
```

## 常见错误
1. `psql: FATAL: Peer authentication failed for user "postgres"`

解决办法如下:
```bash
# 1）. 
sudo vim /etc/postgresql/{xx}/main/pg_hba.conf

将
{
# Database administrative login by Unix domain socket
local     all      postgres        peer
} 改为 
{
# Database administrative login by Unix domain socket
local     all     postgres         trust
}
# 2）. 保存后执行下面的命令重新加载配置文件: 
sudo /etc/init.d/postgresql reload
```
