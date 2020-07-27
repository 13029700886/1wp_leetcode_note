

## 上传文件详细步骤

```git

git config --global user.name "13029700886"     ->"Your Name"

git config --global user.email "1285132564@qq.com"     -> "email@example.com"
```



  

**1、**在用户主目录下，看看有没有.ssh目录，如果有，再看看这个目录下有没有id_rsa和id_rsa.pub这两个文件，如果已经有了，可直接跳到下一步。如果没有，打开Shell（Windows下打开GitBash），创建SSH Key，密码可以不设置直接回车



```git
$ ssh-keygen -t rsa -C "youremail@example.com"
```

如果一切顺利的话，可以在用户主目录里找到 .ssh 目录，里面有 id_rsa 和 id_rsa.pub 两个文件，这两个就是SSH Key 的秘钥对，id_rsa 是私钥，不能泄露出去，id_rsa.pub是公钥，可以放心地告诉任何人。用记事本打开 id_rsa.pub（C:\Users\Administrator\.ssh），得到ssh key 公钥。

2、为 Github 账户添加 ssh key 。登录 Github，展开个人头像的小三角，点settings，然后打开SSH keys菜单，点击Add SSH key新增密钥，填上标题。


上传项目
跟踪项目文件夹中的所有文件和文件夹

```git
$ git add .

输入本次的提交说明，准备提交暂存区中的更改的已跟踪文件，单引号内为说明内容
```

```git
$ git commit -m "提交文件"

关联远程仓库，添加后，远程库的名字就是 origin，这是 Git 默认的叫法，也可以改成别的，但是 origin 这个名字一看就知道是远程库。
```

```git
$ git remote add origin https://github.com/13029700886/1wp_leetcode_note.git
```

 <img src="C:\Users\Expecto Patronum\AppData\Roaming\Typora\typora-user-images\image-20200727141953343.png" alt="image-20200727141953343" style="zoom:80%;" />

如果关联出现错误 fatal: remote origin already exists，则执行下列语句再进行关联

$ git remote rm origin
把本地库的所有内容推送到远程库上

$ git push -u origin master  下面的链接
如果在推送时出现错误 error:failed to push som refs to.......，则执行下列语句

git pull origin master
将远程仓库 Github 上的文件拉下来合并之后重新推送上去
