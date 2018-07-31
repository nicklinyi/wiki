---
title: Git
---


```
$ git log #查看commit的历史记录,方便的回退到任意版本
```

```
$ git reset --hard 322455  #  commit id
# 这条语句非常有用，比如在一个正确的程序上修改，结果运行发现运行结果
# 出错，这时候通过git log 查看上一次commit的id，然后采用这条命令就可以将整个
# 项目下的源文件重新退回到上一次的正确结果上。而因为修改地结果也可以通过git
# reflog来查询出来，如果想重新回到之前修改的结果上的话
```

## 删除文件
```
$ git rm 1.txt
```
## branch

```
$ git branch -v  #查看分支
$ git branch -a  #查看全部分支（包括远程分支）
$ git check -b new # 创建new分支，并切换至该分支
```
```
$ git reflog  #查看历史命令，用于查询回退版本后，找不到未来版本的commit id
ea34578 HEAD@{0}: reset: moving to HEAD^
3628164 HEAD@{1}: commit: append GPL
ea34578 HEAD@{2}: commit: add distributed
cb926e7 HEAD@{3}: commit (initial): wrote a readme file
```

```
$ git branch new-branch-name # 创建新的名为 new-branch-name 的分支
# 这条语句的意义有：
# 1. 用于发行一个release版本，创建一个release版本的分支，用于发行。
# 2. 用于develop，一个master上用于存放正确的代码，develop用于进行测试，测试
# 完后将正确的结果推回至master

```
```
$ git checkout new-branch-name # 切换至名为 new-branch-name 的分支
```
```
$ git branch -a # 查看本地分支和远程分支
$ git branch -d branchName # 删除本地分支branchName，前提条件是该分支已merge到其他分支
$ git branch -D branchName # 强制删除本地分支branchName
$ git push origin --delete branchName # 删除远程分支 origin/branchName
```

## submodule
```
$ git submodule add git:@github.com/xyz/xyz.git xyz-local
$ git submodule init
$ git submodule update
$ git submodule update --remote #从远程分支
```

## tag
```
$ git tag -a v0.1 -m "version 0.1"   # 创建 annotation tag
$ git push origin --tags  # 向远程分支推送 tag
$ git tag ## 查看tag
```

## 生成秘钥

1. From the terminal, enter `ssh-keygen` at the command line.The command prompts you for a file to save the key in:
```
 $ ssh-keygen 
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/emmap1/.ssh/id_rsa):
```
2. Press the Enter or Return key to accept the default location.

> To create a key with a name or path other than the default, specify the full path to the key. For example, to create a key called my-new-ssh-key
, enter a path like the one shown at the prompt:
```
$ ssh-keygen 
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/emmap1/.ssh/id_rsa): /Users/emmap1/.ssh/my-new-ssh-key
```


3. Enter and re-enter a passphrase when prompted.The command creates your default identity with its public and private keys. The whole interaction will look similar to the following:
```
$ ssh-keygen 
Generating public/private rsa key pair.
Enter file in which to save the key (/Users/emmap1/.ssh/id_rsa):
Created directory '/Users/emmap1/.ssh'.
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in /Users/emmap1/.ssh/id_rsa.
Your public key has been saved in /Users/emmap1/.ssh/id_rsa.pub.
The key fingerprint is:4c:80:61:2c:00:3f:9d:dc:08:41:2e:c0:cf:b9:17:69
[emmap1@myhost.local](mailto:emmap1@myhost.local) 
The key's randomart image is:
+--[ RSA 2048]----+
|*o+ooo.          |
|.+.=o+ .         |
|. *.* o .        |
| . = E o         |
|    o . S        |
|   . .           |
|     .           |
|                 |
|                 |
+-----------------+
```
4. List the contents of ~/.ssh to view the key files.
```
$ ls ~/.ssh id_rsa id_rsa.pub
```
The command displays two files, one for the public key (for example `id_rsa.pub`) and one for the private key (for example,`id_rsa`
).

5. 采用免密码提交的方式需要将`.git/config`文件中`url`设为ssh的模式。
```
url = git@github.com:nick/projet-name.git
```

## Reference
https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/#platform-linux

[Git Pro](https://git-scm.com/book/en/v2)


