
设置环境变量 ：
 1. 执行<code style="font-size:15px">vim /etc/profile</code> ，添加环境变量。
 2. 执行<code style="font-size:15px">source /etc/profile</code>使环境变量生效
	
<code>ln -s 当前的库 创建的连接库</code> ： 创建动态库的软连接<br>
<code>ldd</code> ： 查看当前程序使用了哪些动态库<br>
<code>可执行程序的动态库丢失问题 </code> ： linux在执行程序时会自动在/usr/lib/下寻找动态库， find寻找动态库，然后生成软连接到/usr/lib/目录下， 路径需要使用绝对路径。<br>
<code>cp</code> ： 复制<br>
<code>mv</code> ： 剪切，重命名。<br>
<code>mkdir</code> ： 新建文件夹<br>
<code>mkdir -p</code> ： 建立多层目录<br>
<code>cmake .. || cmake CMAKE_BUILD_TYPE=RELEASE .. || cmake -G "Visual Studio 14 2015 Win64" .. || make</code> ： cmake编译基本指令<br>
<code>cat</code> ： 查看文本文件<br>
<code>sodu</code> ： 获取root权限<br>
<code>docker ps -a</code> ： 显示docker下用户<br>
<code>docker start</code> ： 启动docker用户<br>
<code>docker attach</code> ： 进入docker用户<br>
<code>exit</code> ： 退出当前docker<br>
<code>docker exec -it /bin/bash</code> ：在不影响别人的情况下，进入docker<br>
<code>scp webmaster@11.11.11.11:/path_1 path_2</code> ：跨服务器传输文件*path_1* 到 *path_2*<br>
<code>scp path_2 webmaster@11.11.11.11:/path_1</code> ： 跨服务器传输文件*path_2* 到 *path_1*<br>
<code>scp -P port path_2 webmaster@11.11.11.11:/path_2</code> ： 跨服务器传输文件*path_2*到*paht_2*<br>
<code>ssh root@11.11.11.11 -p port</code> ： ssh远程连接到指定端口号
<code>pwd</code> ： 显示当前文件的绝对路径 <br>
<code>unzip name.zip</code> ： 解压<code>.zip</code>文件<br>
<code>zip name.zip name</code> ： 压缩*name*文件为*name.zip*文件<br>
<code>tar zxvf name.tar</code> ： 解压*name.tar*文件<br>
<code>tar czvf name.tar name</code> ： 压缩*name*文件为*name.tar*<br>
<code>tar zxvf 文件名</code> ： 解压<code>.tar</code>文件<br>
<code>vim /etc/profile +  source /etc/profile</code> ： 修改/增加 全局变量<br>




