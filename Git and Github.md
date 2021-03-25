目的：借助Github托管项目代码

## 基本概念
仓库（Repository）：用来存放项目代码，一个项目对应一个仓库
复制克隆项目（Fork）：该Fork的项目是独立存在的
收藏（Star）
发起请求（Pull Request）：a的一个项目被B复制了，B在原来的基础上改进了这个项目，此时给A发起请求修改，B看到了这个请求，认为改得好，能修改，就同意了B的请求，同时也可以将新更新的项目合并到原仓库
关注（Watch）：关注项目，当项目更新时可以收到通知
事务卡片（Issue）：发现代码bug，但是目前没有成型代码，需要讨论时用。比如a访问b的仓库，发现代码有问题，就创建一个issue提交，b看到后可以回复

## 开源项目构建流程
1.新建Issue  提交问题/建议/想法
2.Pull Request  fork项目->修改自己仓库的项目代码->发起pull request->等待作者审核

# Git
通过git管理github托管项目代码

## 安装Git
Mac OS：终端输入：-brew install git

## Git区域分配
Git仓库（Git Repository）：最终确定的文件保存到仓库，成为一个新的版本，并且对他人可见
暂存区：暂存已经修改的文件，最后统一提交到git仓库
工作区（Working Directory）：添加、编辑、修改文件等动作

## Git基础设置
1.设置用户名
git config -global user.name '你的用户名'
2.设置用户名邮箱
git config -global user.email '你的邮箱名'                

该设置在github仓库主页显示谁提交了该文件

## 初始化一个新的Git仓库
**1.创建文件夹**
-mkdir demo01

**2.在文件夹内初始化Git（创建Git仓库）**
-cd demo01
-git init

**3.向仓库添加文件**
（1）创建文件：touch 你要添加的文件
（2）添加到暂存区：git add '文件名'
（3）将文件从暂存区提交到仓库：git commit -m '需要添加的描述'
（4）添加到远程仓库：git push

**4.修改仓库文件**
-vi 你要修改的文件

**5.删除仓库文件**
删除文件：rm 你要删除的文件
从Git中删除文件：git rm 你要删除的文件
提交操作：git commit -m'提交描述'

**6.查看基础信息**
3.查看设置
git config --list

**注意：**git config -global参数，有了这个参数，表示你这台机器上所有Git仓库都会使用这个配置，当然你也可以对某个仓库指定不同的用户名和邮箱

## Git管理远程仓库
使用远程仓库的目的：备份，实现代码共享集中化管理

### Git克隆操作
目的：将远程仓库复制到本地
代码：git clone 仓库地址

## ？无法同步
![](https://img2020.cnblogs.com/blog/2282344/202103/2282344-20210323161041709-1387639620.png)

## Github Pages 搭建网站
1.搭建个人站点 -> 创建仓库（用户名必须是：用户名.github.io）
2.在仓库下新建index.html

**注意：**
1.github pages仅支持静态网页
2.仓库里面只能是.html文件

## Project Pages项目站点
https://**用户名**.github.io/**项目名**

