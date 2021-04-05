### 创建将本地的项目关联到github上去？
```
echo "# ProgramBooks" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:codeGoogler/ProgramBooks.git
git push -u origin main
```

### 版本控制工具：
##### 1，GIT是分布式版本控制系统
- 1、commmit 本地
- 2、push 远端
#### 一，注册
[Git注册教程](http://jingyan.baidu.com/article/455a9950abe0ada167277864.html)
#### 二，删除仓库
- 1、选中要删除的仓库，点击右上角的按钮中的setting，输入仓库名称，删除
#### 三，创建仓库
- 1，输入仓库名称
- 2，是否在仓库中添加一个readme文档
#### 四，克隆代码
- 1，使用SSH协议，SSH和HTTPS（传输加密协议，每次都要输入用户名和密码）
- 2，将地址复制
- ，进入你要放置代码的地方，输入git clone 粘贴地址
#### 五，配置SSH
- 1，ssh-keygen -t rsa -C 邮箱地址（Linux命令 "注册时所输入的邮箱")
- 2，打开id_rsa.pub（公钥），复制代码
- 3，回到github，点击右上角图标中的settings
- 4，点击SSH and GPG keys，点击New SSH key，输入title，粘贴key
- 5，点击添加
- 6，git clone 粘贴地址
#### 六、同步代码（如何将修改的代码提交到远端）
- （1）、进入目录
- （2）、设置用户名和密码
  - git config --global user.name @前面的用户名
  - git config --global user.email emailAddress
- （3）、git status 查看文件修改的状态
- （4）、git add . （添加文件必须用git add . 及git commit -a -m '注释信息' git push(但是远端必须有当前的分支才能进行push,因此需要映射分支) 修改文件用git commit -a -m '注释信息'）
- （5）、git commit -a -m "注释信息" 不管是添加还是修改都提交上去，忘记输入 -m ，按esc输入：q或：wq（保存并退出）退出(-a代表add添加的缩写 -m代表注释信息)
- （6）、git commit 提交
- （7）、git push 提交到远端
- （8）、git add . 把当前文件夹下所有的文件添加到索引仓库里进行跟踪修改
(只修改文件里的内容不需要git add . 只有更新了文件才需要)
- （9）、git pull 从远端到本地
#### 七、分支（多人合作，一般在分支上开发，在主干上发布）
- （1）、git branch 查看分支
- （2）、git checkout -b "20161128-footballSNS-bugflx" 从当前分支上拉一个分支出来
- （3）、git checkout master 切换分支 
- （4）、git push --set-upstream origin "分支名" 映射分支 （在远端创建一个分支 远端有分支才能进行push，合并等操作）
- （5）、git diff 查看改动（difference）
- （6）、命令git checkout -- readme.txt意思就是，把readme.txt文件在工作区的修改全部撤 销，这里有两种情况：
   - 1） - 、一种是readme.txt自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；
   - 2）、一种是readme.txt已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。  
总之，就是让这个文件回到最近一次git commit或git add时的状态。
   - 3）、pwd 用于显示当前目录
   - 4）、ls -ah 用于查看隐藏的目录
   - 5）、git checkout -- file命令中的--很重要，没有--，就变成了“切换到另一个分支”的命令，我们在后面的分支管理中会再次遇到git checkout命令。
   - 6）、用命令git reset HEAD file可以把暂存区的修改撤销掉（unstage），重新放回工作区
   - 7）、git reset命令既可以回退版本，也可以把暂存区的修改回退到工作区。当我们用HEAD时，表示最新的版本
   - 8）、git checkout其实是用版本库里的版本替换工作区的版本，无论工作区是修改还是删除，都可以“一键还原”。
   - 9）、命令git rm用于删除一个文件。
- （7）、把本地库的内容推送到远程，用git push命令，实际上是把当前分支master推送到远程。
由于远程库是空的，我们第一次推送master分支时，加上了-u参数，Git不但会把本地的master分支内容推送的远程新的master分支，还会把本地的master分支和远程的master分支关联起来，在以后的推送或者拉取时就可以简化命令。
git push origin master 推送到远程库
注：
     - （1）、要关联一个远程库，使用命令
        - git remote add origin git@server-name:path/repo-name.git；
     - （2）、关联后，使用命令
       - git push -u origin master第一次推送master分支的所有内容；
     - （3）、此后，每次本地提交后，只要有必要，就可以使用命令
       - git push origin master推送最新修改；
#### 八、diff代码 (找不同)

### 九、merge代码(需有管理员权限)
- (1)、git merge 20161128-footballSNS （merge的同时进行了commit的操作）
- (2)、git push
### 十、git的简写
   网站：git.xx

###### 语法：git config -global alias.st ststus 以status为例
- 一般用 co 表示 checkout
-  一般用 ci 表示 commit
- 一般用 br 表示 branch
- 一般用 st 表示 status
### 十一，添加项目到远程仓
- 1、初始化一个仓库：git init 
- 2、添加一个仓库到本地： git add README.md 
- 3、给仓库添加注释：git commit -m "注释内容"
- 4、关联到远端仓库：git remote add origin git@github.com:yuhuiyong/11yuekao.git
或则     gulp push --set-upstream origin 分支名（在远端建立一个分支也就是分支映射 然后再git push添加到远端） 
- 5、把代码添加到远端仓库：git push -u origin master
注：只需要初始化一次仓库，之后就可以直接添加
pull：
自己的分支从远端（A）拉到本地（B）
步骤：
1、在B分支下 git merge A 
2、然后git push 把B和A的代码和在一起
3、最后 git pull 

### git命令
- 查看远程仓库：$ git remote –v
- 删除远程仓库：$ git remote rm [name]
- 拉取远程仓库：$ git pull [remoteName] [localBranchName]
- 推送远程仓库：$ git push [remoteName] [localBranchName]
-  分支(branch)操作相关命令查看本地分支：$ git branch
- 查看远程分支：$ git branch –r
- 创建本地分支：$ git branch [name] <font  color=red >----注意新分支创建后不会自动切换为当前分支<font>
- 创建新分支并立即切换到新分支：$ git checkout -b [name]
- 删除分支：$ git branch -d [name] ---- -d选项只能删除已经参与了合并的分支，对于未有合并的分 支是无法删除的。如果想强制删除一个分支，可以使用-D选项
- 合并分支：$ git merge [name]
- ----将名称为[name]的分支与当前分支合并创建远程分支
- (本地分支push到远程)：$ git push origin [name]
- 删除远程分支：$ git push origin :heads/[name]
- 版本(tag)操作相关命令查看版本：$ git tag
- 创建版本：$ git tag [name]
- 删除版本：$ git tag -d [name]
- 查看远程版本：$ git tag –r
- 创建远程版本(本地版本push到远程)：$ git push origin [name]
- 删除远程版本：$ git push origin :refs/tags/[name]
- 子模块(submodule)相关操作命令添加子模块：$ git submodule add [url] [path]
- 初始化子模块：$ git submodule init ----只在首次检出仓库时运行一次就行
- 更新子模块：$ git submodule update ----每次更新或切换分支后都需要运行一下
- 删除子模块：$ git rm --cached [path]

#### 出现的问题：
- 一、提交代码到远程仓时遇到『Everything up-to-date』
     详解见http://blog.csdn.net/myhuashengmi/article/details/52197566
- 二、密钥的生成
      详解见 http://blog.csdn.net/hustpzb/article/details/8230454/

 














