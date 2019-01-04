# Git使用

一个不错的git教程。

https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000

## git简介

git是分布式管理系统。git有个本地仓库，使用本地仓库不用联网，在脱机状态下就可正常的使用本地仓库；git还有个联网的代码仓库（如github)，多个人员可以同时工作于一个项目中，通过使用push命令，即可保证本地仓库和代码仓库的数据同步。

## git初次配置

git的配置文件为/etc/gitconfig或~/.gitconfig。

使用一下命令进行初次配置

```
#配置个人用户名和你的电子邮箱，每次Push的时候使用这两条引用，使用说明是谁push了这两次更新。
git config --global user.name "Alex"
git config --global user.emial leecol.wowtime@gmail.com
#查阅配置信息
git config --list
```

## git中的文件状态

### 已跟踪或未跟踪

- 已跟踪

  已跟踪指本来就以纳入版本控制系统中的文件。

  此类文件有三个状态：

  1. 未修改
  2. 以修改，未放入暂存区。
  3. 处于暂存区。

- 未跟踪

  指没有纳入版本控制系统中的文件。

## git的基础操作

```git add file.txt
#将file.txt加入到暂存区，
git add file.txt
#使用status命令查看状态,可以看到file.txt此时的状态为：需要提交状态
git status
#提交暂存区中的文件，存入本地仓库中
git commit -m "加入file.txt"
```

## git查看提交历史

```
git log

##显示最近2次改动的具体内容
git log -p -2

##显示改动的简要内容
git -log --stat

##只以一行显示
git log --pretty=oneline

git log --pretty=format:"%h - %an, %ar : %s"
```

## git撤销操作

```
#修改最后一次提交
git submit --amend
#取消以暂存的文件
git reset HEAD file.txt
#取消对文件的修改
git checkout --file.txt
```

## 远程仓库的使用

> 安装ssh
>
> ```
> sudo pacman -S openssh
> ssh-keygen
> cat ~/.ssh/*pub
> #把cat的内容复制到你的github账号中的ssh公钥里。
> ssh -T git@github.com
> #看到hi+用户名表明设置成功。
> ```
>
>

在github中创建一个新的仓库，把新的远程仓库与本地仓库关联

```
git remote add origin <Clone with SSH>
```

