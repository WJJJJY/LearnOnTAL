<div style="line-height:12px"><font siz=3>
<div>
<font size=4><b>git基本操作指令</b></font><br><br>
<code>git init</code> ： 初始化本地仓库<br>
<code>git add 文件路径</code> ： 向暂存区添加文件<br>
<code>git commit -m ""</code> ： 把暂存区里的文件放入本地仓库<br>
<code>git remote add origin 路径</code> ： 把本地仓库与远程仓库相连接<br>
<code>git status</code> ： 显示当前暂存区里存放了哪些文件，并显示当前工程里面哪些文件被修改<br>
<code>git remote rm origin</code> ： 删除本地仓库与远程仓库的连接<br>
<code>find . -name ".git" | xargs rm -Rf</code> ： 删除本地仓库<br>
<code>git rm --cache 文件路径</code> ： 删除当前暂存区里的文件<br>
<code>rm .git/index</code> ： 清空暂存区<br>
<code>git brach</code> ： 查看当前所处分支<br>
<code>git checkout master</code> ：切换到master分支<br>
<code>git checkout -b master</code> ： 切换到master分支，若该分支不存在，则自动create该分支，并切换到该分支。<br>
<code>git clone 路径</code> ： 将远程仓库的代码拉取到本地工作区<br>
<code>git push origin master</code> ： 将本地仓库的代码更新到远程仓库的master分支上<br>
<code>git pull</code> ： 将远程仓库的代码同步到本地仓库中，很多时候会出现代码冲突，需要手动合并冲突<br>
<code>git stash</code> : 将工作区没有上传的文件放入栈内，便于分支之间的切换。<br>
<code>git stash pop</code> ： 将栈内没有上传的文件恢复到工作区。<br>
<code>git checkout .</code> ： 清空对当前分支所做的所有修改。<br>
<code>git pull -rebase</code><br>
<code>git log</code> ： 查看*commit*日志， <b>*q*</b>退出<br>
<code>git reset --hard fdasfdsarefasderesfe</code> ：版本回退，本地恢复到该节点的状态。<br>
<code>git push -f -u origin master</code> ：强推到远程分支，慎用，会直接覆盖远程分支。版本回退后，若进行分支强退，则之前的新版本无法查看。<br>
<code>git branch -d branch_id</code> ： 删除本地分支*branch_id*<br>
<code>git branch -a</code> ： 列出已有分支目录<br>
<code>git push origin --delete branch_id</code> ： 删除远程分支*branch_id*<br>
<code>git merge branch_id</code> ： 分支合并，把*branch_id*分支合并到当前分支。<br>

<code>git remote -v</code> : 查看远程仓库的地址<br><br>

<font size=4><b>提交当前分支的代码到其他分支 *git cherry-pick commit_id*</b></font><br>
> *<code>git checkout odd_cc</code>* ： 切换到目的分支<br>
> *<code>git cherry-pick commit_id</code>* ：*commit_id*为源分支的*ID*，可在源分支上通过*git log*获取。<br>
> *push*的时候可能会出现冲突，此时需要手动*fix*冲突，然后执行*git commit*<br><br>


<font size=4><b>部分BUG及解决方法</b></font><br>
错误信息 ：<code>fatal: remote origin already exists.</code><br>
原因 ： 执行<code>git remote add origin</code>时出错，因为本地仓库与远程仓库的连接已经存在。<br>
解决方法 ： 首先执行<code>git remote rm origin</code>删除本地仓库与远程仓库的连接。然后再执行<code>git remote add origin</code>指令。<br><br>
错误信息 ：<code>There is no tracking information for the current branch. Please specify which branch you want to merge with.</code><br>
原因 ：一般在执行<code>git pull</code>的时候出错，原因是本地分支没有和远程分支建立联系。<br>
解决方法 ： <code>git branch --set-upstream-to=origin/远程分支 本地分支</code><br><br>
错误信息 ： <code>refusing to merge unrelated histories</code><br>
原因 ： 本地仓库和远程仓库没有一个共同的commit，git认为是origin错误，此时需要开发者确定是这个origin。<br>
解决方法 ： <code>git pull origin master --allow-unrelated-histories</code><br><br>
错误信息 ：

	 From https://github.com/WJJJJY/LearnOnTAL
	　* branch            master     -> FETCH_HEAD
	error: The following untracked working tree files would be overwritten by merge:
	README.md
	gdb.md
	Please move or remove them before you merge.
	Aborting

原因 ： 对于当前本地已有的工程，当我们只想提交部分文件到git上，在<code>git pull</code>的时候会产生此类错误。具体为README.md和gdb.md均是未被跟踪的文件。<br>
解决方法 ： 移动文件至别处，保证当前文件夹下面只保存要提交的文件。<br><br>
错误信息 ： 无法正常切换分支<br>
原因 ： 当前分支做了修改，但未提交。系统会自动提示，当前分支的哪些内容做了修改。<br>
解决方法 ：1. <code>git checkout .</code> 撤销对当前分支做的所有更改。2. <code>git stash</code> 将当前更改内容放入栈内，保持当前分支的干净。当要回到该分支上继续之前的修改的时候，可用<code>git stash pop</code> 恢复之前修改的内容。<br><br>
错误信息 ： fatal: refusing to merge unrelated histories<br>
原因 ： 因为是两个不同的项目，在进行<code>pull</code>的时候，两个仓库不同，拒绝合并。<br>
解决方法 ： 在<code>git pull</code>后面加上<code>--allow-unrelated-histories</code>。如<code>git pull origin master --allow-unrelated-histories</code>。<br><br>
</div>
</font></div>
