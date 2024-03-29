## 系统常见环境变量总结：

> PS1   <!--修改命令提示符信息-->
>
> LANG  <!--修改系统字符编码-->
>
> PATH  <!--定义命令文件所存储的路径信息-->







## 系统特殊符号信息：

> .   <!--文件名称前有点开头，便是隐藏文件-->
>
> ​    <!--可以表示匹配任意且只有一个字符-->
>
> ..  <!--上一级目录-->
>
> {..}   <!--生成序列信息-->
>
> ~    <!--表示家目录-->
>
> \-    <!--两个目录之间相互切换-->
>
> \*   <!--匹配符号，匹配任意字符信息-->
>
> \>   <!--标准输出重定向符号，作用：清空指定文件信息  echo xxx > 文件-->
>
> \>>   <!--标准追加输出重定向符号，作用：在文件中添加信息-->
>
> <    <!--标准输入重定向符号-->
>
> <<   <!--标准追加输入重定向符号-->
>
> $    <!--一行内容结尾定位符-->
>
> ^    <!--一行内容行首定位符-->
>
> \#    <!--在文件中表示注释信息-->
>
> \    <!--转义符号。将没有意义的字符变得有意义，将有意义的字符变得没意义-->
>
> \|    <!--管道符号，将前一个命令执行的结果交给后面的命令识别处理-->
>
> &&   <!--代表多个条件都要满足 或 代表前一个命令执行成功再执行后一个命令-->
>
> ||   <!--代表多个条件满足一个就行 或 代表前一个命令执行失败再执行后面的命令-->

## 常见通配符

> ​	*    匹配任意
>
> ​	?    匹配任意一个字符
>
> ​	[…]  匹配中括号中任意一个字符
>
> ​	[a-z]  匹配a-z之间任意一个字符
>
> ​	[!abc]/[\^a-c] 不匹配括号中的任意一个字符

## 特殊通配符

> ​	[[:upper:]]	所有大写字母
>
> ​	[[:lower:]]	所有小写字母
>
> ​	[[:alpha:]]	所有字母
>
> ​	[[:digit:]]	所有数字
>
> ​	[[:alnum:]]	所有字母和数字
>
> ​	[[:space:]]	所有的空白字符
>
> ​	[[:punct:]]	所有标点符号

## 特殊引号

> ​	单引号‘’ ：所见及所得，强引用，单引号中内容会原样输出
>
> ​	双引号“” ：弱引用，能够识别各种特殊符号、变量、转义符等，解析后再输出结果
>
> ​	反引号`` ：常用于引用命令结果，等同于$(命令)F
>
> ​		例：创建以当前时间命令的文件
>
> ​			touch \`date +%F`.txt
>
> ​		或
>
> ​			touch “\`date +%F`”.txt

## 01. ip-查看网络信息

> ​	ip address show         <!--查看系统网卡地址信息-->
>
> ​	ip address show ethxxx  <!--查看指定网卡信息-->
>
> ​	ip a s eth0	        <!--简写方式查看网卡信息-->



## 02\. nmtui-进入网卡信息修改界面



## 03\. systemctl-管理系统服务程序

> ​	systemctl start 服务程序名称    <!--启动服务-->
>
> ​	systemctl restart 服务程序名称  <!--重启服务-->
>
> ​	systemctl stop 服务程序名称     <!--停止服务-->
>
> ​	systemctl reload 服务程序名称   <!--重新加载配置文件-->
>
> ​	systemctl status 服务程序名称   <!--查看服务状态-->
>
> ​	systemcrl enable 服务程序名称   <!--开机自启-->
>
> ​	systemcrl enable 服务程序名称   <!--开机不自启-->
>
> ​		network：网卡服务名称
>
> ​		sshd：远程连接服务
>
> ​		fire

## 04\. shutdown-关闭或重启系统

> ​	shutdown -h  <!--延迟关机，默认延迟1分钟-->
>
> ​	shutdown -h 10  <!--言辞10分钟关机-->
>
> ​	shutdown -h now/0  <!--立即关机-->
>
> ​	shutdown -r  <!--延迟重启，默认延迟1分钟-->
>
> ​	shutdown -r 10  <!--延迟10分钟重启-->
>
> ​	shutdown -r now/0  <!--立即重启-->
>
> ​	shutdown -c  <!--取消关机或重启-->
>
> ​	关闭系统：
>
> ​		poweroff / init 0
>
> ​	重启系统：
>
> ​		reboot / init 6

## 05\. man-获取命令帮助信息

## 06\. help-获取内置命令帮助信息

## 07\. mkdir-创建系统目录

> ​	mkdir -p        <!--创建多级目录-->
>
> ​	mkdir {..}/{,}  <!--批量创建多个-->

## 08\. rmdir-删除空目录

## 09\. pwd-查看当前所在路径信息

## 10\. ls-列表显示目录中的数据信息

> ​	ll      <!--查看文件详细属性信息-->
>
> ​	ll -d   <!--查看目录详细属性信息-->
>
> ​	ll -rt  <!--按照时间排序显示数据信息-->
>
> ​	ll -rS  <!--按照大小排序显示数据信息-->
>
> ​	ll -h   <!--以 k M G 可读性显示信息-->
>
> ​	ll -a   <!--查看隐藏文件信息-->
>
> ​	ls -i   <!--显示文件inode信息-->



## 11\. tree-显示目录树形结构信息

> ​	tree -L 1 /etc  <!--显示指定层级目录下的结构信息-->
>
> ​	tree -d -L 1 /etc       <!--只显示指定目录下的目录结构信息-->

## 12\. touch-创建一个空文件

> ​	touch {1..10}.txt   <!--创建1到10的 .txt 文件-->

## 13\. echo-输出信息到屏幕上

> ​	echo xxx > 文件   <!--重定向编辑文件内容-->
>
> ​	echo xxx >> 文件  <!--追加重定向编辑文件内容-->

## 14\. cat-查看文件内容

> ​	cat -n 文件             <!--显示文件内容行号-->
>
> ​	cat -b 文件  <!--对非空行显示行号-->
>
> ​	cat -A 文件             <!--可以显示文件每行结尾空格信息-->
>
> ​	cat >> 文件信息 << EOF   ---编辑文件多行信息
>
> ​	xxx
>
> ​	xxx
>
> ​	EOF

## 15\. less/more-逐行查看文件内容



## 16\. head/tail-查看文件前几行/后几行内容

> ​	tail -f  <!--实时追踪查看日志信息-->
>
> ​	tail -F  <!--不断打开文件并监测-->
>
> ​	head/tail -n 20 文件  <!--显示文件前/后20行-->

## 17\. cp-复制文件

> ​	cp -r  <!--递归复制文件-->

## 18\. mv-移动/重命名文件

## 19\. rm-删除文件或目录

> ​	rm -f                  <!--强制删除文件数据信息-->
>
> ​	rm -rf	               <!--强制删除目录数据信息-->
>
> ​	rm \--no-preserve-root  <!--删除根目录信息-->

## 20\. hostname-查看主机名或临时设置主机名

## 21\. hostnamect-查看详细主机名称信息或永久设置主机名

> ​	hostnamectl set-hostname 主机名称   <!--设置主机名称-->

## 22\. wget-可以下载网站资源信息

## 23\. sz/rz-上传或下载数据

## 24\. timedatectl-查看修改系统时间

> ​	netdate   <!--同步调整时间-->
>
> ​	netdate 时间服务器域名地址   



## 25\. sed-修改调整文件内容

> ​	sed ‘s#修改前内容#修改后内容#g’ 文件  <!--显示写入内容后的文件信息-->
>
> ​	sed -i ‘s#修改前内容#修改后内容#g’ 文件  <!--将修改后内容真正写入到磁盘中-->

## 26\. mount-磁盘挂载

> ​	mount 设备文件 挂载点目录（空目录）
>
> ​	mount -a  #挂载/etc/fstab配置文件中的配置 

## 27\. umount-磁盘卸载

> ​	umount 挂载点目录
>
> ​	umount -l 挂载点    #强制卸载

## 28\. fdisk-查看磁盘信息与分区设置

> ​	fdisk -l  <!--查看系统磁盘与磁盘分区情况-->

## 29\. df–查看磁盘挂载和使用情况

> ​	df -h  <!--以可读方式显示磁盘容量大小-->
>
> ​	-T  <!--查看分区类型-->
>
> ​	-i  <!--查看磁盘inode号使用情况-->

## 30\. runlevel-查看系统当前使用级别

## 31\. init-切换系统运行级别

## 32\. grep-过滤筛选文件信息命令

> ​	-i  <!--忽略大小写-->
>
> ​	-E  <!--同时过滤多个信息-->
>
> ​	-r  <!--递归过滤-->
>
> ​	-A  <!--过滤指定行之后内容-->
>
> ​	-B  <!--过滤指定行之前内容-->
>
> ​	-C  <!--过滤指定行上下内容-->

## 33\. alias-设置别名信息

> ​	alias 别名=‘文件路径’  <!--设置别名-->
>
> ​	unalias 别名   <!--取消别名-->

## 34\. yum安装软件命令

> ​	yum install -y   <!--安装软件-->
>
> ​	yum erase        <!--卸载软件程序（将软件以及依赖包一并卸载）-->
>
> ​	yum provides     <!--检索命令文件属于哪个软件包-->
>
> ​	yum search       <!--检索命令文件属于哪个软件包-->
>
> ​	yum remove	 <!--卸载软件-->
>
> ​	yum reinstall    <!--重装软件-->

## 35\. rpm-安装软件程序命令

> ​	rpm -ivh 软件包名称   <!--安装软件  i:安装  v:可视化（可以看见安装过程）  h:百分比-->
>
> ​	rpm -ql 软件名称	      <!--查询软件安装路径-->
>
> ​	rpm -qa 软件名称 <!--查询软件是否已经安装-->
>
> ​	rpm -qf /etc/passwd   <!--查询某一个文件是由哪个软件产生的-->
>
> ​	rpm -e 软件名称        <!--卸载软件-->
>
> ​	rpm -e \--nodeps 软件名称  <!--忽略依赖关系卸载软件-->
>
> ​	rpm -qc 软件名称       <!--查询软件的配置文件-->

## 36\. file-识别文件类型

## 37\. which/whereis-识别命令文件所在绝对路径

> ​	which ls <!--查看命令存放在哪-->

## 38\. locate-定位查找指定文件路径信息

> ​	安装locate后需要更新数据库
>
> ​	updatedb <!--更新系统文件信息数据库-->

## 39\. find-根据路径范围以及条件信息查找数据

> find 从哪里开始找 参数（可以多个） 需要查找什么内容
>
> ​	find -iname      <!--根据名称查找数据，忽略大小写-->
>
> ​	find -type      <!--根据类型查找数据-->
>
> ​	find -mindepth  <!--根据目录层级查找数据，从哪个深度开始查找-->
>
> ​	find -mmin  -/+n    <!--根据分钟查找数据。 - 最近多少分钟之内  + 多少分钟之前-->
>
> ​	find !          <!--取反，将一些数据排除--> 
>
> ​	find -maxdepth  <!--根据目录层级查找数据，查找的最深深度-->
>
> ​	find -size +/-2k     <!--根据文件大小查找数据。 - 小于  + 大于 -->
>
> ​	find -mtime  -/+n   <!--根据修改时间查找数据。 - 最近多少天之内  + 多少天之前-->
>
> ​	find -atime  -/+n   <!--根据访问时间查找数据。 - 最近多少天之内  + 多少天之前-->
>
> ​	find -delete    <!--将找出的文件数据进行删除-->
>
> ​	find -exec      <!--将找出的文件数据进行批量处理-->
>
> ​	find -inum      <!--根据文件inode编号查找文件数据-->
>
> ​	find -perm      <!--根据文件权限查找数据-->
>
> ​	find . -path "./test_find/" -prune -o -name "test*" -print <!--查找"test"的时候忽略"./test_find/"这个文件夹 -->
>
> ​	find . -name "test*" -ok rm {} \; <!--将找出来的文件删除，-ok:问你是否删除 -->
>
> ​	find . -name "test*" -exec rm {} \; <!--将找出来的文件删除 -->
>
> ​	find /etc/ -size +20k -exec cp {} /opt/ \;   <!--将找出来的文件复制到其他目录-->

## 40\. du-查看目录中所有数据的容量总和(目录的大小)

> ​	du -sh /var  <!--查看目录汇总大小  s整个目录的大小  h 以可读方式显示-->

## 41\. tar-压缩解压命令

> ​    tar  参数  给压缩包起名  要压缩的内容
>
> ​	tar -zcvf  <!--打包压缩-->
>
> ​	tar -zxvf  <!--解压缩-->
>
> ​	-z： <!--采用gzip方式进行压缩打包数据或解压gzip打包的数据-->
>
> ​	-c： <!--创建一个压缩包文件-->
>
> ​	-v： <!--显示命令执行过程-->
>
> ​	-f： <!--识别压缩包信息以及路径信息-->
>
> ​	-x： <!--解压缩-->
>
> ​	-h   <!--压缩软连接文件的时候直接压缩软连接文件的源文件-->
>
> ​	-t   <!--显示压缩包里面的内容-->
>
> ​	-C： <!--指定解压到哪个目录-->
>
> ​	-P： <!--保存根目录-->
>
> ​	--exclude： <!--排除单个文件-->
>
> ​	--exclude-from： <!--排除多个文件-->

## 42\. stat-查看文件信息详细属性

## 43\. date-查看或修改时间

> date +%xxx    <!--修改时间输出格式-->
>
> date -d	      <!--显示过去或未来时间信息 -n 过去  +n 未来-->
>
> date -s	      <!--修改时间信息-->
>
> date +%F      <!--显示年月日-->
>
> date +%T      <!--显示时分秒-->
>
> date "+%Y-%m-%d %H:%M:%S"    <!--显示年月日和时分秒-->
>
> 
>
> date “+%Y-%m-%d %H:%M:%S”    #以方便看的方式 显示时间
>
> date +%s    #获取当前时间的时间戳
>
> date -d “2023-3-13 14:52:36” +%s   #获取指定时间的时间戳
>
> 时间加减算法：days(天)、year(年)、month(月)、hour(时)、min(分)、second(秒)
>
> ​	date “+%Y-%m-%d %H:%M:%S” --date ‘1 days/year/month/hour’   #加一天/年/月/小时
>
> ​	date “+%Y-%m-%d %H:%M:%S” --date ‘-1 days/year/month/hour’  #减一天/年/月/小时
>
> date -d “+%Y-%m-%d %H:%M:%S” --date ‘-10 min’ +%s  #显示当前时间减去10分钟的时间戳



## 44\. xargs:

> 跟在管道符后面，将管道前面输出内容信息转换为参数信息 交给后面命令处理	
>
> ​	xargs -n  <!--限制每行输出的个数--> 
>
> ​	xargs -d  <!--指定分隔符分割，默认是空格-->
>
> ​	xargs -i  <!--用{}代替 传递的数据-->
>
> ​		例：将/opt下的所有.txt文本移动到test目录下
>
> ​		    find /opt -name “*.txt” |xargs -i mv {} /opt/test
>
> ​	xargs -I  <!--用字符串代替传递的数据-->
>
> ​		例：将test目录下的所有.txt文件移出来
>
> ​		    find . -name “*.txt” |xargs -I rth mv rth ./ 
>
> ​			find . -name “*.txt”<!--找出许哦有txt文件-->
>
> ​			xargs -I rth <!--将找出来的数据命名为rth-->
>
> ​			mv rth ./ <!--将rth（所有数据）移动到当前目录下-->

## 45\. ln-创建链接文件

> ​	ln 源文件 链接文件       <!--创建硬链接-->
>
> ​	ln -s 源文件 链接文件    <!--创建软连接-->

## 46\. chmod-修改权限

> ​	chmod u/g/o/a +/-/= r/w/x   <!--修改属主/属组/其他/所有用户权限-->
>
> ​	chmod 664    <!--以数字方式修改权限-->
>
> ​	chmod -R     <!--对目录本身以及目录下面的数据进行递归修改-->
>
> 3、Sticky Bit权限
> Sticky Bit (SBit) 当前只针对目录有效， 对文件没有效果。其对目录的作用是：
>  ■ 在 具 有 SBit 的目录下， 用户若在该目录下具有 w 及 x 权限 ， 则当用户在该目录下建立文件或目 录时， 只有文件拥有者与 root 才有权力删除。
> 
>
> 4、设置文件和目录的特殊权限
>
>         为文件或目录添加三种特殊权限同样可以通过chmod命令来实施,使用“u±s”、“g±s”、“o±t”的字符权限模 式分别用于添加和移除SUID、GUID、sticky权限。 
> 若使用数字形式的权限模式,可采用“nnnn”格式的四位八进制数字表示，其中：后面三位是一般权限的数 字表示，前面第一位则是特殊权限的标志数字：
>  0——表示不设置特殊权限 
>  1——表示只设置sticky 
>  2——表示只设置GUID权限 
>  3——表示只设置SGID和sticky权限 
>  4——表示只设置SUID权限 
>  5——表示只设置SUID和sticky权限 
>  6——表示只设置SUID和SGID 
>  7——表示同时设置SUID、GUID、sticky3种权限
> 原文链接：https://blog.csdn.net/txtxla/article/details/127659834

## 47\. chown-修改数据属主或属组信息

> ​    chown 新属主名字  要修改的文件  <!--修改文件属主的语法-->
>
> ​    chown :新属组名字  要修改的文件  <!--修改文件属组的语法-->
>
> ​    chown 新的属主:新属组名字  要修改的文件  <!--同时修改文件属主和属组的语法-->
>
> ​	-R  <!--递归修改文件的属主和属组-->
>
> ​		chown -R 新的属主:新属组名字 要修改的文件夹
>
> ​	chown xxx       <!--单独修改属主-->
>
> ​	chown .xxx      <!--单独修改属组-->
>
> ​	chown xxx.xxx   <!--同时修改属主和属组-->
>
> ​	chown -R user1.user1 /rth   <!--递归修改rth目录下的属主和属组-->F

## 48\. history-显示曾经执行过的命令

> ​	-c   <!--清除历史命令信息-->

## 49\. useradd-创建用户信息

> ​	-g ：  <!--指定用户属于哪个特定组（主要组）-->
>
> ​	-G ：  <!--指定用户属于其他哪个特定组（附属组）-->
>
> ​	-u ：  <!--指定用户编号信息（uid）-->
>
> ​	-c ：  <!--指定用户描述信息-->
>
> ​	-M ：  <!--表示不能创建家目录（虚拟用户）-->
>
>  	-s ：  <!--表示指定用户登录方式-->
>
> ​	     用户登录系统方式：
>
> ​		1、能登陆：/bin/bash
>
> ​		2、不能登录：/sbin/nologin
>
> 

## 50\. usermode-修改用户信息

> ​	-g ：  <!--修改用户属于哪个特定组（主要组）-->
>
> ​	-G ：  <!--修改用户属于其他哪个特定组（附属组）-->
>
> ​	-u ：  <!--修改用户编号信息（uid）-->
>
> ​	-c ：  <!--修改用户描述信息-->
>
>  	-s ：  <!--表示修改用户登录方式-->
>
> ​	     用户登录系统方式：
>
> ​		1、能登陆：/bin/bash
>
> ​		2、不能登录：/sbin/nologin
>
> 

## 51\. userdel-删除用户信息

> ​	userdel 用户       <!--删除用户，不删除用户的家目录，不彻底删除-->
>
> ​	userdel -r 用户    <!--删除用户连带删除用户家目录，彻底删除-->

## 52\. groupadd-创建用户组信息

> ​	groupadd -g   <!--创建组的时候指定gid数值-->

## 53\. groupdel-删除用户组信息

## 54\. passwd-设置用户密码

## 55\. \--stdin-免交互设置用户密码

> echo 123456 |passwd --stdin 用户

## 56\. id-查看用户uid gid 以及所属组信息

## 57\. w 查看当前登录系统用户信息

## 58\. ps 查看系统进程

> ​	-ef   <!--可以显示所有进程信息-->
>
> ​	ps -ef | grep “nginx”  <!--只查看nginx相关的进程-->

## 59\. kill/killall 杀进程命令

> ​	kill 进程号    
>
> ​	kill -1 进程号   <!--刷新进程服务-->  
>
> ​	kill -9 进程号   <!--强制杀进程-->
>
> ​	kill -0 进程号   <!--不发送关闭停止信号，但是会检测进程是否存在-->
>
> ​	killall 进程名   <!--杀掉该进程的所有进程-->

## 60\. crontab-计划任务

> ​	crontab -e    <!--创建计划任务-->
>
> ​	crontab -l    <!--查看计划任务-->
>
> ​	crontab -r    <!--删除计划任务-->

## 61\. du-查看文件大小

> ​	du -sh 文件  



## 62. netstat-查看端口

> ​	netstat -tunlp	
>
> ​	netstat -tunlp | grep “nginx”  <!--只查看nginx的端口-->



## 63. curl-向服务器传输数据或者获取来自服务器的数据 

> \#利用curl命令，发起HTTP网络请求，并且验证对方网络的信息
>
> ​	curl 网站
>
> \#查看淘宝网的web服务器信息，
>
> ​	curl -I https://www.taobao.com

## 64.vim

> \#命令模式下复制、粘贴、删除、撤销
>
> ​	yy  复制光标所在行
>
> ​	nyy 从光标位置开始，复制n行
>
> ​	p   粘贴
>
> ​	dd  删除光变所在行
>
> ​	D   删除光标当前位置到行尾的内容
>
> ​	u   撤销上一步操作
>
> \#快捷操作
>
> ​	o  在光标下一行进入编辑模式
>
> ​	O  在光标上一行进入编辑模式
>
> ​	A  在光标末尾进入编辑模式
>
> ​	zz 快速保存退出
>
> \#批量快捷操作
>
> ​    快捷删除
>
> ​	ctrl + v 进入视图块模式
>
> ​	上下左右选择要删除的内容
>
> ​	输入d ,删除选中内容
>
> ​    快捷插入
>
> ​	ctrl + v 进入视图块模式
>
> ​	上下左右选择要出入几行
>
> ​	输入大写的I ，进入编辑
>
> ​	编辑完内容后按两次esc
>
> \#替换指定内容
>
> ​	:%s/被替换的内容/要替换成什么/g <!--g表示全局，不加g表示只替换每行的第一个匹配的内容-->
>
> ​	:40,50s/被替换的内容/要替换成什么/g   <!--指定替换第40行到第50行的内容-->
>
> \#读取指定文件的内容到当前编辑的文本中
>
> ​	:r /etc/passwd(要读取的文件的路径)
>
> \#删除除了以什么开头的内容
>
> ​	:g!/^root/d  <!-- 删除除了以root开头的所有内容，g 全局。！取反。d 删除-->
>
> \#将文件另存为
>
> ​	:wq 文件路径加上文件名   

## 65.sort 排序

> ​	sort -n <!--从小到大-->
>
> ​	sort -n -r <!--从大到小-->
>
> ​	sort -u <!--去重排序-->
>
> ​	sort -n -t “.” -k 4 <!-- -n 从小到大。-t 指定分隔符， -k 指定位置--> 

## 66.uniq 去重（常和sort一起使用）

> ​	uniq 文件    <!--去除连续的重复行-->
>
> ​	sort -n 文件 | uniq   <!--结合sort更精准的去重-->
>
> ​	sort -n 文件 | uniq -c  <!--统计每一行重复的次数-->
>
> ​	sort -n 文件 | uniq -c -d <!--只输出重复的行，并统计重复的次数-->
>
> ​	sort -n 文件 | uniq -c -u <!--找出只出现过一次的行，必须跟上 -c -->

## 67.wc 统计文件的行数、单词、字节数

> ​	-l  打印行数
>
> ​	-w  打印单词数
>
> ​	-c  打印字节数
>
> ​	-m  打印字符数
>
> ​	-L  打印最长的行的长度(字符串长度)

## 68.tr 从标准输入中替换、删除字符

> 例：
>
> ​	echo “my name is rth” |tr ‘[a-z]’ ‘[A-Z]’  <!--将小写字母转为大写字母-->
>
> ​	echo “my name is rth” |tr -d ‘[a-m]’   <!-- -d 删除指定的字母-->
>
> ​	tr ‘a’ ‘A’ < 文件  <!--使用标准输入将文件里的a替换为A然后输出，实际文件内容是没变的-->
>
> ​	echo “iiii lllove aaaa” |tr -s ‘ila’ <!-- -s 给指定的字符去重-->

## 69.gzip/zip/unzipu压缩解压缩

> gzip无法直接压缩文件夹，需要先tar对文件夹打包后才能压缩，gzip压缩后后缀为.gz
>
> ​        gzip 文件   <!--压缩文件-->
>
> ​	gzip -d <!--解压缩-->
>
> zip 压缩文件名  要压缩的内容  <!--zip压缩文件-->
>
> unzip 压缩包 <!--解压zip压缩的文件-->

## 70.umask值

> 1. umask值存放在/etc/profile中。
> 2. linux默认设置创建文件的最大权限是666，创建文件夹的权限是777
> 3. 每次创建文件和文件夹的时候是使用文件的默认最高权限减去umask的值。
> 4. 普通用户和root用户的umask值是不一样的

## 71.chattr/lsattr 添加/删除/查看文件特殊权限

> chattr 参数 文件 <!--添加/删除特殊权限-->
>
> ​	+/-/= a <!--只能向文件使用追加重定向添加数据，不能删除-->
>
> ​	+/-/= i <!--文件不能被删除、改名、修改内容-->
>
> lsattr 文件  <!--查看文件特殊权限-->

## 72. lsblk 查看所有磁盘信息

## 73. free 查看内存和swap

> ​	free -m   <!--以兆为单位查看-->

## 74. watch实时监控命令执行情况

> ​	watch -n1 “df -hT”  <!--没隔1秒刷新一次df -hT 这个命令的执行结果-->

## 75. pvs 查看物理卷

## 76. vgs 查看卷组

## 77. uname 查看系统内核

> uname -a   <!--查看Linux系统内核和系统版本-->
>
> cat /proc/version  <!--查看Linux系统内核和系统版本-->

## 78. tee 将内容同时输出到多个文件

> 例：将当前时间输出到test1、test2文件中
>
> data |tee > test1 test2   <!--覆盖-->
>
> data |tee -a test1 test2   <!--追加-->

## 79.查看当前用户的用户名 

> whoami
>
> echo $USER

## 80. groups 查看用户属于哪个组

> groups 用户名

## 81. setfacl 设置文件策略规则

> 通过该技术可以更加精准的控制权限的分配，例如仅允许某个用户访问指定目录，或仅有某个用户才具有写入权限 原文链接：<https://www.linuxcool.com/setfacl> 
>
> setfacl -m u:用户名:权限  文件或目录   <!--设置指定用户对指定文件或目录拥有什么权限-->

## 82. getfacl 查看文件策略规则

> getfacl 文件/目录    <!--查看文件或目录的策略规则-->

## 83. vimdiff 比较两个文件的内容差异

## 84. seq 打印数字序列

> seq -w 10   #打印1到10 w：在前面添0使长度相同
>
> seq -s “ ” 1 10

## 85. blkid 查看磁盘UUID和格式化类型

## 86. top 实时显示系统中各个进程的资源占用情况

> ​	-d ：指定刷新时间间隔
>
> ​	-n ：指定刷新的次数，刷新次数完成后退出top命令
>
> ​	-p ：查看指定的进程信息
>
> ​	-u ：查看指定用户的进程
>
> ​	-c ：显示进程的整个命令路径，而不是只显示命令名称
>
> ​	-b ：批处理模式，不进行交互式显示。输出结果可以写入到文件中或者传递给其他程序
>
> top快捷键指令：
>
> ​	1 ：查看CPU核心总数
>
> ​	q ：退出
>
> ​	M ：按内存使用百分比排序
>
> ​	P ：按CPU使用百分比排序
>
> ​	x ：高亮显示排序的列
>
> ​	z ：以彩色显示
>
> ​	b ：高亮显示处于R状态的进程
>
> ​	>或< ：切换排序的列



## 87. ipset 创建IP集合

> ***ipset命令格式***
>
> ​	ipset [options] command [command-options]	
>
> options 参数有：-exist、-file、-output{plan/save/xml}、-quite、-resolve、-sorted、-name
> command 选项有：create、add、del、test、destroy、list、save、restore、flush、rename、
>
> 
>
> ***command选项介绍***:
>
> **n, create**：通过指定SETNAME和TYPENAME创建一个新IP集合。如果指定-exist选项，ipset在创建一个已经存在的IP集合时，ipset将不会报错。 
>
> ​	ipset create/n deny01 hash:ip
>
> **add/-A** ：添加一个条目到SETNAME指定的IP集合中。如果指定-exist选项，IP集合存在此条目时，ipset将不会报错。 
>
> ​	ipset add/-A deny01 192.168.1.3
>
> **del/-D** ：从SETNAME指定的IP集合中删除一个条目。如果指定-exist选项，IP集合不存在此条目时，ipset将不会报错。 
>
> ​	ipset del deny01 192.168.1.3
>
> **test/-T** ：测试一个条目是否在指定的IP集合中。如果在，ipset命令返回0，如果不在，则返回非0
>
> ​	ipset test deny01 192.168.1.3
>
> **destroy/x** ：销毁指定的IP集合，如果不指定，则销毁所有的IP集合。如果某一IP集合正在被引用，则ipset不对该IP集合做任何操作。
>
> ​	ipset destroy deny01
>
> **list/-L** ：查看IP集的头部信息和添加的条目。如果没有指定IP集，则是所有IP集。--sorted选项会把IP集合排序后输出。--output指定IP集合输出的格式： 
>
> ​	ipset list deny01
>
> **flush** ： 清空指定IP集，如果没有指定，则是所有的IP集。 
>
> ​	ipset flush deny01
>
> **rename** ：重命名IP集
>
> ​	ipset rename deny01 deny02
>
> **timeout** ：设置IP集合添加的新条目的默认超时时间，新加的条目的时间超过超时时间后，将从IP集中删除。
>
> ​	ipset create deny01 hash:ip timeout 300  //创建集合的时候设置
>
> ​	ipset add deny01 192.168.1.1 timeout 200 //添加条目的时候可以重新指定该条目的超时
>
> **save** ：保存指定的IP集，如果没有指定，则是所有的IP集。如果不指定-file则是输出到标准输出，指定则是输出到指定文件。 
>
> ​	ipset save deny01 -file /root/ipset.txt
>
> **restore** ：恢复保存的ipset配置
>
> ​	ipset restore -file /root/ipst.txt
>
> 【注】：ipset配置好后需要保存配置，不然重启会失效。将恢复的名命令写到/etc/rc.d/rc.local中并给该文件执行权限。可以实现重启后自动恢复配置
>
> ***将ipset 集挂在iptables封IP***
>
> ​	iptables -A INPUT -m set \--match-set deny01 src -j DROP



## 88. iptables

> \#添加规则
>
> ​	iptables -A INPUT -s 192.168.1.1 -j DROP
>
> \#删除规则
>
> ​	iptables -D INPUT -s 192.168.1.1 -j DROP
>
> \#查看规则
>
> ​	iptables -nL
>
> 【注】iptables配置后需要保存配置，不然重启后将失效。在开机自启动文件中添加还原iptables配置，使配置自动恢复
>
> ​	iptables-save > /etc/sysconfig/iptables   //保存配置
>
> ​	在/etc/rc.d/rc.local中添加恢复命令，并给/etc/rc.d/rc.local执行权限
>
> ​	iptables-restore < /etc/sysconfig/iptables   //恢复配置
>
>  

## 89. pgrep 查看进程PID

> ​	pgrep 进程名

## 90. nohup/& 讲命令（进程）放入后台

> ​	nohup 命令   //方法一
>
> ​	命令 &    //方法二，后台运行脚本常用&符

## 91. strace 跟踪进程的系统调用

> strace [参数] 进程（命令）
>
> ​	strece -p 	//指定进程pid 
>
> ​	strece -f 	//进程以及进程创建的子进程
>
> ​	strece -o filename  	//将输出保存到文件 
>
> ​	

## 92. ltrace 跟踪进程调用库函数

> ​	ltrece -p 	//指定进程pid 
>
> ​	ltrece -f 	//进程以及进程创建的子进程
>
> ​	ltrece -o filename  	//将输出保存到文件 

## 93. uptime/w 查看平均负载

> 需要关注负载的值：总的核心数*70%=关注的点

## 94. iostat 查看磁盘IO

## 95. dirname/basename 取路径/文件名

> dirname /etc/sysconfig/network-scripts/ifcfg-ens33  //取出路径
>
> basename /etc/sysconfig/network-scripts/ifcfg-ens33  //取出文件名