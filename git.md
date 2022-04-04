# Git 基本流程

- 工作区：就是你在电脑里能看到的目录。
- 暂存区：英文叫 stage 或 index。一般存放在 .git 目录下的 index 文件（.git/index）中，所以我们把暂存区有时也叫作索引（index）。
- 版本库：工作区有一个隐藏目录 .git，这个不算工作区，而是 Git 的版本库。

![关系图](https://www.runoob.com/wp-content/uploads/2015/02/1352126739_7909.jpg)

标记为 "master" 的是 master 分支所代表的目录树  
 "HEAD" 实际是指向 master 分支的一个"游标"

![git结构](https://img-blog.csdnimg.cn/20200828142539308.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L1EwNzE3MTY4,size_16,color_FFFFFF,t_70 "git结构")

- git add 时，暂存区的目录树被更新，同时工作区修改（或新增）的文件内容被写入到对象库中的一个新的对象中，而该对象的 ID 被记录在暂存区的文件索引中。

- git commit 时，暂存区的目录树写到版本库（对象库）中，master 分支会做相应的更新。即 master 指向的目录树就是提交时暂存区的目录树。

- git reset HEAD 时，暂存区的目录树会被重写，被 master 分支指向的目录树所替换，但是工作区不受影响。

- git rm --cached < file> 命令时，会直接从暂存区删除文件，工作区则不做出改变。

- git checkout . 或者 git checkout -- < file> 命令时，会用暂存区全部或指定的文件替换工作区的文件。这个操作很危险，会清除工作区中未添加到暂存区中的改动。

- git checkout HEAD . 或者 git checkout HEAD < file> 命令时，会用 HEAD 指向的 master 分支中的全部或者部分文件替换暂存区和以及工作区中的文件。这个命令也是极具危险性的，因为不但会清除工作区中未提交的改动，也会清除暂存区中未提交的改动。

## 用户信息

```
$ git config --global user.name "John Doe"
$ git config --global user.email johndoe@example.com
```

git 的设置使用 git config 命令

```
$ git config --list
credential.helper=osxkeychain
core.repositoryformatversion=0
core.filemode=true
core.bare=false
core.logallrefupdates=true
core.ignorecase=true
core.precomposeunicode=true
```

编辑 git 配置文件

```
$ git config -e    # 针对当前仓库
$ git config -e --global   # 针对系统上所有仓库
```

## 创建仓库

```
git init
```

初始化后，会在 newrepo 目录下会出现一个名为 .git 的目录，所有 Git 需要的数据和资源都存放在这个目录中。

如果当前目录下有几个文件想要纳入版本控制，需要先用 git add 命令告诉 Git 开始对这些文件进行跟踪，然后提交

```
git add *.c
git add README
git commit -m '初始化项目版本'
```

## 添加文件

```
git add .  // 添加所有文件
git commit -m '填写本次信息' // 提交备注
git push  // 推送远程
```

常用命令
```
git add	    添加文件到暂存区
git status	查看仓库当前的状态，显示有变更的文件。
git diff	比较文件的不同，即暂存区和工作区的差异。
git commit	提交暂存区到本地仓库。
git reset	回退版本。
git rm	    删除工作区文件。
git mv	    移动或重命名工作区文件。
```


## 仓库新建分支(目录)

```
git branch testName       // 分支-名字
git checkout testName     // 切换到分支

or

git checkout -b testName  // 创建并切换到的分支下
```

## 推送分支到远程

```
git push origin testName          // 把本地分支提交到远程仓库

or

git push origin testName:testName // 分支的推送到远程-本地分支：(推送到)远程仓库上
```

## 合并你的代码

回到主分支 / 以及-把分支代码-合并到主分支项目上

```
git checkout master // 切换分支
git merge testName      // 合并分支
git push            // 推送远程
```

## 暂存代码，将当前工作区的修改暂存起来

有时候修改了代码，又要更新代码（pull）然后又不被覆盖怎么办呢？

```
git stash // 先把本地代码保存起来
git pull  // 再更新
```

那保存怎么取出来了呢？

```
git stash pop // 取出刚才的保存
然后去解决你的本地冲突就行了
```

## 撤销先前 commit

在 git push 之前， git commit 的内容后悔了怎么办呢？
或者你想回退到之前某个版本的代码，恢复到本地后可以选择覆盖和不覆盖当前的修改

假如你现在是这种情况，C 是你的 HEAD，(F)是你当前文件的状态。

```
   (F)
A-B-C
    ↑
  master
```

你想要除掉 C，并且再也不想见到它。那么你这么做：

```
git reset --hard HEAD~1
```

执行完后的结果就是：

```
 (F)
A-B
  ↑
master
```

现在 B 是 HEAD 了。因为你使用了--hard，所以你的文件被重置到 B 的状态了。
当你要撤销提交，但是保留你更改的代码信息，然后做一些修改，再提交一遍。下面看看状态的情况：

```
   (F)
A-B-C
    ↑
  master
```

那种情况下不用使用--hard：

```
git reset HEAD~1
```

来看下 HEAD 的下标：

```
   (F)
A-B-C
  ↑
master
```

在正常情况下，HEAD 都是指向最近一次提交的一个指针。当你使用 git reset HEAD~1 命令时，你告诉 Git 将 HEAD 指针往前回退一次，到上一个 commit 上。但是（除非你使用--hard 参数）你仍然没有改变文件。那么 git status 会告诉你之前提交到 C 的修改变化还会存在。之前手码的都没有丢失。
所以想要最轻微的改动，撤销你的提交的同时还保留着你的文件和索引：

```
git reset --soft HEAD~1
```

reset 恢复删除的文件

```
$ ls
A文件/  B文件/  C文件/  D文件/
```

先删除一个文件作为试验，查看操作状态会有 deleted 的文件，可以看到列表中已经剩下的三个文件

```
$ git rm A文件
rm 'static_files/abbr_data'

$ git status // '接着查看最新状态'
# On branch master
# Changes to be committed:
#   (use "git reset HEAD <file>..." to unstage)
#
#   deleted:    A文件

$ ls
B文件/  C文件/  D文件/
```

最后通过 reset 把删除的文件文件给恢复就好啦

```
$ git reset HEAD A文件
Unstaged changes after reset:
M   /A文件
```

## 本地撤销后悔了，恢复某一次的提交

1. 执行 git reflog 查看显示日志，所有 HEAD 的历史: git reflog

```
git reflog
// 以下为记录信息
002abcdgrhfkhdg HEAD@{0}: commit: 第二次提交
001abcdgrhfkhdg HEAD@{1}: commit: 第一次提交
```

2. 找到想要恢复的 SHA，执行以下恢复 ok 了:

```
git reset --hard 002abcdgrhfkhdg
```

## 回退线上某一次提交记录

1. 点开 commit 提交，找到想要回退的一次 commit id 信息

```
commit 003abcde123fghijk <复制
```

2. 重置到你某一次 commit 的版本号

```
git reset --hard 003abcde123fghijk
```

3. 以 master 分支为例，强制覆盖线上仓库的分支，此操作只适合个人的项目\*慎重做个备份（可以修改为你当前的分支）

```
git push -f -u origin master
```

## 提交错了分支该怎么办

首先当然是先回滚你的提交并保留最新的更改，然后把修改的放入暂存区，在切换到你需要推送的分支进行提交，修改内容再提出来
假设你提交到了 branch-1 的情况下

```
git reset HEAD~1
...
git stash
...
git checkout branch-2
...
git stash pop
```

紧接着做你想做的事情就好了,比如这里再进行提交信息：

```
git add
...
git commit -m "okok"
...
git push branch-2
```

但是你的 branch-1 分支多了一次不需要的提交,想要弄回来原模原样的记录：

```
git checkout branch-1
...
git push origin branch-1 -f
```
