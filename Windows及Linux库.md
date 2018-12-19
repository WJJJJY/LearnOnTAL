# <b>windows及Linux下的库</font></b>
## <b>一、Windows下的静态库及动态库</font></b>
静态库：后缀名<code>.lib</code>，所谓静态就是link的时候把里面需要的东西提取出来安排到你的exe文件中，以后运行你的exe的时候不再需要lib。<br>
动态库：后缀名<code>.dll</code>，所谓动态就是exe运行的时候依赖于dll里面提供的功能，没有这个dll，exe就无法运行。<br>
<b>lib是编译时需要，dll是运行时需要。</b>

## <b>二、Linux下的静态开及共享库</b></font><br>
静态库：后缀名<code>.a</code>，用于静态连接<br>
共享库：后缀名<code>.so</code>，用于动态链接，相当于Windows下的dll。

### <b>1.　Linux下的<code>.so</code>库找不到的问题</b>
对于可执行程序，可以先用<code>ldd</code>查看当前可执行程序依赖了哪些库。<br>
若对应的库显示<code>not find</code>，可用<code>find -name</code>查找依赖库的位置。及解决问题的前提是缺失的库存在。<br>
<b>几个解决办法：</b>
- 若只是用于临时测试，可以通过设置<b>临时变量</b>来解决。即<code>export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:/home/workspace_private/...</code>；其中<code>LD_LIBRARY_PATH</code>为系统预设的变量；对于<code>LD_LIBRARY_PATH</code>的值，可以用<code>echo $LD_LIBRARY_PATH</code>来显示。临时变量在系统重启后即失效。
- 一般Linux把<code>/lib</code>和<code>/usr/lib</code>这两个目录作为默认的库搜索路径，所以使用这两个目录的库时不需要进行设置搜索路径即可使用。所以，如果允许的情况下，可以将<code>.so</code>库放到该目录下。
- 手动将<b>库路径</b>添加到<code>/etc/ld.so.conf</code>中，或者在<code>/etc/ld.so.conf.d</code>下新建一个对应的<code>.conf</code>文本，将库文件路径一行一行的添加进去。这种方法是永久的，也极为便捷。但是对于<b>共享库</b>而言，在此基础上，还需要在<b>root</b>权限下运行<code>/sbin/ldconfig</code>。这是因为对共享库而言，为了加快程序执行时对共享库的定位，避免使用搜索路径找共享库的低效率，所以是直接读取库列表<code>/etc/ld.so.cache</code>从中搜索的。<code>/etc/ld.so.cache</code>是一个非文本的数据文件，不能直接编辑，它是根据<code>/etc/ld.so.conf</code>中设置的搜索路径由<code>/sbin/ldconfig</code>命令将这些搜索路径下的共享文件集中在一起而生成的。可以使用<code>ldconfig -p</code>查看，当前<code>/etc/ld.sos.cache</code>已经载入的搜索路径。
- 修改<code>~/.bashrc</code>或<code>~/.bash_profile</code>或系统级别的<code>/etc/profile</code>。在其中添加<code>export PATH=/home/workspace_private/...:$PATH</code>。并执行<code>source ~/.bashrc</code>使之生效。

