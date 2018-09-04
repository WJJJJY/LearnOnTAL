<b><font size=5>关于GDB : UNIX下的调试工具</b>


<b><font size=6>基本操作指令
---
**<font size=4>执行gdb调试**　：<em><font size=4>gdb path<b>(可执行文件路径）</b></em>

<img src="https://i.imgur.com/J59JJY8.png" height="50" width="800"></img>

<b><font size=4>设置读入</b>　：<em><font size=4>set args input<b>(读入元素）</b></em>

<img src="https://i.imgur.com/wHDJfV7.png" height="120" width ="800"></img>

<b>运行程序</b>　： <em>run</em>

<img src="https://i.imgur.com/l4H3s1N.png" height="200" width="800"></img>

<b>显示源码</b>　：<em>L</em>

<img src="https://i.imgur.com/AKged81.png" height="200" width="800"></img>

<b>设置断点</b>　：<em>b row<b>(行号)</b></em>

<img src="https://i.imgur.com/BGO7yO1.png" height="50" width="800"></img>

<b>删除断点</b>　：<em>d x<b>(断点编号)</b></em>　　||　　<em>clear x<b>(行号)</b></em>

<img src="https://i.imgur.com/PwwOhtq.png" height="50" width="800"></img>

<img src="https://i.imgur.com/z299vPM.png" height="100" width="800"></img>

<b>屏蔽断点</b>　：<em>disable x<b>(断点编号)</b></em>

<img src="https://i.imgur.com/sovTAVM.png" height="100" width="800"></img>

<b>启动断点</b>　：<em>enable x<b>(断点编号)</b></em>

<img src="https://i.imgur.com/wnzgJOK.png" height="100" width="800"></img>

<b>打印变量的值</b>　：<em>p x</em>

<img src="https://i.imgur.com/j9UE3Tl.png" height="120" width="800"></img>

<b>当条件满足时启动断点</b>　：<em>b row if elem == x</em>

<img src="https://i.imgur.com/DgtJJXK.png" height="200" width="800"></img>

<b>显示运行错误信息</b>　：<em>bt</em>

<img src="https://i.imgur.com/zBwyAqG.png" height="50" width="800"></img>