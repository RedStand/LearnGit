

## Git学习笔记

参考：廖雪峰Git教程 https://www.liaoxuefeng.com/wiki/896043488029600

Git是一个分布式版本管理系统

#### 安装

windows安装：https://git-scm.com/downloads下载，按默认选项安装即可；

linux安装：终端输入：sudo apt-get install git







#### 常用命令

配置命令行输入：

```
git config --global user.name "Your Name"
git config --global user.email "email@example.com"
```

注意：--global使得当前计算机使用同样的配置，也可以对某一代码库进行单独配置

#### 

初始化  在工作目录下运行命令行，输入如下命令：

```
git init
```

添加文件

```
git add xxx   
```

提交

```
git commit -m "messages"
```

查看commit日志

```
git log 
git log --pretty=oneline
```

查看历史命令

```
git reflog
```

查看当前工作区状态

```
git status
```

查看当前与HEAD中的区别

```
git diff HEAD -- readme.txt
```

回退

```
git reset --hard HEAD^   回退一次
git reset --hard HEAD~10  回退10次
git reset --hard xxxxx  xxxxx为commitid  ，可回退至xxxxx
```

撤销工作区的修改：用于修改但未执行add命令

```
git checkout -- readme.txt
```

撤销暂存区的修改：用于执行add命令但未执行commit命令

```
git reset HEAD readme.txt
```

删除文件

```
git rm test.txt
```

暂存

```
git stash
git stash list
git stash pop
```

#### 远程库操作

关联远程库

```
git remote add origin git@github.com:michaelliao/learngit.git
```

推送至远程库

```
git push origin master
```

从远程库克隆

```
git clone git@github.com:michaelliao/gitskills.git
```



#### 分支管理

创建分支

方法1：

```
git checkout -b dev  创建并切换到dev分支
```

等价于

```
git branch dev     	创建dev分支
git checkout dev	切换至dev分支
```

方法2

```
git switch -c dev
```





切换分支

```
git switch master
```

查看分支

```
git branch
```

在master中合并dev分支

```
git checkout master 切换分支到master
git merge <name>
```

删除分支

```
git branch -d <name>
git branch -D <name>  在未合并时强行删除
```



将commit复制到当前分支

```
git cherry-pick <commitid>
```



查看远程库信息

```
git remote
```

```
git remote -v
```

推送分支

```
git push origin master
```

从远程dev分支中拉去dev分支

```
git checkout -b dev origin/dev
```

建立本地分支和远程分支的关联

```
git branch --set-upstream branch-name origin/branch-name
```

变基

```
git rebase
```