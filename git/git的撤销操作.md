<font size=5><b>git的四个阶段的撤销操作</b></font>

<img src="https://i.imgur.com/YTM6wFs.png" height="300" width="800"></img>
<br><br><br>
<font size=5><b>基本概念</b></font>
<img src="https://i.imgur.com/uXs7twd.png" height="150" width="800"></img>
> 通常情况下，*git*分为四个区，即工作区，暂存区，本地仓库，远程仓库。
> 三个基本操作：*<code>git add .</code>*(将修改由工作区推向暂存区）；*<code>git commit -m "..."</code>*(将修改由暂存区推向本地仓库）；*<code>git push origin/master</code>*(将修改由本地仓库推向远程仓库）。

<br><br>

<font size=5><b>检查修改</b></font>
>*<code>git diff</code>* ：检查<b>工作区</b>做了哪些修改，<b>针对已修改未暂存</b>。
>*<code>git diff --cached</code>* ：检查<b>暂存区</b>做了哪些修改，<b>针对已暂存未提交</b>。
>*<code>git diff master origin/master</code>* ：检查<b>本地仓库</b>做了哪些修改，<b>针对已提交未推送</b>

<br><br>
<font size=5><b>撤销修改</b></font>
> *<code>git checkout . 或者 git reset --hard</code>* ：撤销<b>工作区</b>的修改，针对<b>已修改未暂存</b>。
> *<code>git reset</code>* ：撤销对<b>暂存区</b>的修改，对文件的修改会恢复到<b>工作区</b>。
> *<code>git reset --hard origin/master></code>* ： 撤销对<b>本地仓库</b>的修改，对文件的修改会恢复到<b>暂存区</b>。
> *<code>git reset --hard HEAD^</code>* ： 撤销对<b>远程仓库</b>的修改，对文件的修改会恢复到<b>本地仓库</b>。