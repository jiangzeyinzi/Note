# Git Advance

开源的分布式版本管理系统(VCS)

Linus Torvalds用于管理Linux Kernel源代码

# 分布式的理解

- 本地版本控制

- 集中版本控制(CVS)：中央服务器单点故障

  ![](images/VCS1.png)

- 分布版本控制

![](images/VCS2.png)

# 存储方式

- 大多数：存储的是变更，累加所有变更得到最终的版本
- Git：修改则快照整个文件，不修改只存指针。在Git的分支操作高效、节省存储空间（1、存压缩格式 2、打包文件存储方式）

#  三个区域四种状态

- 三个区域
  - Working Directory
  - Staging Area
  - .git directory(Repository)
- 四种状态
  - Untracked（工作区）
  - Unmodified（仓库）
  - Modified（工作区）
  - Staged（暂存区）

# Git GUI

- Git GUI

  - 界面区域
    - Unstaged Changes
    - Staged Changes(Will Commit)
  - Rescan刷新
  - 双击Unstaged中的文件就可以放入Staged（或Staged Changed）
  - 在Commit Message内写message在点击Commit进行提交
  - 点击Push
  - Repository->visualize All Branch History（或在Git Bash中输入`gitk`）
- Source Tree
  - Atlassian
- EGit
  - 安装EGit插件
  - Team

## Git配置

- .gitignore

  IDE环境往往会在项目文件夹下生成一些文件，而这些文件却与源代码无关（如HBuilder会生成.project隐藏文件）。每次`git status`时都会出现这些隐藏文件，所以引入gitignore忽略这些文件。

  - OS生成的文件，如缩略图
  - 编译生成的中间文件、如可执行文件，如.obj、.exe
  - 敏感信息的配置文件，如口令配置文件
  - tmp/临时目录
  - log/日志目录

  ```
  #ignore .project created by HBuilder
  .project
  #ignore *.obj created by C
  *.obj
  ```

  ​	GitHub自带一些.gitignore文本文件

  ​	查看是哪句话忽略：`git check-ignore -v .project`

- 换行符问题

  Windows平台下当使用`git add` a时会出现Warning：

  `warning: LF will be replaced by CRLF in a. The file will have its original line endings in your working directory.`

  windows中的工作区的CRLF在放入暂存区时要换成LF

  - CR: carriage return回车，光标到首行，‘\r’=return
  - LF: line feed换行，光标下移一行，'\n'=newline
  - linux: 换行\n
  - windows: 换行\r\n
  - MAC OS: 换行\r

  **取消Warning：**

  提交时转换为LF，检出时转换为CRLF（默认，不用修改）

  `git config --global core.autocrlf true`

  允许提交包含混合换行符的文件

  `git config --global core.safecrlf false`


- 别名

  以图形的方式打印Git提交日志

  `git log --pretty=format:'%h %ad | %s%s [%an]' --graph --date=short` 

  设置别名

  `git config --global alias.st status`

  编辑在根目录(~)下的`.gitconfig`在alias下添加别名

  `cm = commit`

- 缓存凭证

  在HTTP协议下存储凭证的方法（在做add操作时可以不用重复输入GitHub的帐号密码）

  `git config --global credential.helper wincred`

## Git协议

- 本地协议

  - 克隆本地仓库

    `git clone /c/test.git`

  - 添加远程仓库的链接

    `git remote add origin /c/test.git`

  - **优**：简单。直接可以使用基于Linux的文件网络访问权限，就可以在Linux的文件服务器上放共享的仓库来完成团队协作。

  - **缺**：1、共享的文件系统难以配置 2、挂载磁盘时通过NFS访问版本库效率不高 3、设置shell权限

- Git协议

  - 克隆本地仓库

    `git clone git://server_ip/test.git`

  - 添加远程仓库的链接

    `git remote add origin git://server_ip/test.git`

  - **优**：访问速度最快（省去了加密和授权的开销）

  - **缺**：缺乏授权机制，一般只读，与其他协议配合使用，防火墙开9418端口

- HTTP协议

  - 克隆本地仓库

    `-git clone https://github.com/username/test.git`

  - 添加远程仓库的链接

    `git remote add origin https://github.com/username/test.git`

  - **优**：易上手，端口防火墙开放（http 80端口和https 443端口）

  - **缺**：传输数据效率低，基于文本传输。每次都输入用户名和密码

- **SSH协议**

  Secure Shell 密钥对

  - 克隆远程仓库

    `git clone ssh://git@github.com/username/test.git`

    `git clone git@github.com:username/test.git`

  - 添加远程仓库的链接

    `git remote add origin git@github.com:username/test.git`

  - **优**：速度较快

  - 生成**RSA**密钥对

    `ssh-Keygen -t rsa -C "your email"`

    生成id_rsa（私钥）和id_rsa.pub（公钥）

  - 在GitHub网站添加公钥id_rsa.pub

  - 使用SSH协议，克隆仓库或者添加远程链接（不需要输入用户名和密码）

- 查看使用的协议

  `git remote -v`