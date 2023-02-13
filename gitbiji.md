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





# 疑难解答

### 疑难解答

Q：输入`git add readme.txt`，得到错误：`fatal: not a git repository (or any of the parent directories)`。

A：Git命令必须在Git仓库目录内执行（`git init`除外），在仓库目录外执行是没有意义的。

Q：输入`git add readme.txt`，得到错误`fatal: pathspec 'readme.txt' did not match any files`。

A：添加某个文件时，该文件必须在当前目录下存在，用`ls`或者`dir`命令查看当前目录的文件，看看文件是否存在，或者是否写错了文件名。