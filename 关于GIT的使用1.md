# 关于GIT的使用（限Window系统）
# http://blog.jobbole.com/78960/
### 下载msysgit

msysgit是Windows版的Git，从https://git-for-windows.github.io下载（网速慢的同学请移步国内镜像），然后按默认选项安装即可。

安装完成后，在开始菜单里找到“Git”->“Git Bash”，蹦出一个类似命令行窗口的东西，就说明Git安装成功！

***

### 设置名字和Email地址
安装完成后，还需要最后一步设置，在命令行输入：

> $ git config --global user.name "Your Name"

> $ git config --global user.email "email@example.com"


### 查看配置信息
要检查已有的配置信息，可以使用命令:
> git config --list 


### Git 工作流程

#### 一般工作流程如下：
* 克隆 Git 资源作为工作目录。
* 在克隆的资源上添加或修改文件。
* 如果其他人修改了，你可以更新资源。
* 在提交前查看修改。
* 提交修改。
* 在修改完成后，如果发现错误，可以撤回提交并再次修改并提交。

### Git 创建仓库

#### git init
Git 使用 git init 命令来初始化一个 Git 仓库，Git 的很多命令都需要在 Git 的仓库中运行，所以 git init 是使用 Git 的第一个命令。
在执行完成 git init 命令后，Git 仓库会生成一个 .git 目录，该目录包含了资源的所有元数据，其他的项目目录保持不变
#### 使用方法

1. 使用当前目录作为Git仓库，我们只需使它初始化。

> git init

该命令执行完后会在当前目录生成一个 .git 目录。

2. 使用我们指定目录作为Git仓库。

> git init newrepo

初始化后，会在 newrepo 目录下会出现一个名为 .git 的目录，所有 Git 需要的数据和资源都存放在这个目录中。

***

如果当前目录下有几个文件想要纳入版本控制，需要先用 git add 命令告诉 Git 开始对这些文件进行跟踪，然后提交：

> $ git add *.c

> $ git add README

> $ git commit -m '初始化项目版本'

以上命令将目录下以 .c 结尾及 README 文件提交到仓库中。


### git clone

我们使用 git clone 从现有 Git 仓库中拷贝项目

克隆仓库的命令格式为：

> git clone <repo>

如果我们需要克隆到指定的目录，可以使用以下命令格式：

> git clone <repo> <directory>

**参数说明：**

**repo:Git 仓库**

**directory:本地目录**


*比如，要克隆 Ruby 语言的 Git 代码仓库 Grit，可以用下面的命令：*

> $ git clone git://github.com/schacon/grit.git

执行该命令后，会在当前目录下创建一个名为**grit**的目录，其中包含一个 .git 的目录，用于保存下载下来的所有版本记录。


如果要自己定义要新建的项目目录名称，可以在上面的命令末尾指定新的名字：

> $ git clone git://github.com/schacon/grit.git mygrit

**几种效果等价的git clone写法：**

> git clone http://github.com/CosmosHua/locate new

> git clone http://github.com/CosmosHua/locate.git new

> git clone git://github.com/CosmosHua/locate new

> git clone git://github.com/CosmosHua/locate.git new

