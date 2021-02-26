# Git的使用

## 配置

```bash
# Git配置文件位于根目录(~/)下
$ vim ~/.gitconfig

# 配置提交代码时的用户信息
$ git config [--global] user.name <name>
$ git config [--global] user.email <email address>

# 显示当前的Git配置 (按Q退出)
$ git config --list
```

## 文件添加与上传

```bash
$ mkdir <new folder>
$ cd <new folder>

# 初始化仓库
$ git init

# 初始化完成后目录中多了 .git 隐藏目录
$ ls -a
.    ..   .git

# 添加文件到暂存区
$ git add <file name>

# 添加项目中所有变动的文件
$ git add --all

# 从暂存区提交到代码仓库
$ git commit -m <message>

# 查看提交信息
$ git log

# 查看与上次commit的区别
$ git diff

# 删除工作区文件
$ git rm <file name>
```

## 版本回退

通过 `git log`命令可以查看往期提交记录, 

```bash
$ git log --pretty=oneline

d7f37086ef4e66ee18003236d25878ff78470d57 (HEAD -> master) udpate
589ab062ea7d625ce55904a08cb179d8839d0c47 add more text
a69f4ccdb24250a7ae065b413bd1f9da021f586c add some text
82c174a45b70f66251eee41b51f5ecd6340ea3e4 1st commit
```

注意`HEAD`表示当前版本, 上一个版本即为`HEAD^`, 往上n个版本记为`HEAD^n`. 想要退回到上一个版本, 可用`git reset`命令

```bash
$ git reset --hard HEAD^
```

如果又想回到新版本, 

```bash
# 显示历史记录
$ git reflog
# 重置
$ git reset --hard d7f37
```

## 版本还原

```bash
# 用版本库里的版本替换工作区的版本
$ git checkout -- <file name>
```

