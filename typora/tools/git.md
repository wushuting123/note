# 笔记说明

[xxx]表示需要根据实际情况替换的内容

# 常用命令

## 创建git仓库

```shell
git init
```



## 添加到暂存区

```shell
git add .
```



## 撤销添加到暂存区

```shell
git reset HEAD
```



## 提交到本地仓库

```shell
git commit -m '[committext]'
```



## 查看文件状态

```shell
git status
```



## 查看日志

```shell
git log
```



## 本地仓库管理github仓库并命名

```shell
git remote add [name] [github_url]
```



## 从远程仓库拉取

```shell
git pull [name] [branch]
```



## 提交到本地仓库

```shell
git push [name] [branch]
```



# 配置

## 配置本地git仓库的默认分组

```shell
git config --global init.defaultBranch [defaultbranch]
```



## 忽略文件

在本地仓库根目录下（与.git文件同级）新建文件.gitignore

### 配置示例

```
*[ignorecontent]
```

### mac

需要忽略.DS_Store文件

```
*.DS_Store
```



# github

