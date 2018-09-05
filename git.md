<div style="line-height:12px"><font siz=3>
<font size=4><b>git基本操作指令</b></font>

<div style="margin:20px 0 0 0"><code>git init</code> ： 初始化本地仓库</div>

<code>git add 文件路径</code> ： 向暂存区添加文件

<code>git commit -m ""</code> ： 把暂存区里的文件放入本地仓库

<code>git remote add origin 路径</code> ： 把本地仓库与远程仓库相连接

<code>git status</code> ： 显示当前暂存区里存放了哪些文件，并显示当前工程里面哪些文件被修改

<code>git remote rm origin</code> ： 删除本地仓库与远程仓库的连接

<code>find . -name ".git" | xargs rm -Rf</code> ： 删除本地仓库

<code>git rm --cache 文件路径</code> ： 删除当前暂存区里的文件

<code>rm .git/index</code> ： 清空暂存区

<code>git brach</code> ： 查看当前所处分支

<code>git checkout master</code> ：切换到master分支

<code>git checkout -b master</code> ： 切换到master分支，若该分支不存在，则自动create该分支，并切换到该分支。

<code>git clone 路径</code> ： 将远程仓库的代码拉取到本地工作区

<code>git push origin master</code> ： 将本地仓库的代码更新到远程仓库的master分支上

<code>git pull</code> ： 将远程仓库的代码同步到本地仓库中，很多时候会出现代码冲突，需要手动合并冲突

<code>git stash</code> : 将工作区没有上传的文件放入栈内

<code>git checkout .</code>

<code>git pull -rebase</code>



<div style="margin:50px 0px 0px 0px"><font size=4><b>部分BUG及解决方法</b></font></div>

错误信息 ：<code>fatal: remote origin already exists.</code>

原因 ： 执行<code>git remote add origin</code>时出错，因为本地仓库与远程仓库的连接已经存在。

解决方法 ： 首先执行<code>git remote rm origin</code>删除本地仓库与远程仓库的连接。然后再执行<code>git remote add origin</code>指令。
<br>
错误信息 ：<code>There is no tracking information for the current branch. Please specify which branch you want to merge with.</code>

原因 ：一般在执行<code>git pull</code>的时候出错，原因是本地分支没有和远程分支建立联系。

解决方法 ： <code>git branch --set-upstream-to=origin/远程分支 本地分支</code>
<br>
错误信息 ： <code>refusing to merge unrelated histories</code>

原因 ： 本地仓库和远程仓库没有一个共同的commit，git认为是origin错误，此时需要开发者确定是这个origin。

解决方法 ： <code>git pull origin master --allow-unrelated-histories</code>
<br>
错误信息 ：<code>

	 From https://github.com/WJJJJY/LearnOnTAL
	　* branch            master     -> FETCH_HEAD
	error: The following untracked working tree files would be overwritten by merge:
	README.md
	gdb.md
	Please move or remove them before you merge.
	Aborting

原因 ： 对于当前本地已有的工程，当我们只想提交部分文件到git上，在<code>git pull</code>的时候会产生此类错误。具体为README.md和gdb.md均是未被跟踪的文件。

解决方法 ： 移动文件至别处，保证当前文件夹下面只保存要提交的文件。
<br>
错误信息 ： 无法正常切换分支

</font></div>
