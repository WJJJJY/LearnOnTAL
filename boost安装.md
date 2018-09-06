安装 ：
 >wget http://jaist.dl.sourceforge.net/project/boost/boost/1.58.0/boost_1_58_0.tar.bz2

解压 ： <code>tar -xjf boost_1_58_0.tar.bz2</code>

运行bootstrap.sh ： <code>./bootstrap.sh</code>

使用b2进行构建 ： <code>sudo ./b2</code>

安装boost库到指定目录 ： <code>sudo ./b2 --prefix=/usr/local/boost install</code>

卸载 ： <code>apt-get autoremove libboost1.62-dev</code>

查看当前版本 ： <code>dpkg -S /usr/include/boost/version.hpp</code>

相关问题 : 可能会提示 <code>"fatal error : bzlib.h"</code>

解决方法 ： <code>sudo apt-get install libbz2-dev</code>

进行版本迭代的时候，需要卸载旧版本。然后把当前boost库的安装路径添加到环境变量中。

设置环境变量 : 执行<code>vim /etc/profile</code>

在末尾添加 ：

	export CPLUS_INCLUDE_PATH=/usr/boost/include:$CPLUS_INCLUDE_PATH

	export LIBRARY_PATH=/usr/boost/lib:$LIBRARY_PATH

	export LD_LIBRARY_PATH=/usr/boost/lib:$LD_LIBRARY_PATH

然后执行 ： <code>source /etc/profile</code>

相关详细链接 ：
>https://www.cnblogs.com/findumars/p/6253092.html