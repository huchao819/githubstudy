##   ʹ��SSH��½��GitHub
	$ ssh -T git@github.com 
 
## ����git�Ƿ���ϵ
     $ ssh -Tv git@github.com
 
## ��¡����⡣
	$ git clone git://github.com/gotgit/gotgit.git  Git-daemonЭ��
	$ git clone https://github.com/gotgit/gotgit.git
	$ git clone git@github.com:huchao819/Helloworld.git
 
## ����Ŀ��ʱ����ʼ����������ļ���ʽһ
    ��
      1.  ��Github���ϴ���һ��test�汾��
       2.  ��¡�汾�⵽����
     $ git clone git@github.com:huchao/test.git 
   3. �ύ����
            �л�������github/testĿ¼�£�����README.md�ļ�
     $  git add README.md
     $  git commit -m "README  for this project"
      4.  ���͵�Github�汾��
            $ git push origin master

## ����Ŀ��ʱ����ʼ����������ļ�����
    1.  ��Github���ϴ���һ��test�汾��
    2.  �ڱ��ص�GithubĿ¼�´���TestĿ¼
      $ mkdir test
      $ cd test
      $ git init
    3. �ڰ汾�������ʾ���ļ�����README.MD
      $ git add README.MD
      $ git commit -m "README for this project."
    4. Ϊ�汾�����origin��Զ�̰汾�⡣
             $  git remote add origin git@github.com:huchao819/test.git
    5.  ִ������������GitHub�汾��ĳ�ʼ����ע���������е�-u�����������ͳɹ����Զ��������ط�֧��Զ�̰汾���֧��׷�١�             
     $ git push -u origin master
