# Git
- git init 初始化一个git文件夹
- git add 将一个文件添加到暂存区 `git add <file>`
- git commit 将暂存区的提交`git commit -m "massage"`,`git commit -m <message>`
- git status 查看状态 `git status`
- git diff 查看修改`git diff <file> `
- git log 查看版本历史
- git reset --hard HEAD^ 回退到上个版本 `git reset --hard HEAD~10`
- git reset --hard \<id> 去到某个id的版本 
- git reflog 查看历史命令
- HEAD 指向当前版本 
- git checkout -- file 丢弃工作区的修改
- git reset HEAD \<file> 可以把暂存区的修改撤销掉
- git rm 删除文件，并用commit提交修改，可以用`git checkout -- test.txt`还原
- `$ git remote add origin git@github.com:michaelliao/learngit.git`
- `$ git push -u origin master` 推送到GitHub仓库
- `git remote -v`查看远程库信息
- `$ git remote rm origin`删除库
- 要关联一个远程库，使用命令`git remote add origin git@server-name:path/repo-name.git；`
关联后，使用命令`git push -u origin master`第一次推送master分支的所有内容；
此后，每次本地提交后，只要有必要，就可以使用命令`git push origin master`推送最新修改；
- `git clone`下载一个库
****
- `$ git checkout -b dev` 创建一个dev分支，并切换到dev分支
- 相当于2命令的的效果，-b创建并切换
- `$ git branch dev` 查看分支
- `$ git checkout dev` 切换到dev分支
- `git merge dev` 合并指定分支到当前分支
- `git branch -d dev` 删除分支
- 创建并切换到新的dev分支，可以使用：
`$ git switch -c dev`
直接切换到已有的master分支，可以使用：
`$ git switch master`
- 通常，合并分支时，如果可能，Git会用Fast forward模式，但这种模式下，删除分支后，会丢掉分支信息。如果要强制禁用Fast forward模式，Git就会在merge时生成一个新的commit，这样，从分支历史上就可以看出分支信息。下面我们实战一下--no-ff方式的git merge：
- `$ git merge --no-ff -m "merge with no-ff" dev`
- `git tag <name>`对于当前commit打一个标签
- `git tag` 查看所有标签
- `git tag v0.9 f52c633` 对于某次的提交打标签
- 命令git tag -a \<tagname> -m "blablabla..."可以指定标签信息；
- git show \<tagname>可以看到说明文字
```
$ git tag -d v0.1
Deleted tag 'v0.1' (was f15b0dd)
```
删除标签
- 因为创建的标签都只存储在本地，不会自动推送到远程。所以，打错的标签可以在本地安全删除。
如果要推送某个标签到远程，使用命令git push origin \<tagname>
- $ git push origin --tags 推送所有标签

如果标签已经推送到远程，要删除远程标签就麻烦一点，先从本地删除：
`$ git tag -d v0.9`
`Deleted tag 'v0.9' (was f52c633)`
然后，从远程删除。删除命令也是push，但是格式如下：
`$ git push origin :refs/tags/v0.9`

参与开源
https://www.liaoxuefeng.com/wiki/896043488029600/900937935629664





