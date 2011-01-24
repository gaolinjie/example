[example]()  
===========    
    
这是一个演示如何使用Git来进行项目管理的小型示例项目。    
     
什么是Git？   
---------   
  
以下是引自维基百科对Git的介绍：  
http://zh.wikipedia.org/zh/Git/  
  
Git是一个由Linus Torvalds为了更好地管理linux内核开发而创立的分布式版本控制/软件配置管理软
件。需要注意的是和GNU Interactive Tools，一个类似Norton Commander界面的文件管理器相区
分。

Git最初的开发动力来自于BitKeeper和Monotone。 Git最初只是作为一个可以被其他前端比如Cogito
或StGIT包装的后端而开发的。不过，后来Git内核已经成熟到可以独立地用作版本控制。很多有名的软件
都使用Git来进行版本控制，其中有Linux内核，X.Org服务器和OLPC内核开发。

###命名来源：

Linus Torvalds自嘲地取了这个名字"git"。在英式英语中指一个愚笨或者不开心的人。
“I'm an egotistical bastard, and I name all my projects after myself. First 
Linux, now git.”

Git的官方维基也给出了多种其他的关于名字的解释。

###主要功能：

Git --- The stupid content tracker,傻瓜内容跟踪器。Linus是这样给我们介绍Git的。

Git 是用于Linux内核开发的版本控制工具。与常用的版本控制工具CVS,Subversion等不同，它采用了
分布式版本库的方式，不必服务器端软件支持，使源代码的发布和交流极其方便。Git的速度很快，这对于诸
如Linux kernel这样的大项目来说自然很重要。Git最为出色的是它的合并跟踪（merge tracing）能力。

实际上内核开发团队决定开始开发和使用Git来作为内核开发的版本控制系统的时候，世界开源社群的反对声
音不少，最大的理由是Git太艰涩难懂，从Git的内部工作机制来说，的确是这样。但是随着开发的深入，
Git的正常使用都由一些友好的脚本命令来执行，使Git变得非常好用，即使是用来管理我们自己的开发项
目，Git都是一个友好，有力的工具。现在，越来越多的著名项目采用Git来管理项目开发，例如：wine, 
U-boot等，详情看 http://www.kernel.org/git。

作为开源自由原教旨主义项目，Git没有对版本库的浏览和修改做任何的权限限制，通过其他工具也可以达到
有限的权限控制，比如：gitosis,CodeBeamer MR。原本Git的使用范围只适用于Linux/Unix平台，
但逐步并成熟了在Windows平台下的使用，主要归功于Cygwin与msysgit环境与TortoiseGit这样易用
的GUI工具。其实Git的源代码中已经加入了对Cygwin与MinGW编译环境的支持并被逐步完善，对于
Windows使用者是个福音。

###早期历史：

早期Linux的開發人員是使用BitKeeper来管理版本控制和维护程式码。2005年的时候，开发BitKeeper
的公司同Linux内核开源社区结束合作关系，並收回使用BitKeeper的权利。Torvalds开始着手开发
Git来替代BitKeeper。

###实现原理：

Git和其他版本控制系统（CVS）有不少的差别，Git本身关心档案的整体性是否有改变，但多数的CVS，或
Subversion系统则在乎檔案内容的差异。因此Git更像一個檔案系统，直接在本機上取得資料，不必連線
到host端取資料回来。

###移植性：

在Windows平台上有msysgit與TortoiseGit可資利用。TortoiseGit還提供有GUI。  
  
  
什么是GitHub？  
------------  

GitHub是一个用于使用Git版本控制系统的项目的基于互联网的存取服务。它是由GitHub公司（先前被称 
作用Logical Awesome）的开发者Chris Wanstrath,PJ Hyett,和Tom Preston-Werner使用
Ruby on Rails写成的。GitHub同时提供商业账户和为开源项目提供的免费账户。根据在2009年的Git
用户调查，GitHub是最流行的Git存取站点。  

它提供了像feedsfollowers和显示开发者们怎样在他们的版本库的版本上工作的网络图表。  

GitHub也经营了一个pastebin风格的站点，维基用于个人信息库，并且可以通过一个git版本库进行编辑
网页。  

截至2010年1月,GitHub仍然由GttHub公司所经营。  
