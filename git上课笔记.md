#学习内容：
单机GIT工具使用；
GIT基本操作流程；
GIT工作区、暂存区、主分区的概念；
GIT实现版本的回退功能；
GIT实现文件的修改操作；

#为每个机器都填写自己的基本信息：开发者名字、Email地址。
姓名: git config --global user.name "yootk"
email: git config --global user.email "mldnqa@163.com"
查询全局信息: git config -l

#创建仓库
初始化仓库(将此目录变为可以被GIT管理的仓库)
git init

#添加文件

#察看当前仓库的状态
git status
.现在的开发属于主分支:On branch master;
.初始化仓库的提交:Initial commit;
.未标记的文件:Untracked files;
.随后给出了一些操作的命令: (use "git add <file>..." to include in what will be committed)
.未标记文件的列表。

#加入到暂存库
git add (file)
git status
Changes to be committed:

#提交文件信息
git commit -m "New Java File - Hello.java Create"

#查看日志信息
git log Hello.java
$ git log Hello.java
commit 51ddd63c5061312717145ee6a0f2de8f02f39ee7
Author: chcyellow <chcplus@gmail.com>
Date:   Fri Jun 3 09:12:42 2016 +0800

    New Java File - Hello.java Create

#修改文件

#查看 git status
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

        modified:   Hello.java

no changes added to commit (use "git add" and/or "git commit -a")
提一下:git checkout -- <file> 可以放弃修改。

#查看文件前后区别
$ git diff Hello.java
diff --git a/Hello.java b/Hello.java
index ad2cf98..06b6f8c 100644
--- a/Hello.java
+++ b/Hello.java
@@ -1,5 +1,7 @@
 public class Hello{
        public static void main (String args[]){
                System.out.println("Hello the World!");
+               System.out.println("Hello chcyellow");
+               System.out.println("chcplus@gmail.com")
        }
-}
\ No newline at end of file
+}

#工作区与仓库
<工作区>：就是当前电脑的操作目录(包含.git);
<仓库>(版本库，Repository)：工作区有一个隐藏目录.git,这个不算工作区，而是Git的仓库(版本库);
Git的版本库里存了很多东西，其中最重要的就是称为stage的暂存区，还有Git为用户自动创建的主程序分支master,以及指向master的HEAD指针。

#版本回退
//查看日志
git log --pretty=oneline
回退一步
git reset --hard HEAD~1
不会被删除，但代码已经回到指定的版本
git reflog(查看所有commit id)
git reset --hard 8d709e0

#撤销修改
git add后，git commit前的修改，可以撤销对文件所做出的修改操作。
	撤销暂存区的修改操作：git reset HEAD 文件名称；==>针对Add
	放弃已经修改的文件内容：git checkout --文件名称；==》针对工作区