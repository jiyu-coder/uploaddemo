# demo
本地仓库管理
ref--基于vscode进行的git操作，可不看
https://www.bilibili.com/video/BV1Hkr7YYEh8/?spm_id_from=333.337.search-card.all.click&vd_source=493e8b86e3ffb6d41122114c66662787


```
git --version

打开文件目录cmd
$ git init

$ git config --global user.name "jiyu-coder"

$ git config --global user.eamil 1905341249@qq.com

$ git add .

$ git commit -m "用户管理中心V1.0"

$ branch  -M main

$ remote add origin https://github.com/jiyu-coder/user-center-backend.git

$ git push -u origin main

//-u 设置默认上游分支
//-M强制重命名当前分支main

//下次push
$ git push


其他命令
git branch  //
git remote -v
```


远程仓库管理-github

Jjy8659github

分支branch

| 名称                 | 含义                     |
| ------------------ | ---------------------- |
| **分支 (branch)**    | 项目的一个独立开发线，可以并行开发不同功能。 |
| **main/master 分支** | 主分支，用于保存稳定、正式版本的代码。    |
| **dev 分支**         | 用于日常开发和测试。             |
| **feature 分支**     | 用于开发新功能。               |
| **hotfix 分支**      | 用于紧急修复线上 bug。          |

# 命令学习


## 🚀 零、一键推送项目（常用初始化模板）

以下命令是你**第一次将项目上传到 GitHub** 的完整流程，可直接复制执行👇：

git init                                                                                                              # 初始化本地仓库
git add .                                                                                                       # 添加全部文件
git commit -m "first commit"                                                           # 提交
git branch -M main                                                                              # 强制将分支命名为 main
git remote add origin https://github.com/用户名/仓库名.git  # 关联远程仓库
git push -u origin main                                                                             # 推送到 GitHub

## 🧱 一、Git 初始化与配置

	# 初始化本地仓库（在项目根目录执行）
	git init  
	
	# 查看当前 Git 状态（哪些文件被修改、哪些未提交）
	git status  
	
	# 查看当前配置（用户名、邮箱、代理等）
	git config --list  
	
	# 设置全局用户名（提交记录的作者名）
	git config --global user.name "你的用户名"
	
	# 设置全局邮箱（提交记录的邮箱）
	git config --global user.email "你的邮箱@example.com"


---

## 📦 二、文件管理与提交
	
	# 将文件添加到暂存区（. 表示全部文件）
	git add .
	
	# 或者添加指定文件
	git add 文件名.java
	
	# 提交暂存区中的修改到仓库
	git commit -m "提交说明"
	
	# 查看提交日志（最新在上）
	git log  
	
	# 查看单行简洁日志
	git log --oneline  
	
	# 修改最近一次提交的说明文字
	git commit --amend -m "修改后的提交说明"


---

## 🌍 三、远程仓库操作

	# 添加远程仓库（origin 为别名）
	git remote add origin https://github.com/用户名/仓库名.git  
	
	# 查看当前远程仓库信息
	git remote -v  
	
	# 修改远程仓库地址（如果仓库迁移或改名）
	git remote set-url origin https://github.com/新用户名/新仓库.git  
	
	# 删除远程仓库
	git remote remove origin  


---

## 🚀 四、推送与拉取
	
	# 推送本地 main 分支到远程仓库（并设置上游）
	git push -u origin main  
	
	# 以后只需简单执行（自动推送到上游分支）
	git push  
	
	# 从远程拉取更新到本地
	git pull  
	
	# 拉取远程分支并合并到当前分支
	git pull origin main  
	
	# 克隆远程仓库到本地
	git clone https://github.com/用户名/仓库名.git


---

## 🌿 五、分支管理
	
	# 查看所有分支（带 * 的是当前分支）
	git branch  
	
	# 创建一个新分支
	git branch 分支名  
	
	# 切换到指定分支
	git checkout 分支名  
	
	# 创建并切换到新分支（推荐）
	git checkout -b 分支名  
	
	# 将当前分支强制命名为 main
	git branch -M main  
	
	# 合并指定分支到当前分支
	git merge 分支名  
	
	# 删除本地分支
	git branch -d 分支名  
	
	# 删除远程分支
	git push origin --delete 分支名  


---

## 🧩 六、撤销与回滚
	
	# 撤销未暂存的修改（恢复到上一次提交状态）
	git checkout -- 文件名  
	
	# 撤销已暂存的文件（回到未暂存状态）
	git reset HEAD 文件名  
	
	# 回滚到上一个提交版本（保留文件修改）
	git reset --soft HEAD^  
	
	# 回滚到上一个提交版本（丢弃修改）
	git reset --hard HEAD^  
	
	# 查看历史提交版本号（commit id）
	git log --oneline  
	
	# 回滚到指定版本
	git reset --hard 提交ID  
	
	# 撤销最近一次推送（慎用）
	git push -f origin main  


---

## 🧭 七、查看与比较
	
	# 查看文件修改的具体内容
	git diff  
	
	# 查看暂存区与上次提交的差异
	git diff --cached  
	
	# 查看远程分支列表
	git branch -r  
	
	# 查看本地与远程所有分支
	git branch -a  


---

## 🔐 八、SSH 方式连接 GitHub（推荐长期使用）
	
	# 生成 SSH 密钥（一路回车）
	ssh-keygen -t rsa -b 4096 -C "你的GitHub邮箱"
	
	# 查看公钥内容
	cat ~/.ssh/id_rsa.pub  
	
	# 测试是否连接成功
	ssh -T git@github.com  
	
	# 设置 SSH 远程地址
	git remote set-url origin git@github.com:用户名/仓库名.git


---

## 🧰 九、实用技巧命令
	
	# 忽略文件或文件夹（编辑 .gitignore 文件）
	# 例如：
	# /target/
	# *.log
	# application.properties
	
	# 查看 .gitignore 是否生效
	git status  
	
	# 清除未被跟踪的文件（慎用）
	git clean -f  
	
	# 查看当前所在分支、远程跟踪状态等
	git status  
	
	# 临时保存当前修改（切分支前使用）
	git stash  
	
	# 恢复暂存的修改
	git stash pop  

---

## 🧾 十、简要命令速查表

|操作|命令|说明|
|---|---|---|
|初始化仓库|`git init`|创建本地仓库|
|查看状态|`git status`|查看修改情况|
|添加文件|`git add .`|所有文件加入暂存区|
|提交修改|`git commit -m "msg"`|提交说明|
|查看日志|`git log --oneline`|查看提交记录|
|创建分支|`git branch name`|创建新分支|
|切换分支|`git checkout name`|切换到分支|
|合并分支|`git merge name`|合并代码|
|推送远程|`git push -u origin main`|推送到 GitHub|
|拉取远程|`git pull`|同步远程更新|

# BUG

1、 
```
$ git push -u origin main

fatal: unable to update url base from redirection:
  asked for: https://start.aliyun.com/type=maven-project&language=java&architecture=none&bootVersion=2.6.13&baseDir=sb-mybatis-p-demo&groupId=com.example&artifactId=sb-mybatis-p-demo&name=sb-mybatis-p-demo&description=Demo%20project%20for%20Spring%20Boot&packageName=com.example.sb-mybatis-p-demo&packaging=jar&javaVersion=1.8&dependencies=web,lombok,mysql/sb-mybatis-p-demo.git/info/refs?service=git-receive-pack
   redirect: https://error.taobao.com/app/tbhome/common/error.html

```

远程仓库 URL **不是 GitHub 仓库地址**，而是一个 **Spring Initializr 的阿里云镜像链接**

2、Connection was reset
更换手机热点



