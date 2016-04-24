---
layout: post
title: git常用命令
---

### 1. 远程操作

- _克隆某分支仓库_

```
$ git clone -b <branch> <remote_repo>
```

- _显示远程主机详细信息_

```
$ git remote show origin
```

- _推送新分支dev到远程主机分支dev_

```
$ git push origin dev:dev
```

- _标签推送_

```
$ git push origin v1.5
or
$ git push origin --tags
```


### 2. 本地操作

- _新建分支dev并切换到该分支_

```
$ git checkout -b dev
or
$ git branch dev
$ git checkout dev
```

- _重命名分支dev为develop_

```
$ git branch -m dev develop
```

- _提交时显示所有diff信息_

```
$ git commit -v
```

- _删除分支_

```
$ git branch -d [name]
```

### 3. git stash 用法


- _备份当前的工作区的内容，从最近的一次提交中读取相关内容，让工作区保证和上次提交的内容一致。同时，将当前的工作区内容保存到Git栈中_

```
$ git stash
```

- _显示Git栈内的所有备份，可以利用这个列表来决定从那个地方恢复_

```
$ git stash list
```

- _将工作应用回来_

```
$ git stash apply
```

- _从Git栈中读取最近一次保存的内容，恢复工作区的相关内容。由于可能存在多个Stash的内容，所以用栈来管理，pop会从最近的一个stash中读取内容并恢复_

```
$ git stash pop
```

- _指定版本号为stash@{1}的工作取出来_

```
$ git stash apply stash@{1}
```

- _清空Git栈_

```
$ git stash clear
```



