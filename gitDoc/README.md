# Git学习

参考文档：

​	[Git命令行基础操作](https://www.cnblogs.com/tocy/p/git-command-line-manual.html)

## Git历史

​	同生活中的许多伟大事件一样,Git诞生于ー个极富纷争大举创新的年代。 Linux内核开源项目有着为数众广的参与者。绝大多数的工m内核维护工作都花在了提交补丁和保存归档的繁琐事务上(1991-2002年间)。到2002年,整个项目组开始启用分布式版本控制系统 Bitkeeper来管理和维护代码。

​	到2005年的时候,开发 Bitkeeper的商业公司同 Linux内核开源社区的合作关系结東,他们收回了免费使用 Bitkeeper的权力。这就迫使Linx开源社区(特别是Linx的缔造者 Linus Torvalds)不得不吸取教训,只有开发一套属于自己的版本控制系统才不至于重蹈覆撤。他们对新的系统订了若干目标：

- 速度

- 简单的设计

- 对非线性开发模式的强力支持（允许上千个并行开发的分支）

- 完全分布式

- 有能力高效管理类似Linux内核一样的超大规模项目（速度和数据量）

  

## Git与SVN对比

### SVN

​	SVN是集中式版本控制系统,版本库是集中放在中央服务器的,而干活的时候,用的都是自己的电脑,所以首先要从中央服务器哪里得到最新的版本,然后干活,干完后,需要把自己做完的活推送到中央服务器。集中式版本控制系统是必须联网才能工作,如果在局域网还可以,带宽够大,速度够快,如果在互联网下,如果网速慢的话,就郁闷了下图就是标准的集中式版本控制工具管理方式:

![1565599084871](.\img\1565599084871.png)

​	集中管理方式在一定程度上看到其他开发人员在干什么,而管理员也可以很轻松掌握每个人的开发权限。

但是相较于其它优点而言，集中式版本控制工具缺点很明显：

- 服务器单点故障
- 容错性差



### Git

​	Git是分布式版本控制系统,那么它就没有中央服务器的,每个人的电脑就是一个完整的版本库,这样,工作的时候就不需要联网了,因为版本都是在自己的电脑上。既然每个人的电脑都有一个完整的版本库,那多个人如何协作喝?比如说自己在电脑上改了文件A,其他人也在电脑上改了文件A,这时,你们两之间只需把各自的修改推送给对方,就可以互相看到对方的修改了。

下图就是分布式版本控制工具管理方式

![1565599446338](.\img\1565599446338.png)

### git工程流程

一般工作流程如下：

1. 从远程仓库中克隆Git资源作为本地仓库；
2. 从本地仓库中 checkout代码然后进行代码修改；
3. 在提交前先将代码提交到暂存区提交修改；
4. 提交到本地仓库。本地仓库中保存修改的各个历史版本；
5. 在修改完成后，需要和团队成员共享代码时，可以将代码Push到远程仓库

下图展示了Git的工作流程：

![1565599867082](.\img\1565599867082.png)

## Git 的安装

​	最早Git是在 Linux上开发的，很长一段时间内也只能在 Linux和Unix系统上跑。不过,慢慢地有人把它移植到了 Windows上。现在Git可以在 Linux、Unix、Mac和 Windows这几大平台上正常运行了。

​	到[git官网](https://git-scm.com/)进行下载。 如果需要其它git客户端界面可以到这里[下载](https://git-scm.com/download/gui/win)，比如git for windows。

### TortoiseGit

​	Tortoise（乌龟）,  之前使用svn的时候经常使用TortoiseSVN，在git它也有相应的版本工具，名为TortoiseGit。

下载[TortoiseGit](https://tortoisegit.org/download/)，有软件本身还有各种语言补丁。

在安装了语言补丁后为什么语言没有还米有变，这个时候需要做一下设置：

![1565602708956](.\img\1565602708956.png)

这个工具提供很多的功能方便我们操作Git。

![1565603810211](.\img\1565603810211.png)

## 使用git管理文件版本

### 创建版本库

​	创建版本库后，在目录中会多一个.git的隐藏文件目录，这个目录就是本地仓库，包含这个文件夹的这个目录就被称为工作空间。

#### 使用gitBash

```bash
git init
```

#### 使用gitGUI

![1565602891715](.\img\1565602891715.png)

#### 使用TortoiseGit

​	右键菜单中，选取“git 在这里创建版本库(Y)...”。

![1565602981518](.\img\1565602981518.png)

### 向本地仓库添加文件

​	Git的版本库里存了很多东西，其中最重要的就是称为stage（或叫index）的暂存区，还有Git为我们自动创建的第一个分支master，以及指向master的第一个指针叫HEAD。

![1565604318975](.\img\1565604318975.png)

​	下面是将文件添加到暂存区。

#### 使用gitBash

```bash
git add hello.txt
```

#### 使用gitGUI

Commit -> Stage to Commit， 快捷键Ctrl + T。

![1565603616371](.\img\1565603616371.png)

#### 使用TortoiseGit

![1565603408437](.\img\1565603408437.png)

添加完毕后，TortoiseGit提供了文件图片标注：

![1565603511374](.\img\1565603511374.png)

### 向本地仓库提交文件

#### 使用gitBash

```bash
git commit -m '这是日志信息'
```

#### 使用gitGUI

![1565604682082](.\img\1565604682082.png)

#### 使用TortoiseGit

右击工作区，“Git 提交(C) -> master”。

![1565604830536](.\img\1565604830536.png)

在工作区空白处右击，选择“TortoiseGit” -> "版本库浏览器"，可以看到提交到本地库中的文件相关信息。

### 修改并提交到本地仓库

#### 使用gitBash

```
# 查看文件现在的状态
git status
# 添加文件到暂存区
git add hello.txt
# 提交修改的文件
git commit -m '修改日志信息'
```

#### 使用gitGUI

​	先将文件添加到暂存区ctrl+t，然后提交文件。

#### 使用TortoiseGit

​	这个工具直接将为我们省去了一个添加了暂存区的步骤（工具做了，不需要人去做）。

![1565605660053](.\img\1565605660053.png)

### 查看仓库日志

#### 使用gitBash

```bash
git log 
git log --stat      # 仅显示摘要选项
git log --pretty=oneline        # 定制记录格式
git log --graph     # 图像化分支和版本更新
```

#### 使用gitGUI

​	打开git GUI窗口，点击菜单“Repository” -> "Visualize master's History"。

![1565606080800](.\img\1565606080800.png)

#### 使用TortoiseGit

​	git菜单中，点击“显示日志”。

![1565605905471](.\img\1565605905471.png)

### 删除并提交到本地仓库

#### 使用gitBash

文件系统中直接删除后，使用：

```bash
# 查看删除的文件
git status
# 添加文件
git add hello2.txt
# 提交
git commit -m '提交删除的文件'
```

也可以使用：

```bash
git rm hello.txt
# 查看状态
git status
# 提交
git commit -m '提交删除的文件'
```

#### 使用gitGUI

​	在gitGUI中可以看到删除的文件，使用ctrl+t将该文件添加到暂存区stage中，然后输入日志commit。

#### 使用TortoiseGit

​	右击工作区，点击“Git 提交(C) -> 'master'”。

![1565608940483](.\img\1565608940483.png)	

也可以直接使用文件右键菜单中TortoiseGit提供的删除功能：

![1565609250805](.\img\1565609250805.png)

​	"**删除并保留本地副本**"是给文件添加删除标记，用于那种只需要本地游，版本库中不需要有的清空，如开发工具为我们生成的一些文件或者其它一些情况。



### 添加到忽略列表

#### 使用gitBash

​	直接新建一个.gitignore文件配置忽略规则

#### 使用gitGUI

​	直接新建一个.gitignore文件配置忽略规则

#### 使用TortoiseGit

![1565610124805](.\img\1565610124805.png)

![1565610265840](.\img\1565610265840.png)

这个时候会生成一个.gitignore文件，内容是(参见【[忽略文件语法](https://www.cnblogs.com/songyinan/p/10969775.html)】)：

![1565610679325](.\img\1565610679325.png)

忽略之后的文件或文件夹，在提交的时候就不会再显示了。



## 将本地仓库推送到远程仓库

### 什么是SSH

​	ssh（Secure Shell 安全外壳协议），由 IETF 的网络小组（Network Working Group）所制定；SSH 为建立在应用层基础上的安全协议。SSH 是目前较可靠，专为远程登录会话和其他网络服务提供安全性的协议。利用 SSH 协议可以有效防止远程管理过程中的信息泄露问题。SSH最初是UNIX系统上的一个程序，后来又迅速扩展到其他操作平台。SSH在正确使用时可弥补网络中的漏洞。SSH客户端适用于多种平台。

​	ssh提供了两种级别的安全验证：第一种级别（基于口令的安全验证），知道用户名和密码就可以登录到远程主机。第二种级别（基于密钥的安全验证），必须为自己创建一对密钥，私钥放自己机器上，公钥放要访问的服务器上。

### 创建密钥对

```bash
ssh-keygen -t rsa
# -t 指定密钥类型，默认是 rsa ，可以省略。
# -C 设置注释文字，比如邮箱。
# -f 指定密钥文件存储文件名。
# 还有其它参数，可以在网络上搜索学习

# 完毕后，在用户目录下有一个.ssh文件夹，里面存放了生成好的公钥和私钥
```

### 添加SSH key到github

a、首先你需要拷贝 id_rsa.pub 文件的内容，你可以用编辑器打开文件复制，也可以用git命令复制该文件的内容，如：

```bash
# git bash中
clip < ~/.ssh/id_rsa.pub
```

b、登录你的github账号，从又上角的设置（ Account Settings ）进入，然后点击菜单栏的 SSH key 进入页面添加 SSH key。

c、点击 Add SSH key 按钮添加一个 SSH key 。把你复制的 SSH key 代码粘贴到 key 所对应的输入框中，记得 SSH key 代码的前后不要留有空格或者回车。当然，上面的 Title 所对应的输入框你也可以输入一个该 SSH key 显示在 github 上的一个别名。默认的会使用你的邮件名称。

![1565694092963](.\img\1565694092963.png)

### 测试SSH Key

```bash
# git bash中
ssh -T git@github.com
```



### ssh本地仓库推送远程仓库

#### 使用gitBash

```bash
# origin只是远程仓库的一个代号/标识
git remote add origin git@github.com:FallenGodCoder/learnGit.git
git push -u origin master
```

#### 使用gitGUI

在Git GUI中， "remote" =》 "add..."，添加远程仓库别名。

![1565694822982](.\img\1565694822982.png)

"remote" =》 “Push...” 将选中的分支推送到目标仓库。

![1565694878987](.\img\1565694878987.png)

#### 使用TortoiseGit

 在工作目录中右击选择“Git 同步”。

![1565695233761](.\img\1565695233761.png)

​	点击“管理”，添加远程地址别名。 其中，Putty密钥这里，如果是使用Putty，那么久呀哦使用Putty密钥，这里我们使用的是ssh，所以这里要选择ssh的私钥（告诉ssh使用这个私钥加密数据）。

![1565695404069](.\img\1565695404069.png)

关闭上面对话框，点击“推送”按钮，然后选择“是”，就可以了。

![1565695662932](.\img\1565695662932.png)

成功效果图： 这个时候去远程仓库也可以看到已经将内容推送到了远程仓库了，包括在本地仓库提交的日志信息，在远程仓库也是可以看到的。

![1565695856497](.\img\1565695856497.png)

### https本地仓库推送远程仓库

#### 使用TortoiseGit

​	https和ssh操作流程大致差不多，唯一不同的是在添加地址别名的时候，URL写https的地址，不用配置密钥，然后在推送的时候会弹出框让你输入用户名和密码（基于口令方式）。



## 克隆仓库到本地

​	什么是克隆仓库，相当于将远程仓库复制一份到本地。

​	克隆方式可以使用ssh或者https方式，两者的操作是一样的，因为使用的public的仓库，任何人都可以讲远程仓库克隆到本地（因为开源文化）。

### 使用gitBash

```bash
git clone git@github.com:FallenGodCoder/learnGit.git
```

### 使用gitGUI

![1565696833414](.\img\1565696833414.png)

![1565696904885](.\img\1565696904885.png)

### 使用TortoiseGit

​	在目标文件夹中右击，选择“Git 克隆”。(窗口中的URL栏，如果在打开对话框中已经有这个信息，会自动在这一栏填入。)

![1565696984248](.\img\1565696984248.png)



## 解决文件冲突

​	远程仓库和本地的同一个文件，如果远程仓库发生改变，本地也发生了改变的情况下，如果进行“拉取pull”操作，这个时候文件会出现冲突，如果发生变化的位置两端相隔较远，git会自动帮我们合并解决这个冲突，但是如果两者位置较近，这个时候就会形成冲突文件，只能让我们手动去处理这个冲突了。

![1565698561553](.\img\1565698561553.png)

![1565698603992](.\img\1565698603992.png)

> ​	如果本地文件的版本不是远端的文件的最新版本，这个时候提交git就会报错，这个时候就需要进行拉取pull操作。

### 使用TortoiseGit

我们可以手动处理git的冲突内容，也可以使用Tortoise提供的工具完成。

右击冲突文件，选择TortoiseGit菜单=》“编辑冲突”。

处理好之后，再次右击文件，选择TortoiseGit菜单=》“解决冲突”。



## 忽略文件语法

空行或是以 # 开头的行即注释行将被忽略。

可以在前面添加正斜杠 / 忽略当前路径文件，但不包括子目录的同名文件。

可以在后面添加正斜杠 / 来忽略文件夹。

可以使用 ! 来否定忽略，即比如在前面用了 *.apk ，然后使用 !a.apk ，则这个a.apk不会被忽略。

\* 用来匹配零个或多个字符，如 *.[oa] 忽略所有以".o"或".a"结尾， *~ 忽略所有以 ~ 结尾的文件（这种文件通常被许多编辑器标记为临时文件）； [] 用来匹配括号内的任一字符，如 [abc] ，也可以在括号内加连接符，如 [0-9] 匹配0至9的数； ? 用来匹配单个字符。

看了这么多，还是应该来个栗子：

\# 忽略 .a 文件

*.a

\# 但否定忽略 lib.a, 尽管已经在前面忽略了 .a 文件

!lib.a

\# 仅在当前目录下忽略 TODO 文件， 但不包括子目录下的 subdir/TODO

/TODO

\# 忽略 build/ 文件夹下的所有文件

build/

\# 忽略 doc/notes.txt, 不包括 doc/server/arch.txt

doc/*.txt

\# 忽略所有的 .pdf 文件 在 doc/ directory 下的

doc/**/*.pdf





## 搭建私有git服务器

​	在github上，只能使用公有的public仓库，在实际项目上通常代码是不允许公开的，虽然github有private，但是要收费，总的来说还是不怎么好。所以，要使用私有远程仓库，通常情况下是搭建属于自己的私有Git服务器。 