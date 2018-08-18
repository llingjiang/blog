# github入门
- github
小白的技术&amp;生活博客
## git速成
### 什么是git
Git是Linux发明者Linus开发的一款新时代的版本控制系统。
### Git具体命令
**提醒**：在进行任何Git操作之前，都要先切换到Git仓库目录，也就是先要切换到项目的文件夹目录下。
#### git status
查看状态，这时候提示当前目录还不是一个仓库；
#### git init
初始化git仓库，test目录已经是一个仓库
这时候输入git status ，默认在master分支；a.md文件Untracked files，就是说a.md这个文件没有被跟踪，还没有提交到git仓库里，而且提示你可以使用git add这个命令去操作你想要提交的文件。
#### git add
git add a.md 提交a.md这个文件，然后输入git status，这时候提示以下文件changes to be committed，意思就是a.md文件已经被提交了。
#### git commit
输入 git commit -m'first commit'，commit为提交的意思，'-m'代表是提交信息，执行了以上命令代表我们正式进行了第一次提交
#### git log
git log 可以查看所有产生的commit记录，所以可以看到产生了一条commit记录；
#### git add & git commit
git add 先把改动添加到一个[暂存区]，可以理解为一个缓存区域，可以临时保存改动；而git commit 才是真正的提交；好处：防止误提交；
#### git branch
branch为分支的意思，分支的概念很重要，尤其在团队协作的时候，假设俩个人在做同一个项目，分支保证俩个人能协作的最大利器；
执行git init 初始化之后git仓库会自动生成一个默认主分支master，也是你所在的分支也是基于实际开发环境下的分支，一般情况下master分支不会轻易直接在上面操作的，可以输入git branch查看当前分支情况。*号表示当前所在的分支。
#### git branch a
新建分支
#### git checkout a
切换分支到a分支
#### git checkout -b a
新建一个分支，并且自动切换到a分支 
#### git merge
合并分支。
##### 针对这个情况首先要分俩步
1. 切换到要合并的分支比如master
2. 执行git merge a意思是把a分支代码合并到master分支上；为什么说不出意外就是因为这个时候可能有冲突而合并失败。
#### git branch -d
删除分支； git branch -d a，删除a分支
#### git tag
##### git tag v1.0
代表在当前状态下新建了一个v1.0的标签
##### git tag
查看历史tag记录
#### git checkout v1.0
切换到v1.0tag的代码状态
以上内容仅仅是对本地Git仓库进行操作

##github上提交代码
### SSH
一种网络协议，用于计算机之间的加密登录
### Git 分支管理
#### 分支的概念
#### 分支的常用操作
##### 新建一个分支
git branch develop
 提醒：新建分支的命令是基于当前所在的分支的基础上进行的，即以上是基于master分支新建了一个叫做develop的分支，此时develop分支的内容和master分支的内容一模一样。如果你有A、B、C三个分支，三个分支分别是三个同学的，内容不一样，如果你当前是在B分支，如果执行新建命令的时候，新建分支的内容和B分支是一样的
 ##### 切换到develop分支
 git checkout develop
 ##### 合并以上俩步，即新建分支并且自动切换到这个分支上
 git checkout -b develop
 ##### 把分支推送到远程仓库
 git push origin develop
 ##### 并且取别名为develop2
 git push origin develop：develop2
 但是强烈不建议这样做，这会导致混乱，很难管理，所以建议本地的分支和远程的分支保持一致
 ##### 查看本地分支列表
 git branch
 ##### 查看远程分支列表
 git branch -r
 ##### 删除本地分支
 git branch -d develop
 git branch -D develop （强制删除）
 ##### 删除远程分支
 git push origin：develop
