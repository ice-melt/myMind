错误：psql: FATAL: Peer authentication failed for user "postgres"

解决办法如下:

1）. 运行下面的命令编辑pg_hba.conf文件 sudo vim /etc/postgresql/9.1/main/pg_hba.conf

2）. 将

 # Database administrative login by Unix domain socket

local     all      postgres        peer

改为 

# Database administrative login by Unix domain socket

local     all     postgres         trust

3）. 保存后执行下面的命令重新加载配置文件: sudo /etc/init.d/postgresql reload



导出

psql  -d  postgres  -f  coffeine.sql postgres

1.导出数据库：方式一：pg_dump  -U  postgres  -f  c:\db.sql postgres

                           方式二：pg_dump  -U postgres postgres> c:\db.sql

2.导入数据库：方式一：psql  -d postgres  -f  c:\db.sql  postgres

3.导出具体表：方式一：pg_dump -Upostgres -t mytable -f  dump.sql  postgres

4.导入具体表：方式一：psql  -d postgres  -f  c:\ dump.sql postgres