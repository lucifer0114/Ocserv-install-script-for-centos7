# Ocserv-install-script-for-centos7
Thanks
将其中 ocserv_version=”0.10.8″ 这一行的版本号改成 你想要的版本，据说0.10.8此版本较稳定。
vi ocserv-install-script-for-centos7.sh
修改后保存，然后运行脚本。
sh ocserv-install-script-for-centos7.sh
安装过程中会提示你输入端口、用户名和密码等，自己按需填写。 安装完成后可编辑配置文件，添加用户或者删除用户等待操作。
配置目录：

/usr/local/etc/ocserv/ocserv.conf

相关参数命令：

1.添加用户

ocpasswd -c /usr/local/etc/ocserv/ocpasswd username(username是要添加的用户名)

2.删除用户

编辑在/usr/local/etc/ocserv目录下名为“ocpasswd”的文件，可以看到
username:*:********************************
找到你要删除的用户名，删除那一行就ok.

特别说明：在修改路由或者相关参数配置文件时，需要重新启动服务才能生效。
为了实现全局路由，亲注释掉route。如#route = *.*.*.*/*.*.*.*(即安全路由为0.0.0.0/0)

3.启动：
systemctl start ocserv.service

4.停止：
systemctl stop ocserv.service

5.重启：
systemctl restart ocserv.service

6.状态：
systemctl status ocserv.service

