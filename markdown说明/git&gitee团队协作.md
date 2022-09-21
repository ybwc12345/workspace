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

- https方式访问
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
  - comit错了需要进行状态回滚	

- SSH方式访问
  - 在命令终端输入``ssh-keygen -t ed25519 -C "xxxxx@xxx.com"``『``ed25519``为密钥类型，``“xxxxx@xxx.com”``为公钥名称，一般用你注册gitee的邮箱来命名』
  - 然后按三次回车
  - ``cat ~/.ssh/``
  - 查看公钥（id_ed25519.pub）和私钥（id_ed25519）
  - 将公钥上传到gitee上
  - ``ssh -T git@gitee.com``进行验证
  - 使用只需要``git remote add origin git@gitee.com:xxxx/xxxx.git``

### 参与团队仓库内容操作

- 首先前往当前地址https://gitee.com/SoulDrinker/ai-team-library点击**fork**，fork到自己的仓库
- 与之前一样在本地建立与gitee的连接，是==自己仓库中的fork==
- 为了方便同步，我们可以再添加一个远程仓库
- ``git remote add main https://gitee.com/SoulDrinker/ai-team-library.git``
- 之后需要**push**到自己仓库的**fork**之前都需要``git pull main master``,做一次同步，再``git push origin master``
- 然后到==自己仓库==的**fork**中点击**pull request**,写好内容等待审核
- 当然==每次开始创作内容时也要同步一次==，不然你的内容可能会被覆盖

### 而外功能介绍—创建分支

- https://www.liaoxuefeng.com/wiki/896043488029600/900003767775424
- 可以参考廖雪峰网站上的图示
- ``git checkout-b dev``『登记一个名为dev的分支并切换至dev分支，相当于``git branch dev``&``git checkout dev``』
- ``git branch``
- ``git checkout master``切换回主线
- ``git merge dev``将dev分支合并到当前分支
- ``git checkout-d dev``删除dev分支

### 而外功能介绍—本地版本回退

- ``git log``查看日志
- 选择你想回退的版本
- ``git reset xxxxx``
- 当然也可以``git rest HEAD~x``『x表示往前退回多少个版本，需要回到上一个只需要``git rest HEAD~1``』
- ==如果push到gitee上就gg了，你只能手动的去一个个更改==

#### 