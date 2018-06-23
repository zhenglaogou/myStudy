# 版本控制系统:让代码回到历史版本

## 1990s 锁定模式

CVS并发版本系统

VSS Virtual Source Safe 微软出品

## 2000s 合并模式

Subversion - SVN

 集中控制式的版本系统

## 2005

Git

BitKeeper

分布式版本控制系统（不需要副武器的存储）

没有网没有服务器也能够实现版本控制

# 操作流程

### 1.将文件夹变成git仓库 :

git init

### 2.将文件加入仓库中的暂存区:

git add <filename1> <>hello.py

/git add .

### 3.查看仓库的状态:

git status

### 4.提交在本地仓库(必须要在后面添加原因):

git commit -m 'resson'

ps提交的时候回问你please tell me who you are

这个时候你就输入name and email

git config --global user.name zyz

git config --global user.email 1742455714@qq.com

### 5.日志 记录你提交了多少次:

git log(粗略的去看)

git log --graph --pretty=oneline --abbrev-commit

git reflog(第五版跑到第二版，然后在第二版看日志能看见第五版的版本号，可以git reset --hard version回到第五版)

金闪闪的一坨是（版本代码）

### 6.想要改变提交的代码的版本

git reset --hard <version>

### 7.删除文件:

git rm 文件名

### 8.当你误删或者错删了文件，恢复文件的操作!

git checkout -- 文件名 / git checkout .

将本地的代码提交到远端

### 9.与远端仓库关联/断掉关联：

git remote add origin <url>你的git地址

git remove remove origin

### 10.将本地仓库的东西推送到远端仓库,推送！

git push (-u 第一次提交需要写) origin <branch>(master)

### 11.将本地与远端仓库同步:

进入该文件所在的文件夹:git pull

### 12.将远端仓库的资源克隆在本地:

git clone url(url可以是网络的，也可以是公司的)

https://github.com/jackfrued/Python-100-Days.git

然后再执行11

### 13.在分支上面做开发:

git branch(查看在哪条线上面，开始都在master线上面) 

-->git branch pitaya(建立pitaya的分支)

-->git checkout pitaya(切换到pitaya的工作区)   

ps(以上两步可以合并-->git checkout -b pitaya)

-->(开始工作)vim crawler.py -->git add . -->git commit -m 'resson' -->ls

--> git checkout master(切换到master上面) 

--> git merge pitaya(合并pitaya的工作到master上,默认合并模式是fast=forward)

ps(-->git merge --no-ff pitaya -m 'reason' 不使用默认合并模式)

以上操作就是你的日常操作

当你离职的时候，公司要把你这条分支删除了

--git checkout master(切换到master主干下)

--git branch -d pitaya(删除掉pitaya这条分支)

ps当分支没有与主干合并的时候,会有提示,强制删除git branch -D pitaya

git reflog:如果你从第五版跑到了第二版，又想跑到第五版；使用这个去到未来(你当时回到过去的那个版本号)，然后git reset --hard <version前7位>,然后再git log,就能看见此版本的之前的所有版本号了。

jira redmine bugzilla

国内著名的代码托管平台:

码云 

扣丁

