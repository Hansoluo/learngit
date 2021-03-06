## git操作教程 ##

### `git`简介 ###

`git`是一个文件的分布式版本控制系统。

版本控制和仓库的管理有点类似。简单的仓库管理只用来管理进出物品的数量，而`git`更复杂一点，需要跟踪文件随时间变化的状态，如文本的修改历史，代码的版本更新等。

分布式是相对于集中式来说的。如果说人是集中式控制的，那么树是分布式控制的。人的大脑控制着四肢，四肢离开大脑很快失去作用；而枝条插到地里能重新长成一棵树。

树木和`git`还有一个共同点是都有分支`branch`，而分支`branch`或许是`git`里面最重要的概念。除此之外，它还有克隆`clone`（将远程仓库复制到本地）。在`github`（**一个基于web的远程仓库**）里还可以进行分叉`fork`（**复制他人的仓库**）。

它的主要功能有：

- 版本托管（首先得有个仓库，可以放置些东西）
- 版本管理（版本控制）
- 地对空传输（本地仓库和远程仓库的传输）
- 分支管理
- 多人协作
- 标签管理

### 版本托管 ###

- 学会使用命令行来进行文件路径操作，这和在Windows下powershell里运行命令行是一致的
- `mkdir`创建目录 `pwd`显示当前目录 `cd`打开该目录 `ls`列出该目录下所有文件 `cd ..`退回上一层级目录
- 设定git bash程序的起始目录，点击图标属性里修改，否则会找不到文件
- 初始化`git`仓库： `git init`
- 这样便完成`git`仓库的创建

### 版本管理 ###

- 将文件放入到该工作目录下
- 添加文件到`git`仓库：`git add <file>`
- 提交该文件：`git commit -m "XXX"`(XXX类似于对文件的说明)
- 查看仓库状态：`git status`，会显示是否有文件被修改
- 查看修改内容：`git diff`
- 查看提交历史：`git log`
- 版本回退：`git reset --hard commit_id`
- `commit_id`:上一版本是`HEAD^`，上上版本是`HEAD^^`
- `git`的工作原理是，实际上分为工作区和版本库。版本库里分为暂存区和仓库。命令`git add`只是把文件放入到暂存区，只有`git commit`才将文件放入到真正的仓库
- 每一次的提交`git commit`都以之前最后一次的`git add`的版本为准
- 丢弃工作区的更改：`git checkout -- <file>`
- 工作区删除文件 `rm <file>`
- 版本库里删除文件 `git rm <file>`，并且提交`git commit`

### 地对空传输 ###

- 添加远程仓库
- 利用SSHkey连接远程仓库
 - 在添加远程库这步操作中运行下列命令时报错：
``$ git remote add origin git@github.con:Hansoluo/learngit.git``
``fatal: Could not read from remote repository``
 - 上网寻找解决措施，过程记录如下：
     - 删除SSHkey重新添加，却仍报错
     - 修改`.gitconfig`。这才发现配置信息不对
     - 把用户名改成`github`上的用户名：`$ git config --global github.user Hansoluo`
     - 重新连接`github`远程项目，报错`fatal:remote origin already exits.`
     - 输入`$ git remote rm origin`重新连接远程仓库
     - 执行`$ git push -u origin master`报错`failed to push some refs to..`
     - 输入`$ git pull origin master`，把文件拉下来再push上去
     - 关闭问题
 - 原因可能有：
     - 配置信息和Github上不匹配
     - SSHkey有两个，一个生成的，一个安装PC版自动生成的
  - 这两个原因导致一直连接不上，后逐步修改才最终得于解决。

### 分支管理 ###

- 查看当前分支 `git branch`
- 创建本地新分支 `git branch <name>`
- 创建并切换新分支`git chenckout -b <name>`
- 将本地的新分支推送到远程仓库 `git push origin dev `，需要在当前分支下进行
- 这个命令跟推送master下的文件一致
- 合并分支到当前分支`git merge <name>` 
- 删除本地分支`git branch -d <name>` 删除前需要切换到其他分支上
- 切换分支 `git checkout <name>`
- 删除远程分支`git push origin -d <name>`
- 合并分支 `git merge --no--ff -m"XXX" <name>`

### 多人协作 ###

### 标签管理 ###


### CHANGELOG ###
----------
2017/8/2 创建V1.0版本
