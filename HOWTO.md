HOWTO use Git manage your project  
=================================  
  
  
在Ubuntu上安装Git  
---------------  

    $ sudo apt-get install git git-core  
    # 使用该命令可以在Ubuntu上安装Git的核心部件，此外还可以利用别的命令安装一些Git的辅助工具，  
    # 此处略过。  
  
建立github账户  
------------  
  
登录https://github.com/申请账户，github是一个提供Git服务的站点，可以利用它作为我们管理项
目的服务器。  

在github上和本地建立项目仓库  
-----------------------  
  
在github账户主页上点击Create a Repository创建新的仓库，填入项目名为example和项目介绍，然
后按照提示的教程完成新项目仓库的创建。  

    $ git config --global user.name "gaolinjie"  
    $ git config --global user.email gaolinjie@gmail.com  
    # 在本地设置用户提交项目使用的用户名和邮箱，此处设置的用户名为gaolinjie，  
    # 邮箱为gaolinjie@gmail.com。  
  
    $ mkdir example  
    $ cd example  
    # 在本地用户目录中建立一个名为example的目录作为项目的工作树，进入该目录。  

    $ git init  
    # 初始化Git仓库，在当前目录创建一个.git目录，即为Git仓库，原来的当前目录不再是普通的文档  
    # 目录，而是Git工作树。  

    $ touch README  
    $ git add README  
    # 新建一个README文件，然后生成Git仓库所能接受的数据格式，即快照。  
  
    $ git commit -m 'first commit'  
    # 将临时存储快照的区域（索引）提交到仓库中，每次提交就意味着版本的一次更新，first commit为    
    # 版本更新信息。  
    # 请注意，现在的更新只是提交到了本地的项目仓库中，服务器中的项目仓库并没更新(实际上，此时服务  
    # 器中还未建立相应的项目仓库）。  
  
    $ git remote add origin git@github.com:gaolinjie/example.git  
    # 在github服务器中创建example项目仓库，其中origin为默认的远程仓库。  
    # git@github.com:gaolinjie/example.git为远程仓库的SSH地址。  
  
    $ git push origin master  
    # 将项目仓库本地版本更新推送到远端仓库中，master为默认的远程仓库origin中的主分支。  
  
删除仓库中的某个文件并更新远程仓库  
---------------------------  
  
    $ git rm INDEX  
    # 删除本地工作树中的INDEX文件。  
  
    $ git commit -a  
    # 通知本地项目仓库工作树中有文件删除或修改。  
  
    $ git push origin master  
    # 将更改应用到远程仓库。  





