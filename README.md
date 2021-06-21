# smartdnsprocd
OpenWrt上Smartdns的自动守护进程，监控smartdns运行状态，在崩溃时自动重启。  

使用方法：  
将smartdnsprocd文件放到 /etc/init.d 目录下执行 chmod 755 /etc/init.d/smartdnsprocd 赋予权限  
开机自启 service smartdnsprocd enable  
开始监控 service smartdnsprocd start  
停止监控 service smartdnsprocd stop  
  
查看效果：  
执行 pgrep smartdns 查看smartdns的进程号  
执行 kill -s 9 进程号 杀死进程，此时再快速执行 pgrep smartdns 应该不会有smartdns进程号出现  
等待几秒后执行 pgrep smartdns 发现smartdns以新的进程号启动成功  

service smartdns stop 并不会让Smartdns守护进程重启Smartdns
