# 安装git

> 从官网下载安装包。一直默认回车即可
>
> 安装完成后，在开始菜单里找到“Git”->“Git Bash”，蹦出一个类似命令行窗口的东西，就说明Git安装成功！ 
>
> 安装完成后，还需要最后一步设置，在命令行输入： 
>
> ​	git config --global user.name "Your Name"
>
> ​	git config --global user.email "email@example.com"
>
> 

# 创建版本库

> mkdir  github   <!--创建一个空目录 -->
>
> cd  github    <!--进入目录-->
>
> pwd   <!--显示当前目录 -->
>
> git  init   <!--把这个目录变成Git可以管理的仓库 -->
>
> 把文件放在github目录下，然后就可以使用命令管理了

# 版本回退

> 在Git中，用`HEAD`表示当前版本，也就是最新的提交，上一个版本就是`HEAD^`，上上一个版本就是`HEAD^^`，当然往上100个版本写100个`^`比较容易数不过来，所以写成`HEAD~100`。 
>
> git reset \--hard HEAD^   <!--回退到上一个版本-->
>
> git reset \--hard 1093a(版本号)   <!--回到指定的版本-->
>
> 版本号没必要写全，前几位就可以了，Git会自动去找。当然也不能只写前一两位，因为Git可能会找到多个版本号，就无法确定是哪一个了。 
>
> 
>
> 当回退到了某个版本，关掉了电脑，第二天早上就后悔了，想恢复到新版本怎么办
>
> git reflog   <!--查看历史版本号-->
>
> 
>
> 现在总结一下：
>
> * `HEAD`指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令`git reset --hard commit_id`。
> * 穿梭前，用`git log`可以查看提交历史，以便确定要回退到哪个版本。
> * 要重返未来，用`git reflog`查看命令历史，以便确定要回到未来的哪个版本

# 常用命令

> git add 文件    <!--把文件添加到仓库 -->
>
> git commit -m “提交的说明”   <!--把文件提交到仓库 -->
>
> git status   <!--查看工作区当前的状态-->
>
> git diff 文件  <!--查看修改了什么内容-->
>
> git log   <!--查看从近到远的提交日志-->
>
> git log	--pretty=oneline   <!--只查看日志中的commit id（版本号）-->
>
> git diff HEAD \-- 文件   <!--查看工作区和版本库里最新版本的区别-->
>
> git checkout \-- 文件  <!--丢弃工作区的修改--> 这个命令中的\--很重要，如果没有\--，就变成了切换到另一个分支的命令
>
> git restore 文件   <!--丢弃工作区的修改-->
>
> git restore --staged 文件   <!--丢弃暂存区的修改，返回到工作区的修改中-->
>
> git reset HEAD 文件   <!--丢弃暂存区的修改，返回到工作区的修改中-->
>
> git rm 文件    <!--删除文件-->
>
> git push origin（远程库的名字） master（分支）  <!--上传本地库的内容到远程库-->
>
> git remote -v   <!--查看远程库信息-->
>
> git remote rm origin（远程库的名字）  <!--删除本地和远程的绑定关系 -->
>
> git clone <code下的链接>   <!--克隆库-->
>
> git checkout -b <分支>   <!--创建并切换到分支-->
>
> git switch -c <分支>    <!--创建并切换到分支-->
>
> git switch <分支>    <!--切换分支-->
>
> git branch <分支>     <!--创建分支-->
>
> git checkout <分支>    <!--切换分支-->
>
> git branch    <!--查看分支，当前分支前面会标一个`*`号 -->
>
> git merge <分支>    <!--合并指定分支到当前分支 -->
>
> git branch -d <分支>   <!--删除分支-->
>
> git stash   <!--把当前工作现场隐藏起来 -->
>
> git stash list   <!--查看隐藏的工作现场-->
>
> git stash apply   <!--恢复工作现场，但是恢复后，stash内容并不删除 -->
>
> git stash drep <隐藏的工作现场>   <!--删除隐藏的工作现场-->
>
> git stash pop   <!--恢复的同时把stash内容也删了 -->
>
> git cherry-pick <commit_id>   <!--复制一个特定的提交到当前分支 -->
>
> git branch -D <分支>    <!--强行删除分支-->
>
> git tag v1.0    <!--给当前提交打标签-->
>
> git tag   <!--查看所有标签-->
>
> git show v1.0   <!--查看指定标签的详细信息-->
>
> git tag v1.1 <commit_id>   <!--给指定的提交打标签-->
>
> git tag -a v1.2 -m “说明” <!--创建带有说明的标签 -a：指定标签名。-m：指定说明文字-->
>
> git tag -d <标签>   <!--删除本地标签-->
>
> git push origin :refs/tags/<标签>    <!--删除远程库标签-->
>
> git tag <远程库名>  <标签>   <!--推送某个标签到远程 -->
>
> git tag <远程库名> \--tags   <!--推送所有标签到远程 -->
>
> 如果标签已经推送到远程，要删除远程标签就麻烦一点，先从本地删除，在从远程删除
>
> ​	
>
> 标签总是和某个commit挂钩。如果这个commit既出现在master分支，又出现在dev分支，那么在这两个分支上都可以看到这个标签。 
>
> 

# 创建git远程仓库

> 注册GitHub账号。由于你的本地Git仓库和GitHub仓库之间的传输是通过SSH加密的，所以，需要一点设置： 
>
> 第1步：创建SSH Key。在用户主目录下（C:\Users\用户名\ ），看看有没有.ssh目录，如果有，再看看这个目录下有没有`id_rsa`和`id_rsa.pub`这两个文件，如果已经有了，可直接跳到下一步。如果没有，打开Shell（Windows下打开Git Bash），创建SSH Key： 
>
> ​	ssh-keygen -t rsa -C "邮箱地址"   //一路回车，使用默认值即可 
>
> 如果一切顺利的话，可以在用户主目录里找到`.ssh`目录，里面有`id_rsa`和`id_rsa.pub`两个文件，这两个就是SSH Key的秘钥对，`id_rsa`是私钥，不能泄露出去，`id_rsa.pub`是公钥，可以放心地告诉任何人。
>
> 第2步：登陆GitHub，打开设置（settings），点击SSH和GPG密钥（SSH and GPG keys），
>
> 点击“新的SSH密钥（New SSH key）”，在标题（Title）这里随便起个名，在钥匙（Key）文本框里粘贴id_rsa.pub文件的内容
>
> 点“Add Key”，你就应该看到已经添加的Key
>
> 创建完成

# 添加远程库

> 首先，登陆GitHub，然后，在右上角找到“新存储库（new repository）”按钮，创建一个新的仓库
>
> 在存储库名称（Repository name）这里输入仓库名称
>
> 然后点击create repository(创建存储库)，就成功地创建了一个新的Git仓库 
>
> 创建好库之后，在本地的仓库下运行命令：
>
> ​	git remote add origin git@github.com:rthzxy/gitck.git（库页面code（代号）下面的ssh链接）   <!--rthzxy：GitHub账户名。 gitck：新建库的名称-->
>
> 添加后，远程库的名字就是`origin`，这是Git默认的叫法，也可以改成别的 
>
> 下一步，就可以把本地库的所有内容推送到远程库上： 
>
> ​	git push -u origin master   
>
> 把本地库的内容推送到远程，用`git push`命令，实际上是把当前分支`master`推送到远程。
>
> 由于远程库是空的，我们第一次推送`master`分支时，加上了`-u`参数，Git不但会把本地的`master`分支内容推送的远程新的`master`分支，还会把本地的`master`分支和远程的`master`分支关联起来，在以后的推送或者拉取时就可以简化命令。

# 从远程库克隆

> 上面讲了先有本地库，后有远程库的时候，如何关联远程库。
>
> 现在，假设我们从零开发，那么最好的方式是先创建远程库，然后，从远程库克隆。
>
> 首先，登陆GitHub，创建一个新的仓库，名字叫`gitku`：勾选添加自述文件（Add a README file ）,这样GitHub会自动为我们创建一个`README.md`文件。创建完毕后，可以看到`README.md`文件： 
>
> 远程库已经准备好了，下一步是用命令`git clone`克隆一个本地库： 
>
> ​	git clone git@github.com:rthzxy/gitku.git   <!--rthzxy：GitHub账户名。 gitku：新建库的名称-->
>
> 注意把Git库的地址换成你自己的，然后进入`gitku目录看看，已经有`README.md`文件了： 

# 配置别名

> \# 命令配置
>
> ​	git config –global alias.st status 
>
> \# 在配置文件中配置
>
> ​	配置Git的时候，加上`--global`是针对当前用户起作用的，如果不加，那只针对当前的仓库起作用。
>
> ​	配置文件放哪了？每个仓库的Git配置文件都放在`.git/config`文件中。别名就在`[alias]`后面，要删除别名，直接把对应的行删掉即可。
>
> ​	而当前用户的Git配置文件放在用户主目录下的一个隐藏文件`.gitconfig`中，配置别名也可以直接修改这个文件，如果改错了，可以删掉文件重新通过命令配置。 

# 搭建git服务器（centos）

> \# 安装git
>
> ​	yum install -y git
>
> \# 创建git用户，用来管理git服务，并为git用户设置密码
>
> ​	useradd git
>
> ​	passwd git
>
> \# 创建证书登录 
>
> ​	收集所有需要登录的用户的公钥，就是他们自己的`id_rsa.pub`文件，把所有公钥导入到`/home/git/.ssh/authorized_keys`文件里，一行一个。 
>
> ​	cd /home/git 
>
> ​	mkdir .ssh && cd .ssh
>
> ​	vim authorized_keys <!--将客户端的id_rsa.pub 公钥复制进去-->
>
> \# 服务器端创建按git仓库
>
> ​	设置一个目录为git仓库，然后把仓库的所属用户和组设置为git
>
> ​		mkdir -p /git/gitcangku && cd /git/gitcangku
>
> ​		git init   <!--创建有工作区的仓库-->
>
> ​		git init --bare sample.git  <!--创建没有工作区的仓库。-->
>
> ​		裸仓库没有工作区，因为服务器上的Git仓库纯粹是为了共享，所以不让用户直接登录到服务器上去改工作区，并且服务器上的Git仓库通常都以`.git`结尾。
>
> ​		cd /git
>
> ​		chown -R git.git gitcangku/
>
> ​	配置客户端每次推送到远程仓库自动更新工作目录内容
>
> ​		cd /git/gitcangku/.git/hooks
>
> ​		vim post-receive 添加如下内容
>
> ​	    	  #!/bin/sh
>
> ​			WORK_TREE='../'
> 			git  --work-tree="${WORK_TREE}" reset --hard
>
> \# 禁用shell登录
>
> ​	出于安全考虑，第二步创建的git用户不允许登录shell，这可以通过编辑`/etc/passwd`文件完成。找到类似下面的一行： 
>
> ​	git : x : 1001:1001:,,,:/home/git:/bin/bash
>
> ​	改为：
>
> ​	git: x :1001:1001:,,,:/home/git:/usr/bin/git-shell
>
>  
>
> \# 客户端克隆仓库
>
> ​	git clone git@ip地址:/git/gitcangku   <!--默认端口为22，如果不是22，IP地址后面还有加端口号-->
>
> ​	 





# 疑难解答

问：输入`git add readme.txt`，得到错误：`fatal: not a git repository (or any of the parent directories)`。

答：Git命令必须在Git仓库目录内执行（`git init`除外），在仓库目录外执行是没有意义的。



问：输入`git add readme.txt`，得到错误`fatal: pathspec 'readme.txt' did not match any files`。

答：添加某个文件时，该文件必须在当前目录下存在，用`ls`或者`dir`命令查看当前目录的文件，看看文件是否存在，或者是否写错了文件名。



问：使用git pull拉取时出现：fatal: refusing to merge unrelated histories

答：在git pull和git push命令中添加–allow-unrelated-histories。 让git允许提交不关联的历史代码。 