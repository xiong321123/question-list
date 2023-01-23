# Git快速上手
## 我自己怎么用Git维护我的项目

git init

git status

edit

git add

git commit

*git remote add origin

*git push --set-upstream origin master

git pull

git push

## 我如何通过Git参与别人的项目

fork

git clone

edit

git push

pull request

## 我如何让别人通过Git参与我的项目

## SSH

```shell
ssh-keygen -t ed25519 -C "your_email@example.com"
```

通过上面的命令在本地生成密钥对儿文件

将.pub文件上传至github

## 命令

| 命令             | 用途                | 频次 |
| ---------------- | ------------------- | ---- |
| git status       | 查看git仓库的状态   |      |
| git add          | 将文件提交给git管理 |      |
| git commit -m    | 游戏存档            |      |
| git branch       | 查看&创建分支       |      |
| git checkout     | 切换分支            |      |
| git branch -d/-D | 删除分支            |      |
| git pull         | 将源拉取到本地      |      |
| git push         | 将本地推送至源      |      |

## 已知问题
**看不到.git**

因为.git默认是隐藏的，所以每个人电脑上关于隐藏文件的查看设置不同，可能会看不到。

解决：

1. 搜索关于如何查看隐藏文件，如何在vscode中看到.git文件夹等内容，自行解决；
2. 在运行了`git init`的文件夹内执行`git status`，如果有返回结果，表明git初始化成功了。

**初始化成功后，Git和GitHub关联失败**
将对应GitHub仓库上的SSH下面的地址复制，粘贴到powershell当前前面目录下，回车运行时，出现了下面报错：
fatal: unable to access 'https://github.com/xiong321123/git.git/': 0penSSL SSL read: Connection was reset, errno 10054

解决：见视频中00:51及以后的演示
1.生成密码对。
在 powersheer中输入：ssh-keygen -t ed25519 -C "your@email.com" （这里的邮箱地址应该是你注册GitHub的邮箱地址）并按下回车。就在后面提示的文件夹（此文件夹位置需要注意，后面要用到）中生成了密码对。
后面直接回车，就生成了一对密码文件。
2.复制密码。
进入到刚才生成密码对的文件夹中，用记事本打开其中一个带后缀为pub的文件，全选并复制其中的内容。

3.将密码上传到gitHub。
进入自己的GitHub主页，点击右上角自己的头像，点击弹出的settings，再点击左侧的SSH and GPG keys界面，再点击绿色的new ssh key进行创建新的密码。Title可以随意命名，Key下面的方框中粘贴刚刚复制的内容。再点击 Add SSH key。输入GitHub密码以后，就配对成功。

后面再将对应GitHub仓库上的SSH下面的地址复制，粘贴到powershell当前前面目录下，回车运行时，原本的问题就不会出现，就能顺利关联git和GitHub。
