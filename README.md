# learn_git
[toc]
###### 本地文件管理
tip:
Git管理的文件分为：工作区，版本库，版本库又分为暂存区stage和暂存区分支master(仓库)
你执行git init的文件夹叫工作区(work)，里面的隐藏目录.git是版本库，版本库里有暂存区(index)、默认分支(master)、默认指针(HEAD)。

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

###### 本地版本管理


HEAD指向的版本就是当前版本，因此，Git允许我们在版本的历史之间穿梭，使用命令git reset --hard commit_id。

穿梭前，用git log可以查看提交历史，以便确定要回退到哪个版本。

要重返未来，用git reflog查看命令历史，以便确定要回到未来的哪个版本。

```c
git reset --hard <>
git log
git reflog
```


###### 添加远程库
tip:
要关联一个远程库，使用命令
```c
git remote add origin git@server-name:path/repo-name.git；
```
关联后，使用命令第一次推送master分支的所有内容；
```c
git push -u origin master
```

以上2个命令在github上新建版本库后会告诉你。

此后，每次本地提交后，只要有必要，就可以使用命令git push origin master推送最新修改；

分布式版本系统的最大好处之一是在本地工作完全不需要考虑远程库的存在，也就是有没有联网都可以正常工作，而SVN在没有联网的时候是拒绝干活的！当有网络的时候，再把本地提交推送一下就完成了同步，真是太方便了！

