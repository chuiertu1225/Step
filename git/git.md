*摘于阮一峰*
https://www.ruanyifeng.com/blog/2015/12/git-cheat-sheet.html
## 1.新建代码库
新建一个git代码库 `git init`  
新建一个目录，将其初始化为代码库 `gir init [proj-name]`  
下载一个项目和它整个代码历史 `git clone [url]`
## 2.配置
显示当前的git 配置 `git config --list`  
编辑git配置文件`git config -e [--global]`  
设置提交代码时的用户信息  
`git config [--global] user.name "[name]"`  
`get config [--global] user.email "[email]"`
## 3.增加删除文件
添加文件到暂存区`git add [file1] [file2] ...`  
添加指令目录到暂存区 `git add [dir]`  
添加当前目录所有文件 `git add .`
## 4.代码提交
提交暂存区到仓库区`git commit -m [message]`  
提交指定文件到仓库区 `git commit [f1][f2] ... -m [message]` 
## 5.分支
列出本地所有分支`git branch`  
列出远程所有分支`git branch -r`  
列出本地远程所有分支`git branch -a`  
新建一个分支，停留在当前分支`git branch [branch-name]`  
新建一个分支，切到该分支`git branch -b [branch-name]`   
新建一个分支，与指定的远程分支建立追踪关系`git branch --track [branch] [remote-branch]`  
切换到指定分支`git checkout [branch-name]`  
切换到上一个分支`git checkout -`  
在现有分支和远程分支建立追踪关系`git branch --set-upstream [branch] [remote-branch]`  
合并指定分支到当前分支`git merge [branch]`
## 6.标签
列出所有标签`git tag`  
新建一个标签在当前commit`git tag [tag]`  
新建一个标签在指定coomit`git tag [tag] [commit]`  
删除本地tag`git tag -d [tag]`  
删除远程tag`git push origin :refs/tags/[tagName]`  
查看tag信息`git show [tag]`  
## 7.查看信息
显示有变更的文件`git status`  
显示当前分支的版本历史`git status`  
显示commit历史，以及每次变更的文件`git log -stat`  
搜索提交历史，根据关键词`gir log -S [keyword]`  
显示暂存区和工作区的差异`git diff`  
## 8.远程同步
下载远程仓库所有变动`git fetch [remote]`  
显示所有远程仓库`git remote -v`  
显示某个远程仓库的信息`git remote show [remote]`  
增加一个新的远程仓库，并命名`git remote add [shortname] [url]`  
取回远程仓库的所有变化，与本地分支合并`git pull [remote] [branch]`  
上传本地指定分支到远程仓库`git push [remote] [branch]`  
强行推送到当前分支到远程仓库，即使有冲突`git push [remote] --force`  
推送所有分支到远程仓库`git push [remote] --all`  
## 9.撤销
恢复暂存区指定文件到工作区`git checkout [file]`  
恢复某个commit的文件到暂存区和工作区`git checkout [commit] [file]`  
恢复暂存区所有文件到工作区`git checkout .`  
重置暂存区的指定文件，与上一次commit保持一致，但工作区不变`git reset [file]`
重置暂存区与工作区，与上一次commit保持一致`git reset --hard`
## 10.其他
生成一个可供发布的压缩包`git archive`

