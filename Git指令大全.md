# Git指令大全



## 一、命令详情

1. 新建git仓库

Plain  Text

\# 在当前目录新建一个Git代码库

$ git init

\# 新建一个目录，将其初始化为Git代码库

$ git init [project-name]

\# clone项目

$ git clone [远程仓库地址]

1. 配置

Plain  Text

\# 显示当前的Git配置

$ git config --list

\# 编辑Git配置文件

$ git config -e [--global]

\# 设置提交代码时的用户信息

$ git config [--global] user.name "[name]"

$ git config [--global] user.email "[email address]"

1. 增加/删除文件

Plain  Text

\# 添加指定文件到暂存区

$ git add [文件名1] [文件名2]

\# 添加指定目录到暂存区，包括子目录

$ git add [目录名]

\# 添加当前目录的所有文件到暂存区

$ git add .

\# 添加每个变化前，都会要求确认

\# 对于同一个文件的多处变化，可以实现分次提交

$ git add -p

\# 删除工作区文件，并且将这次删除放入暂存区

$ git rm [文件名1] [文件名2] ...

\# 停止追踪指定文件，但该文件会保留在工作区

$ git rm --cached [文件名]

\# 改名文件，并且将这个改名放入暂存区

$ git mv [file-original] [file-renamed]

1. 提交代码

Plain  Text

\# 提交暂存区到仓库区

$ git commit -m [说明信息]

\# 提交暂存区的指定文件到仓库区（暂存区是指 git add 之后的文件）

$ git commit [文件名1] [文件名2] ... -m [message]

\# 提交的暂存区并提交的仓库

$ git commit -a

\# 提交时显示所有diff信息

$ git commit -v

\# 使用一次新的commit，替代上一次提交

\# 如果代码没有任何新变化，则用来改写上一次commit的提交信息

$ git commit --amend -m [message]

\# 重做上一次commit，并包括指定文件的新变化

$ git commit --amend [file1] [file2] ...

1. 分支（branch）

Plain  Text

\# 列出所有本地分支

$ git branch

\# 列出所有远程分支

$ git branch -r

\# 列出所有本地分支和远程分支

$ git branch -a

\# 新建一个分支，但依然停留在当前分支

$ git branch [branch-name]

\# 新建一个分支，并切换到该分支

$ git checkout -b [branch]

\# 新建一个分支，指向指定commit

$ git branch [branch] [commit]

\# 新建一个分支，与指定的远程分支建立追踪关系

$ git branch --track [本地分支] [远程分支]

\# 切换到指定分支，并更新工作区

$ git checkout [分支名]

\# 切换到上一个分支

$ git checkout -

\# 建立追踪关系，在现有分支与指定的远程分支之间

$ git branch --set-upstream [branch] [remote-branch]

\# 合并指定分支到当前分支

$ git merge [branch]

\# 删除分支

$ git branch -d [branch-name]

\# 删除远程分支

$ git push origin --delete [branch-name]

$ git branch -dr [remote/branch]

1. 标签（tag）



Plain  Text

\# 列出所有tag

$ git tag

\# 新建一个tag在当前commit

$ git tag [tag]

\# 新建一个tag在指定commit

$ git tag [tag] [commit]

\# 删除本地tag

$ git tag -d [tag]

\# 删除远程tag

$ git push origin :refs/tags/[tagName]

\# 查看tag信息

$ git show [tag]

\# 提交指定tag

$ git push [remote] [tag]

\# 提交所有tag

$ git push [remote] --tags

\# 新建一个分支，指向某个tag

$ git checkout -b [branch] [tag]

1. 查看信息

Plain  Text

\# 显示有变更的文件

$ git status

\# 显示当前分支的版本历史

$ git log

\# 显示commit历史，以及每次commit发生变更的文件

$ git log --stat

\# 搜索提交历史，根据关键词

$ git log -S [keyword]

\# 显示某个commit之后的所有变动，每个commit占据一行

$ git log [tag] HEAD --pretty=format:%s

\# 显示某个commit之后的所有变动，其"提交说明"必须符合搜索条件

$ git log [tag] HEAD --grep feature

\# 显示某个文件的版本历史，包括文件改名

$ git log --follow [file]

$ git whatchanged [file]

\# 显示指定文件相关的每一次diff

$ git log -p [file]

\# 显示过去5次提交

$ git log -5 --pretty --oneline

\# 显示所有提交过的用户，按提交次数排序

$ git shortlog -sn

\# 显示指定文件是什么人在什么时间修改过

$ git blame [file]

\# 显示暂存区和工作区的差异

$ git diff

\# 显示暂存区和上一个commit的差异

$ git diff --cached [file]

\# 显示工作区与当前分支最新commit之间的差异

$ git diff HEAD

\# 显示两次提交之间的差异

$ git diff [first-branch]...[second-branch]

\# 显示今天你写了多少行代码

$ git diff --shortstat "@{0 day ago}"

\# 显示某次提交的元数据和内容变化

$ git show [commit]

\# 显示某次提交发生变化的文件

$ git show --name-only [commit]

\# 显示某次提交时，某个文件的内容

$ git show [commit]:[filename]

\# 显示当前分支的最近几次提交

$ git reflog

1. 远程同步

Plain  Text

\# 下载远程仓库的所有变动

$ git fetch [remote]

\# 显示所有远程仓库

$ git remote -v

\# 显示某个远程仓库的信息

$ git remote show [remote]

\# 增加一个新的远程仓库，并命名

$ git remote add [shortname] [url]

\# 取回远程仓库的变化，并与本地分支合并

$ git pull [remote] [branch]

\# 上传本地指定分支到远程仓库

$ git push [remote] [branch]

\# 强行推送当前分支到远程仓库，即使有冲突

$ git push [remote] --force

\# 推送所有分支到远程仓库

$ git push [remote] --all

1. 撤销操作

Plain  Text

\# 恢复暂存区的指定文件到工作区

$ git checkout [file]

\# 恢复某个commit的指定文件到暂存区和工作区

$ git checkout [commit] [file]

\# 恢复暂存区的所有文件到工作区

$ git checkout .

\# 重置暂存区的指定文件，与上一次commit保持一致，但工作区不变

$ git reset [file]

\# 重置暂存区与工作区，与上一次commit保持一致

$ git reset --hard

\# 重置当前分支的指针为指定commit，同时重置暂存区，但工作区不变

$ git reset [commit]

\# 重置当前分支的HEAD为指定commit，同时重置暂存区和工作区，与指定commit一致

$ git reset --hard [commit]

\# 重置当前HEAD为指定commit，但保持暂存区和工作区不变

$ git reset --keep [commit]

\# 新建一个commit，用来撤销指定commit

\# 后者的所有变化都将被前者抵消，并且应用到当前分支

$ git revert [commit]

\# 暂时将未提交的变化移除，稍后再移入

$ git stash

$ git stash pop

## 二、常用命令

- git branch 查看本地所有分支



- git status 查看当前状态

 

- git commit 提交

 

- git branch -a 查看所有的分支

 

- git branch -r 查看远程所有分支

 

- git remote add origin git@192.168.1.119:ndshow

 

- git push origin [分支名称 ]   将文件给推到某分支上

 

- git remote show origin 显示远程库origin里的资源

 

- git checkout --track origin/dev 切换到远程dev分支

 

- git branch -D master develop 删除本地库develop

 

- git checkout -b dev 建立一个新的本地分支dev

 

- git merge origin/dev 将分支dev与当前分支进行合并

 

- git checkout dev 切换到本地dev分支

 

- git remote show 查看远程库

 

- git add .

 

- git rm 文件名(包括路径) 从git中删除指定文件

 

- git clone [git://github.com/schacon/grit.git](https://link.jianshu.com/?t=git://github.com/schacon/grit.git) 从服务器上将代码给拉下来

 

- git config --list 看所有用户

 

- git ls-files 看已经被提交的

 

- git rm [file name] 删除一个文件

 

- git commit -a 提交当前repos的所有的改变

 

- git add [file name] 添加一个文件到git index

 

- git commit -m "This is the message describing the commit" 添加commit信息

 

- git log 看你commit的日志

 

- git diff 查看尚未暂存的更新

 

  //这两步需要同时操作方可删除

- git rm --cached a.a 移除文件(只从暂存区中删除)

- git commit -m "remove" 移除文件(从Git中删除)



- git stash push 将文件给push到一个临时空间中



-  git stash pop 将文件从临时空间pop下来