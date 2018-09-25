<div><font size=5><b>VIM基本操作指令</b></font></div>

<code>:w</code> ： 保存

<code>:x</code> ： 直接退出

<code>:q</code> ： 直接退出

<code>u</code> ： 回退到上一步操作

<code>v</code> ： 选中当前光标所处位置的字符

<code>V</code> ： 选中当前光标所处的一整行

<code>x</code> ： 删除当前光标所处位置的字符

<code>d</code> ： 通常跟<code>V</code>配合使用，剪切

<code>p</code> ： 粘贴

<code>y</code> ： 复制

<code>o</code> ： 在当前行的下一行插入

<code>O</code> ： 在当前行的上一行插入

<code>j && k && h && l</code> ： 上下左右

<code>A</code> ： 光标直接跳转到行尾

<code>I</code> ： 光标直接跳转到行首

<code>G</code> ： 光标跳转到程序最后一行

<code>gg</code> ： 光标跳转到程序第一行

<code>w</code> ： 光标以单词为单位向后移动

<code>:/string</code> ： 在当前程序中查找<code>string</code>字符串

<code>:num</code> ： 跳转到<code>num</code>行

<code>set num</code> ： 显示行号

<code>set nonum</code> ： 不显示行号

<code>:%s/AAA/BBB</code> ： 将文本里面所有的AAA替换成BBB

<code>进入根目录后执行vim ~/.vimrc</code> ：进入<code>vimrc</code>