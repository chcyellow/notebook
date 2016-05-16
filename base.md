#第一次推送仓库
#git init
//初始化代码库。
#git add .
//把所有文件及文件夹添加到跟踪。
#git commit -m "first commit"
//先提交到本地。
#git commit -a -m
Git 提供了一个跳过使用暂存区域的方式，只要在提交的时候，给 git commit 加上 -a 选项，Git 就会自动把所有已经跟踪过的文件暂存起来一并提交，从而跳过 git add 步骤。
#git remote add origin git@git.oschina.net:chcyellow/notebook.git
//告诉本地代码库:远程代码库在哪里。
#git push -u origin master
OR
#git push -u origin gh_pages
OR
#git push -f origin master
//推送本地更新到远程或强制执行。
#git pull origin master
//从远程更新到本地。

#git clone git@git.oschina.net:chcyellow/notebook.git
//获取源码，机器上就有一个repo。

#git tag -a v1.0 -m 'my version 1.0'
//打标签

#$ git config --global alias.ci commit
//git别名

#撤销操作
工作区撤销	git checkout --readme.txt

#问题集锦
1.faltal:remote origin already exists.
    $ git remote rm origin
    $ git remote add origin git@github:chcyellow/suneps_doc.github.io.git
	$ git remote add origin git@git.oschina.net:chcyellow/notebook.git
      if not
    $ C:\Users\chc\AppData\Local\GitHub\PortableGit_ca.......\etc Delete gitconfig [remote "origin"]
    $ OK!

2.mac下git push -u origin master失败，加参数-f运行。
3.首次推送到远程时出现错误提示failed to push some refs to 'git@git.oschina.net
出错的原因主要是github中的README.md文件不在本地代码目录中
可以通过如下命令进行代码合并
git pull --rebase origin master
此时再执行 git push -u origin master即可完成代码上传。