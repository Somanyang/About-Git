# About-Git
## 1、git 切换远程分支
#### a、从远程仓库git clone 到本地，进入目录master
#### b、git branch -a 查看远程仓库的分支
####  remotes/origin/HEAD
####  remotes/origin/dev
#### c、切换到 dev 使用命令 git checkout -b dev origin/dev   （dev为本地分支，origin/dev为远程分支，直接切换到分支）

## 2、git与github连接

### a、创建ssh key
#### 为了让github能够识别是我们自己上传文件，需要创建ssh key
#### $ ssh-keygen -t rsa -C "your_email@youremail.com"
#### 在输入后会询问你是否保存创建的ssh key，点回车就好，然后要求输入你要设置的密码，如果直接回车表示不设密码。然后会提示你ssh key已经创建好
### b、将ssh可以写入github
#### 创建好本地的ssh key后，我们需要让github知道这个ssh key是我们自己，所以需要将生成的ssh key复制出来，写入github，在mac下在终端输入
#### cat ~/.ssh/id_rsa.pub
#### 此时在终端会显示出刚刚创建好的ssh key，复制出来，在github在点击头像，然后点击setting，在找到SSH and GPG keys，创建一个new ssh key，然后将刚刚复制的ssh key填入即可
### c、验证是否连接成功
#### $ ssh -T git@github.com
#### 如果回车看到：You’ve successfully authenticated, but GitHub does not provide shell access 。表示已成功连上github。
### d、设置username和email
#### 在把本项目上传到github之前还需要分别输入设置username和email，因为github每次commit都会记录他们。所以分别输入如下命令：
#### $ git config --global user.name "your name"
#### $ git config --global user.email "your_email@youremail.com"

