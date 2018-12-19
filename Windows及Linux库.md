# <b>windows及Linux下的库</font></b>
## <b>一、Windows下的静态库及动态库</font></b>
静态库：后缀名<code>.lib</code>，所谓静态就是link的时候把里面需要的东西提取出来安排到你的exe文件中，以后运行你的exe的时候不再需要lib。<br>
动态库：后缀名<code>.dll</code>，所谓动态就是exe运行的时候依赖于dll里面提供的功能，没有这个dll，exe就无法运行。<br>
<b>lib是编译时需要，dll是运行时需要。</b>

## <b>二、Linux下的静态开及共享库</b></font><br>
静态库：后缀名<code>.a</code>，用于静态连接<br>
共享库：后缀名<code>.so</code>，用于动态链接，相当于Windows下的dll。

###<b>１.　Linux下的<code>.so</code>库找不到的问题



