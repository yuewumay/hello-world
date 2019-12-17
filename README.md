# Hello-World
Trial: Learning by yourself

## Introduction
Hi Humans!
**May** here. I am a boring PhD student in *Economics* who has passion for life. I pursue my doctoral degree at [HKU!](https://www.hku.hk/). 
I don't like coding at all but I have to master the skill which is required as necessary for a so-called "qualified" PhD candidate on the job market. That's why I am here. Honestly speaking, it is not out of **love** though,  please rest assured that I will commit to the learning process since I am **determined** and **persistent** once I have decided. Finally, I would like to share one of my favorite quotes with you from the acknowledged novel **The Shawshank Redemption**, which has been adapted to a well-known movie, that is:

> Hope is a good thing, maybe the best of things, and no good thing ever dies. - Stephen Edwin King
> ~~- Stephen Edwin King~~


## Review
### 1st Week
1. Tutorial:
* Guides at bilibili: [Introduction to GitHub](https://www.bilibili.com/video/av24441039)

2. Remarks:
* 本地：工作区（写代码）== `git add` == 暂存区（临时储存）== `git commit` == 本地库（历史版本）
* GitHub: 代码托管中心，帮助维护**远程库**；Git:帮助维护**本地库**，在本地做版本控制
* 本地**本地库**与代码托管中心**远程库**如何交互？
  * 团队内: A: 本地库 == `push` == 远程库; B: 远程库 == `clone` == 本地库; B加入团队: 本地库 == `push` == 远程库; A: 远程库 == `pull` == 本地库
  * 跨团队: C: 远程库1 == `fork` == 远程库2; C: 远程库2 == `clone` == 本地库2; C: 本地库2 == `push` == 远程库2; A:远程库2 == `pull request` == `审核` == `merge` == 远程库1; A: 远程库1 == `pull` == 本地库1
  
3. Steps for basic set-up:
* 安装Git程序
  * Git Bash here: 在当前目录下打开Git命令行窗口
* 本地库初始化：git init
* 设置签名（区分不同开发人员信息）：git config
  * Username: may_pro（项目级别）/glb（系统用户级别）
  * Useremail: goodmorning_pro（项目级别）/glb（系统用户级别）@may.com
* 查看状态：git status
* **此步需要联结到特定的编辑器**
* 把需要track的文件或工作区的“新建/修改”放到转存区：git add
* 将暂存区的内容提交到本地库：git commit
  * 输入提交message：可以直接用 git commit -m "Commit Message"
* 创建远程库
  * 登录GitHub: 创建repository
  * 复制该远程库http型地址
* 在本地创建远程库地址别名: git remote add 
  * 别名起为origin
* 推送：git push
* 克隆：git clone
  * 完整把远程库下载到本地
  * 创建origin地址别名
  * 初始化本地库
* 可以实现本地修改，提交到本地库: git add 和 git commit
* 接受邀请，成为团队collaborator
* 可以实现本地修改提交到远程库: git push
* 拉取:
  * fetch: git fetch
  * merge: git merge
  * 若修改比较简单，可以直接使用 git pull 合并两步操作

4. Codes for basic set-up:
```javascript
$ ll 查看当前目录下资源
$ cd LaTeXlearning/ 进入特定工作区
$ ll
$ ls -lA 带隐藏资源
$ mkdir Mylearning 新建项目目录，在开发此项目过程中需要Git去做版本控制
$ ll 这一次查看，相比前次，出现了新建的项目目录
$ cd Mylearning/
$ git init 出现了一个隐藏资源，需要`ls -lA`才能查看
$ ll .git/ 能查看初始化本地库之后的效果，此目录中存放的子目录及文件，禁止胡乱修改删除
$ git config user.name may_pro 设置签名
$ git config user.email goodmorning_pro@may.com
$ git config --global user.name may_glb
$ git config --global user.email goodmorning_glb@may.com
$ git status 看工作区、暂存区、本地库状态
$ vim good.txt 使用vim编辑器创建一个txt文件 **（这一步如何使用其它编辑器？）**
$ git status 这一次查看，相比前次，出现了有待tracked的文件，但还没有放到暂存区
$ git add good.txt 
$ git status 这一次查看，相比前次，将文件添加到暂存区
$ git commit -m "Commit Message" good.txt 提交到本地库；已经tracked的文件，可以直接commit,但直接commit就不可撤销了;可被commit的文件显示绿色
$ git status
$ git remote -v 初次查看，没有任何地址别名
$ git remote add origin https://github.com/yuewumay/Mylearning.git 给该远程库地址命名为origin
$ git remote -v 这一次查看，相比前次，能看到用于fetch和push的两个地址
$ git push origin master 这句命令 + 远程库别名 + 指定需要推送的相应分支，从本地master到远程master
$ cd .. 先退出原来的工作目录
$ mkdir Herlearning 新建一个本地工作目录
$ cd Herlearning/ 进入此新目录
$ git clone https://github.com/yuewumay/hello-world.git  这句命令 + 远程库地址，完成了从远程到本地的克隆
$ pwd 查看现在位于什么地方
$ cd ../../Mylearning 先退出目前的工作目录，再进入最初的工作目录
$ git fetch origin master 只是把远程的内容下载到本地，并未更改本地工作区的文件
$ git checkout origin/master 看一看下载下来的东西在哪里，长什么样子
$ git checkout master 再切换回去；看好下载更新的文件之后，再去做合并
$ git merge origin/master 把远程的master合并到本地的master；合并完成后本地就有更新的内容了
```

### 2nd Week 
1. Tutorial: 
* Guides at GitHub: [Hello World](https://guides.github.com/activities/hello-world/)
* Guides at GitHub: Understanding the [GitHub flow](https://guides.github.com/introduction/flow/)
  * Branch name should be descriptive so that others can see what is being worked on.
* Guides at GitHub: Mastering [Markdown](https://guides.github.com/features/mastering-markdown/)
  * Markdown can be used in most places around GitHub like Comments in Issues and Pull Requests and Files with the `.md` or `.markdown` exension.  
* More references at GitHub: [Writing on GitHub](https://help.github.com/en/github/writing-on-github)

2. Basic actions to be conducted in GitHub:
* Create a new repository
  * Hello World repository
* Create a new branch
  * readme-edits
* Make and commit changes (in the branch)
* Open a Pull Request
  * Propose your changes (showing the difference)
  * Request the review from others (asking for feedback from other by using @ in the Pull Request message)
* Merge your Pull Request (by yourself to be familiar with the GitHub flow before cooperating with others)
  * Branch can be deleted after being merged successfully.
  * Merged after accepted by reviewers
 
3. Remarks:
* GitHub: Code hosting platform for version control and collaboration.
* Repository: A place containing anything you need to organize a project.
* Commits: Saved changes.

### 3rd Week
1. Task:

Objectives   | Progress (All done)
------------ | -------------
熟练掌握Markdown | 尝试使用Text; Lists; Images; Headers & Quotes; Code; Table
寻找并使用能编辑Markdown的编辑器 | Microsoft VS Code
Git和GitHub基本使用 | 能提交代码; 能提交Issue; 能提交Pull Request

2. Tutorial:
* 知乎：[主流Markdown编辑器推荐](https://zhuanlan.zhihu.com/p/69210764)
* 知乎：[使用vscode开始Markdown写作之旅](https://zhuanlan.zhihu.com/p/56943330)
* Guides at GitHub: [Mastering Issues](https://guides.github.com/features/issues/)

### 4th Week
1. Task: 
- [] Catch up with the updates in Repository


### Problems
1. Quotes：即便将图1的代码复制粘贴过来，出来的效果也不是图2；最后我是让“-”紧随其后而非另起一行实现的。
![Quotes1](https://github.com/yuewumay/hello-world/blob/master/Quotes1.png)
![Quotes2](https://github.com/yuewumay/hello-world/blob/master/Quotes2.png)
2. 如何将Git Bash与类似vim的其它编辑器串联起来？
