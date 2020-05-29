GitHub笔记
===

### 1.本地配置
配置基本帐号

	git config --global user.name XXX
配置基本邮箱

	git config --global user.email XXX

--global 参数，有了这个参数，表示你这台机器上所有的Git仓库都会使用这个配置

新建一个目录 github，进入
执行命令

	git init

代表建好了一个新的git仓库
可以写个文件测试

	vim README.md
	git add README.md    #加入
	git commit -m "注释"    #为本地创建了一次commit
	git push origin master    #上传到创库
	git log    #查看日志，可查看做了什么修改
	git status    #查看状态
	git commit -a -m "注释"    #简化 相当于git add + git commit -m




### 2.GitHub配置

在自己的hub上点击New repostitory建立一个目录
创建成功后

	git remote add origin https://github.com/XXX/demo.git    #连接自己的GitHub仓库

	git push origin master    #上传到仓库中

remote 代表要操作远程库
add 代表在本地仓库添加一各从github上获取的远程库
origin 别名(可以任意名称)
push 我们可以认为就是 上传代码到服务器上
master 主分支/文件库

#### 分支

建立分支

	git branch test    #建立分支test
	git checkout test    #切换到分支test
	git branch -d    #删除本地分支 -D 强制删除
	git push origin :test    #删除远程分支，冒号前边有空格

#### 版本冲突处理

fetch
1. 远程取到更新
2. 对比一下不同
3. 执行合并，或修改

	git fetch origin master    #从远程master分支获取更新
	git diff master origin/master    #对主分支和远程分支进行比对
	git merge origin/master    #合并

如果，fetch之后，我们又修改了本地库，然后merge会冲突，怎么办？

	git checkout --ours 文件名   #以本地库为准
	git add 文件名
	git commit -m "#"
	git merge origin/master   
	git push origin master     #push之后远程仓库就会发生改变
	#最后需要重新add commit 一下，然后push到远程仓库
    
	git checkout --theris 文件名    #以远程仓库为准

#### 克隆

clone

	git clone -b 分支名  git地址    #不写分支就是主分支



