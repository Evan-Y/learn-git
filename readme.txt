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
