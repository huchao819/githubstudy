	
## 使用SSH登陆到GitHub
	$ ssh -T git@github.com 
 
## 测试git是否联系
     $ ssh -Tv git@github.com

## 创建一个空文件
    $ touch hello1
 
## 克隆代码库。
    $ git clone git://github.com/gotgit/gotgit.git  Git-daemon协议
    $ git clone https://github.com/gotgit/gotgit.git
    $ git clone git@github.com:huchao819/Helloworld.git
 
## 使用克隆初始化项目库
   1 在Github线上创建一个test版本库
   
   2 克隆版本库到本地
   
      $ git clone git@github.com:huchao/test.git 
      
   3 提交数据  切换到本的github/test目录下，创建README.md文件
   
     $  git add README.md
     $  git commit -m "README  for this project"
     
   4 推送到Github版本库
     $ git push origin master

## 使用本地推送的方式初始化项目库 
   1 在Github线上创建一个test版本库
   
   2 在本地的Github目录下创建Test目录
   
     $ mkdir test
     $ cd test
     $ git init
     
   3 在版本库中添加示例文件，如README.MD
   
     $ git add README.MD
     $ git commit -m "README for this project."
     
   4 为版本库添加origin的远程版本库。
   
     $  git remote add origin git@github.com:huchao819/test.git
     
   5  执行推送命令，完成GitHub版本库的初始化。注意命令行中的-u参数，在推送成功后自动建立本地分支与远程版本库分支的追踪。
   
     $ git push -u origin master
     
     
## 提交本地址库中所有修改的文件到远程版本库
 
    $ git add -u
    $ git commit -m "修改文件的注释"
    $ git push
     
     
强制推送
===========
 
## 显示某个项目库的日志信息
 
     $ git log --prety=fuller
     
  eg: 
  * commit 92dee9b8125afc9a606394ed463f9f264f2d3d58
  * Author:     Jiang Xin <worldhello.net@gmail.com>
  * AuthorDate: Wed Dec 14 14:52:40 2011 +0800
  * Commit:     Jiang Xin <worldhello.net@gmail.com>
  * CommitDate: Wed Dec 14 14:52:40 2011 +0800'
 
 
## 重新设置用户名和邮箱地件变量

    $ git config user.name "Jiang Xin"
    $ git config user.email "gotgithub@gmail.com"
    
## 执行Git修补提交命令
    
    $ git commit --amend --rest-author -C HEAD
    
  其中参数 --rest-author会将提交信息中的属性Author连同AuthorDate一并修改，否则只修改Commit和CommitData.
  参数-C HEAD 维持提交说明不变
  
## 直接强制推送到Github项目库
    $ git push -f 
    

新建分支
===========
  
  Git的分支就是存储在.git/refs/heads/命令空间下的引用。引用文件的内容是该分支对应的ID。
  当前版本库中默认分支master就对应于文件'.git/refs/heads/master'
  
## 创建新分支的方法 
  * 在本地版本中创建新的分支（即引用）
  * 然后使用推送命令将新的引用推送到GitHub版本库中

## 本地版本库中建立新分支mybranch1
   使用git branch命令。如果使用git checkout -b命令可以同是完成新分支的创建和切换。
   
    $ git checkout -b mybranch1

## 将本地分支mybranch1推送到GitHub远程版本库中。

    $ git push -u origin mybranch1
    
## 显示当前版本库的分支
   
    $ git branch
    $ git branch -r 显示分支情况
    
    origin/HEAD -> origin/mybranch1
    origin/master
    origin/mybranch1
    
## 显示远程版本库的目录结构
    
    $ git ls-remote
    From git@github.com:gotgithub/helloworld.git
    f46a28484adb6c1b4830eb4df582325c740e9d6c        HEAD
    e1e52d99fa71fd6f606903efa9da04fd0055fca9        refs/heads/master
    f46a28484adb6c1b4830eb4df582325c740e9d6c        refs/heads/mybranch1
    
 可以看出HEAD和引用refs/heads/mybranch1的哈希值是一样的。
 
## 切换当前分支
   
    $ git checkout master

## 删除分支
   不能删除当前所在的分支，需切换到其它分支后。 
    
    $ git branch -d mybranch1
    
    如果该分支还没有合并，则GitHub不允许删除，需用-D参数强制删除
    $ git branch -D mybranch1
    
    推送命令，删除GitHub远程版本中无用的分支,分支前需要特殊引用表达式'冒号'
    $ git push origin :mybranch1    
    
    
里程碑管理
===========

 里程碑和分支一样也是以引用式存在的，保存在.git/refs/tags/路径下。引用可能指向一个提交，但也可能是其他类型（Tag对象）。
 
 * 轻量级里程碑：  git tag <tagname> [<commit>] 创建，引用直接指向一个提交对象<commit>
 * 带说明的里程碑：git tag -a <tagname> [<commit>] 创建,并且在创建时需要提供说明。保存里程碑说明、指向、创建里程碑的用户信息。
 * 带签名的里程碑：git tag -s <tagname> [<commit>] 创建，在说明的基础上引入了PGP签名

## 创建里程碑命令
    
    $ git tag -m "Tag on inital commit" mytag1 HEAD^
    $ git tag -m "Tag on new commit" mytag2
    $ git tag mytag3
    
## 查看新建立的里程碑
    
    $ git tag -l -n1
    
## 将本地里程碑推送到GitHub远程版本库

    $ git push origin refs/tags/*
    
## 删除里程碑
    
    $ git tag -d mytag3
    $ git push origin :mytag3
    
    
日志文件
 
## 显示某个版本库的日志
    
    $ cd gotgit
    $ git log --graph -3
    
    
    

    
    
 
   
