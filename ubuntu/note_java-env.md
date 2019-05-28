

#### 安装java
	sudo apt install software-properties-common -y

	sudo add-apt-repository ppa:webupd8team/java

	sudo apt install oracle-java8-installer -y

安装完成后，检查系统上安装的Java版本。 

	java -version

#### 配置Java环境 

在配置JAVA_HOME环境之前，我们需要知道Java目录的位置。 用下面的命令检查Java目录的位置： 

	sudo update-alternatives --config java

结果如下：

	ice-melt@Y430P:~$ sudo update-alternatives --config java
	There is 1 choice for the alternative java (providing /usr/bin/java).

	  Selection    Path                                     Priority   Status
	------------------------------------------------------------
	  0            /usr/lib/jvm/java-8-oracle/jre/bin/java   1081      auto mode
	* 1            /usr/lib/jvm/java-8-oracle/jre/bin/java   1081      manual mode

	Press <enter> to keep the current choice[*], or type selection number: 


java目录是**/usr/lib/jvm/java-8-oracle/jre**

现在使用vim编辑'**/etc/environment**'文件。

	vim /etc/environment

在那里粘贴以下配置。

	JAVA_HOME="/usr/lib/jvm/java-8-oracle/jre"

保存并退出。

编辑'〜/ .bashrc'文件。

	vim ~/.bashrc

粘贴下面的配置。

	export JAVA_HOME=/usr/lib/jvm/java-8-oracle/jre
	export PATH=$JAVA_HOME/bin:$PATH

保存并退出。

现在重新加载'〜/ .bashrc'脚本并测试'JAVA_HOME'目录。

	source ~/.bashrc
	echo $JAVA_HOME

Java环境设置已完成。
#### 安装Apache Tomcat

在这一步中，我们将在'tomcat'用户和组下安装Apache Tomcat。 我们将下载apache tomcat二进制文件，配置Catalina tomcat servlet容器环境，并对Tomcat服务器进行第一次测试。

使用以下命令添加名为'tomcat'的新用户和组。

	groupadd tomcat
	useradd -s /bin/false -g tomcat -d /opt/tomcat tomcat

现在转到'/opt/'目录并使用wget命令下载最新的apache tomcat稳定版本（9.0.12）。

	cd /opt/
	wget http://www-eu.apache.org/dist/tomcat/tomcat-9/v9.0.12/bin/apache-tomcat-9.0.12.tar.gz

解压apache tomcat包文件并将目录重命名为'tomcat'。

	tar -xzvf apache-tomcat-9.0.12.tar.gz
	mv apache-tomcat-9.0.12/ tomcat/

将tomcat目录和文件的所有者更改为'tomcat'用户和组，然后使所有apache tomcat二进制文件可执行。

	chown -R tomcat:tomcat /opt/tomcat
	chmod +x /opt/tomcat/bin/*

接下来，我们将通过使用vim编辑'〜/ .bashrc'文件来配置Catalina tomcat servlet容器环境。

vim ~/.bashrc

在那里粘贴以下配置。

export CATALINA_HOME=/opt/tomcat

保存并退出。

重新加载'〜/ .bashrc'文件并测试Catalina环境。

source ~/.bashrc
echo $CATALINA_HOME

您将得到如下所示的结果。

设置Tomcat

现在测试运行Apache Tomcat本身。

运行下面的命令启动Apache tomcat。

$CATALINA_HOME/bin/startup.sh

你会看到结果 - apache tomcat已经启动。 它将在默认端口'8080'上运行 - 您可以使用netstat命令检查端口。

netstat -plntu

Apache Tomcat正在端口8080下运行服务器。

安装并启动Apache Tomcat

测试apache tomcat的另一种方法是使用端口8080访问服务器IP地址。

http://192.168.10.100:8080/

你会看到下面的apache tomcat主页。

Tomcat开始了

Apache Tomcat已经安装在Ubuntu 18.04上。

现在运行下面的命令停止apache tomcat。

$CATALINA_HOME/bin/shutdown.sh
chown -hR tomcat:tomcat /opt/tomcat/

停止Tomcat服务器
第4步 - 将Apache Tomcat配置为服务

在本教程中，我们希望以tomcat用户身份运行Apache Tomcat并使用systemd服务文件，以便轻松启动和停止它。 现在我们需要创建'apache-tomcat.service'文件。

转到systemd系统目录并创建一个新文件'apache-tomcat.service'。

cd /etc/systemd/system/
vim apache-tomcat.service

在那里粘贴以下配置：

[Unit]
Description=Apache Tomcat 9 Servlet Container
After=syslog.target network.target

[Service]
User=tomcat
Group=tomcat
Type=forking
Environment=CATALINA_PID=/opt/tomcat/tomcat.pid
Environment=CATALINA_HOME=/opt/tomcat
Environment=CATALINA_BASE=/opt/tomcat
ExecStart=/opt/tomcat/bin/startup.sh
ExecStop=/opt/tomcat/bin/shutdown.sh
Restart=on-failure

[Install]
WantedBy=multi-user.target

保存并退出。

现在重新加载systemd服务。

systemctl daemon-reload

并使用下面的systemctl命令启动'apache-tomcat'服务。

systemctl start apache-tomcat
systemctl enable apache-tomcat

将Apache Tomcat配置为服务

Apache Tomcat现在作为Ubuntu 18.04上的服务运行，请使用以下命令对其进行检查。

netstat -plntu
systemctl status apache-tomcat

检查Tomcat服务

Apache Tomcat现在正在运行，它将8080端口用作默认端口。
第5步 - 配置Apache Tomcat用户

在这一步中，我们将为Apache Tomcat配置用户。 我们将添加一个新用户来访问管理器用户界面，然后允许管理员和主机管理员访问。

转到'/ opt / tomcat / conf'目录并使用vim编辑'tomcat-users.xml'文件。

cd /opt/tomcat/conf
vim tomcat-users.xml

在关闭配置' </ tomcat-users> '之前粘贴以下配置。

<role rolename="manager-gui"/>
<user username="hakase" password="hakasepassword01" roles="manager-gui,admin-gui"/>

保存并退出。

配置Apache Tomcat用户

现在通过编辑配置'context.xml'文件允许外部访问'manager'仪表板。

cd /opt/tomcat/webapps/manager/META-INF/
vim context.xml

评论'允许'第19-20行。

<!--  <Valve className="org.apache.catalina.valves.RemoteAddrValve"
         allow="127\.\d+\.\d+\.\d+|::1|0:0:0:0:0:0:0:1" /> -->

保存并退出。

在外部网络接口上配置Tomcat

并为'主管经理'。

cd /opt/tomcat/webapps/host-manager/META-INF/
vim context.xml

评论'允许'第19-20行。

<!--  <Valve className="org.apache.catalina.valves.RemoteAddrValve"
         allow="127\.\d+\.\d+\.\d+|::1|0:0:0:0:0:0:0:1" /> -->

保存并退出。

注释掉org.apache.catalina.valves.RemoteAddrValve

使用systemctl命令重新启动Apache Tomcat服务。

systemctl restart apache-tomcat

apache tomcat用户配置，管理器和主机管理器配置已完成。
第6步 - 测试

打开您的网页浏览器并使用端口8080输入您的服务器IP。您将看到Apache Tomcat主页。

http://192.168.10.100:8080/

Apache Tomcat作为服务运行

使用以下网址转到管理员信息中心：

http://192.168.10.100:8080/manager/html

在第5步中输入密码为“hakasepassword01”的管理员用户名'hakase'。

Apache Tomcat应用程序管理器

现在通过以下网址转到主机管理器仪表板：

http://192.168.10.100:8080/host-manager/html

从第5步输入管理员用户和密码，您将看到Tomcat虚拟主机管理器。

Apache Tomcat虚拟主机管理器

Apache Tomcat 9.0.8已成功安装在Ubuntu 18.04 Bionic Beaver上。
参考

    http://tomcat.apache.org/ 

Tag标签： server ubuntu linux

上一篇

如何在Ubuntu 18.04 LTS上安装Trac项目管理工具

下一篇

如何在Ubuntu 18.04上安装Anaconda Python发行版

文章分类 10
运维
架构
开发工具
操作系统
编程语言
WEB开发设计
服务器
数据库
网络安全
综合分类
热门文章8

    MySQL中的查询简介
    PostgreSQL中的查询简介
    如何在Linux中使用Git版本控制系统[综合指南]
    如何列出Apache Web Server中的所有虚拟主机
    在CentOS 7上安装Plex Media Server
    Zulip - 群聊或团队聊天最具生产力的聊天应用程序
    如何在Nginx中启用和监视PHP-FPM状态
    4个在多个Linux服务器上运行命令的有用工具


Linux入门

QQ交流群:308781113
