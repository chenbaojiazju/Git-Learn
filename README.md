# Git知识点

## 分布式git

### git 历史和基本知识

Linux的发明者linus 发明了git，git的应用场景DevOps，持续集成，Gitlab，Github

#### 创建git仓库

1. 已有项目git init
2. 新建git init project_name

#### 工作区和暂存区

1. 本地工作区

2. （git add）暂存区

3. （git commit）本地库

4. （git push）远端库 
#### commit tree blob

> commit 包含tree（根快照）

> tree就是文件夹的快照包含blob（文件）和tree（子文件夹）

> 叶子结点都是blob

> 创建文件，gitstatus没变化，必须创建文件

> 文件内容相同就是唯一的一个blob

### 特殊文件夹
#### .git

- config
- refs（分支和tags）
- objects（文件名+SHA1） 本地库文件 

#### .gitignore
vi .gitignore
### 注意事项
#### depatched head

```
git branch <branch_name> <commit_id>  # 创建分支
git branch -D <branch_name>  # 删除分支
git remote remove <repository_name>  # 删除远程库
git push origin --delete depatched-test-brach
```

### git 命令
#### git config
```
git config --global user.name ""
git config --local
git config --system
git config --list --global(local, system)
```
#### git clone

```
git clone --bare file://<local_repository_address> <repository_name>  #不带工作区
git clone --bare file://E:/Git-learn/.git zhineng
```

#### git remote

```
git remote add origin git@github.com:chenbaojiazju/Git-Learn.git
```
#### git log
```
git log --online -n4 --all --graph
```

#### git checkout

```git
git checkout -b <new_branch_name> <base_branch> #在分支上创建新的分支并切换到新分支
git checkout -- <file> # 恢复工作区和暂存区一致
```
#### git merge

```
git merge --allow-unrelated-histories
```



#### git push

```
git push origin <branch_name > #创建远程分支
git push --set-upstream origin <branch_name>
```
#### git stash

```
git stash
git stash pop #取出缓存区，并删除
git stash apply
git stash list
git stash clear
git stash drop
```

#### git cat-file

```
git cat-file -t # 版本号 识别类型
git cat-file -p sha1  # 查看内容
```
#### git diff
```
git diff  # 工作区和暂存区的差异
git diff -- file
git diff --cached # 暂存区和本地库的差异
git diff HEAD  # 工作区和本地库的差异
git diff <commit_id1> <commit_id2>
```
#### git branch
```
git branch -d
git branch -D # 强制删除没有merge的分支
```
#### git commit
```
git commit --amend  #修改当前分支最近一次提交的commit信息
git rebase -i <commit_id>
commit 合并
git rebase -i 
squash
```
#### git reset 
```
git reset HEAD
git reset HEAD <file>
git reset --hard <commit_id> #恢复暂存区工作区本地库到指定的提交版本
```

#### git rm

```
git rm <file>
```











