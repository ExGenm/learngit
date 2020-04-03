# learn_git
2.first diff
3.Working Directory,Stage and Repository

tip:
Git管理的文件分为：工作区，版本库，版本库又分为暂存区stage和暂存区分支master(仓库)

工作区>>>>暂存区>>>>仓库

git add把文件从工作区>>>>暂存区，git commit把文件从暂存区>>>>仓库，

git diff查看工作区和暂存区差异，

git diff --cached查看暂存区和仓库差异，

git diff HEAD 查看工作区和仓库的差异，

git add的反向命令git checkout，撤销工作区修改，即把暂存区最新版本转移到工作区，

git commit的反向命令git reset HEAD，就是把仓库最新版本转移到暂存区。

你执行git init的文件夹叫工作区(work)，里面的隐藏目录.git是版本库，版本库里有暂存区(index)、默认分支(master)、默认指针(HEAD)。

```c
git add : work >> index
git checkout : work << index
git commit : index >> HEAD
git reset HEAD : index << HEAD
    
git diff : diff work and stage 
git diff -- cached : diff stage and HEAD
git diff HEAD : diff work and HEAD
```


