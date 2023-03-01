# Git的环境配置
1、git安装好后，再去GitHub上注册一个账号：https://github.com/
再点击桌面上的Git Bash快捷图标，我们要用账号进行环境配置了

2、在点击桌面上的Git Bash快捷图标中输入：

```js
配置用户名：

git config --global user.name "username"    //（ "username"是自己的账户名，）

配置邮箱：

git config --global user.email "username@email.com"     //("username@email.com"注册账号时用的邮箱)
```

![](F:\Note\3.png)

以上命令执行结束后，可用如下命令查看配置是否OK

```js
git config --global --list 
```

![](F:\Note\2.png)

#  生成ssh key

```js
# 创建 .ssh 目录
$ mkdir ~/.ssh
# 切换到 .ssh 目录下
$ cd ~/.ssh
# 生成密钥（下面的提示直接按回车即可，不用设置密码）
$ ssh-keygen -t rsa -C "sun@163.com"
    Generating public/private rsa key pair.
    Enter file in which to save the key (/c/Users/scy/.ssh/id_rsa): #保存密钥的位置（回车就是默认）
    Enter passphrase (empty for no passphrase): # 密码（回车不设置密码，如果设置密码使用idea的ssh代码会拉不下来）
    Enter same passphrase again: # 确认密码
    Your identification has been saved in /c/Users/scy/.ssh/id_rsa
    Your public key has been saved in /c/Users/scy/.ssh/id_rsa.pub
    The key fingerprint is:
    SHA256:F123456............89624 sun@163.com
    The key's randomart image is:
    +---[RSA 3072]----+
    |   ..o.*+o  .oo+o|
    |  .    .     o =.|
    |              +. |
    |              .oo|
    +----[SHA256]-----+
# 获取刚刚生成的ssh key
$ cat ~/.ssh/id_rsa.pub
```

