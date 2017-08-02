## git操作教程 ##



### 分支管理 ###
- 查看当前分支 `git branch`
- 创建本地新分支 `git branch <name>`
- 将本地的新分支推送到远程仓库 `git push origin dev `，需要在当前分支下进行
- 这个命令跟推送master下的文件一致
- 合并分支到当前分支`git merge <name>` 
- 删除本地分支`git branch -d <name>` 删除前需要切换到其他分支上
- 切换分支 `git checkout <name>`
- 删除远程分支`git push origin -d <name>`