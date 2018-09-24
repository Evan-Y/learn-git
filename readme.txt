Git is a version control system.
Git is free software.

初始化一个Git仓库：git init
添加文件到Git仓库：
	1、git add 文件，可以添加多次
	2、git commit -m '说明注释'

修改文件：
	1、git status: 查看工作区的状态，是否有文件修改过
	2、git diff: 查看修改的内容
	3、提交修改: 和添加文件一样，分两步，git add + git commit

版本回退：
	1、git log: 查看提交的日志，从近到远
	2、HEAD 表示当前的版本，HEAD^上一个版本，HEAD^^上上一个版本，HEAD~100往上100个版本
	3、git reset + '版本' 回退到指定的版本
	4、git reset + 'commit id' 回退到commit id对应的版本
	5、git reflog: 查看历史命令历史

工作区和暂存区：
	1、工作区：电脑中的当前目录
	2、暂存区（stage），分支
	3、git add: 把工作区的文件添加到暂存区（stage）
	4、git commit: 把暂存区中的所有内容提交到当前分支
	5、git diff--> 工作区与暂存区比较; git diff --cached --> 暂存区与分支比较

撤销修改：
	1、git chekout -- filePath: 修改了但是未git add到暂存区；让文件回到最近一次git commit或git add时的状态
	2、git reset HEAD <file>: 把暂存区中的修改撤销掉（unstage），重新放回工作区
	3、若已commit，回退版本

删除文件：
	1、rm file: 从工作区删除文件
	2、git status: 查看哪些文件被删除了
		2.1 git rm file + git commit 从版本库中删除该文件
		2.2 git checkout -- file 误删，从版本库中恢复文件

添加远程库：
	1、关联一个远程库：git remote add origin git@server-name:path/repo-name.git
	2、关联后，使用命令 git push -u origin master 第一次推送master分支的所有内容
	3、此后，每次本地提交后，只要有必要，使用命令 git push origin master 推送最新修改

从远程库克隆：
	1、从远程库克隆到本地库：git clone git@server-name:path/repo-name.git
	2、ssh支持的原生git协议速度最快

创建与合并分支：
	1、git checkout -b branch-name: -b参数表示创建并切换到新的分支
	2、git branch: 查看所有分支，×表示当前分支
	3、提交后，切换回master分支，master分支并看不到刚提交的内容，master分支此刻的提交点并没有变，需要进行合并
	4、git merge branch-name: 合并指定分支到当前分支
	5、git branch -d branch-name: 删除指定分支 -d

分支冲突：
	git无法自动合并分支时，需要先解决冲突
	解决冲突就是把git合并失败的文件手动编辑为我们希望的内容，再提交
	git log --graph 查看分支合并图
