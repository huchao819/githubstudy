	
## 使用SSH登陆到GitHub
	$ ssh -T git@github.com 
 
## 测试git是否联系
     $ ssh -Tv git@github.com
 
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
     
 
 ##  显示某个项目库的日志信息
 
     $ git log --prety=fuller
  eg: 
  * commit 92dee9b8125afc9a606394ed463f9f264f2d3d58
  * Author:     Jiang Xin <worldhello.net@gmail.com>
  * AuthorDate: Wed Dec 14 14:52:40 2011 +0800
  * Commit:     Jiang Xin <worldhello.net@gmail.com>
  * CommitDate: Wed Dec 14 14:52:40 2011 +0800'
  * 
 
 ##  重新设置用户名和邮箱地件变量

    $ git config user.name "Jiang Xin"
    $ git config user.email "gotgithub@gmail.com"
    
## 执行Git修补提交命令
    
    $ git commit --amend --rest-author -C HEAD
    
  其中参数 --rest-author会将提交信息中的属性Author连同AuthorDate一并修改，否则只修改Commit和CommitData.
  参数-C HEAD 维持提交说明不变
  
## 直接强制推送到Github项目库
    $ git push -f 
 
   
