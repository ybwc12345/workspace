# workspace

## 介绍
本项目主要用于介绍git对于远程仓库的链接和给i他的基本操作和如何用仓库进行团队操作。

### 安装Git

- https://git-scm.com/downloads
- 打开这个网址，选择自己的系统进行安装。

### 创建my first git workspace

- 在任意位置创建名为”workspace“的文件夹–一般我们创建的文件夹名称与项目名称一致–
- 打开命令框：
- Windows: ``cmd``
- Mac&Linux: 终端
- 用``cd``指令进入到workspace『Windows用户需要先用cd指令进入到相应的系统盘后再进入到workspace中，如``cd d:\\``&& ``cd workspace``』
- 接着输入命令``git init``
- 我们的第一个git workspace就建立好了

### 在本地与gitee建立连接

#### 前期操作

- 设置全局用户名和邮箱（需要和gitee上注册的一致，可以去个人中心查看）
- ``git config --global user.name<name>``
- ``git config --global user.email<email address>``

#### 添加项目和提交项目	

- https方式
  - 回到workspace,输入：``git remote add origin https://xxxxx.git``『添加远程仓库并设置其名称为origin，``http://xxxxx.git``就是一开始的路径』
  - ``git pull origin master``『将远程仓库origin中的master分支中的文件拉取到当前workspace目录』
  - ``git rm -f xxxx``移除xxxx项目
  - 试着在workspace目录下新建一个文件
  - 输入``git status`` 查看当前目录下各文件的状态
  - 输入``git add .``将所有修改的文件添加到预提交的目录『我们几乎不会一个个添加，都是一键添加，所以之前写的.gitignore就起了很大的作用』
  - 输入``git commit -m "my first commit"``『提交所有已经预提交的文件并赋上"my first commit"说明，==这个是必须的,注意双引号是英文半角符==』
  - ``git logs``查看日志
  - 输入``git push origin master:master``『将本地master分支推送到远程仓库origin的master分支上，后一个master是远程仓库的，若要push当前的分支可以省略：和其前面的参数』
  - 输入``git branch``可以查看当前workspace中的所有分支，标*的为当前的分支		

- 

#### 

## 
