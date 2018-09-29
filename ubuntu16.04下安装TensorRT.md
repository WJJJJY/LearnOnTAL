<div><b><font size=6>Linux ubuntu 16.04</font></b></div>
<div><b><font size=5><b>安装pip</b></font></div>
下载并 安装setuptools ：

    wget --no-check-certificate https://bootstrap.pypa.io/ez_setup.py
    sudo python ez_setup.py --insecure 

下载pip安装包，然后解压安装 ：

    wget https://pypi.python.org/packages/11/b6/abcb525026a4be042b486df43905d6893fb04f05aac21c32c638e939e447/pip-9.0.1.tar.gz#md5=35f01da33009719497f01a4ba69d63c9
    tar -xf pip-9.0.1.tar.gz
    cd pip-8.0.0
    sudo python setup.py install
    ln -s /usr/local/python27/bin/pip /usr/bin/pip
<br>

安装CUDA8.0/9.0 CUDNN7.0 python2/3<br>

 
安装TensorRT
>安装*TensorRT*需要预先安装*cuda，cudnn*以及*python*<br>

1. 解压*tar*文件，解压完会出现相应的文件夹，文件下下面会包含相应的*lib，bin*等文件。<br>
>tar -xzvf TensorRT-3.0.0.Ubuntu-16.04.3.cuda-9.0.tar.gz
2. 添加环境变量(方便可执行程序，找到TensorRT动态库)<br>
>vim ~/.bashrc
>export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:~/TensorRT-4.0.1.6/lib
>source ~/.bashrc
3. 安装*python TensorRT*包
>cd TensorRT-3.0.0/python<br>
>sudo pip2 install tensorrt-3.0.0-cp27-cp27mu-linux_x86_64.whl-------*python2*<br>
>sudo pip3 install tensorrt-3.0.0-cp35-cp35m-linux_x86_64.whl -------*python3*<br>
4. 测试*TensorRT*是否安装成功
>which tensorrt ---------*常用命令，输出安装路径*<br>
>/usr/local/bin/tensorrt -------*此处没有打印路径也不要紧，只要上述安装步骤没有报错即可*<br>
><b>可能出现的bug：</b><br>
    *In file included from src/cpp/cuda.cpp:1:0:<br>
    src/cpp/cuda.hpp:14:18: fatal error: cuda.h: No such file or directory<br>
    compilation terminated.<br>
    error: command 'x86_64-linux-gnu-gcc' failed with exit status 1*<br>
    <b>显示的原因是找不到*cuda.h*，根据网上分析是因为用了*sudo*之后环境变量用的是*root*的环境变量<br>
    解决方法：</b><br>
    vim /etc/profile.d/cuda.sh<br>
    添加：export PATH=/usr/local/cuda-8.0/bin:$PATH<br>
    sudo su -<br>
    pip2 install tensorrt-3.0.0-cp27-cp27mu-linux_x86_64.whl --trusted-host pypi.douban.coms<br>
    exit<br>
5. 安装*uff*包
>转到*uff*目录下<br>
>sudo pip2 install uff-0.1.0rc0-py2.py3-none-any.whl ---------*python2*<br>
>sudo pip3 install uff-0.3.0rc0-py2.py3-none-any.whl ---------*python3*<br>
6. 测试*uff*是否安装成功
>which convert-to-uff<br>
>/usr/local/bin/convert-to-uff<br>
7. 测试
>cd TensorRT-4.0.1.6/samples<br>
>make<br>
><b>可能出现的错误：</b><br>
    sampleMNIST.cpp:9:10: fatal error: cuda_runtime_api.h: No such file or directory<br>
    /#include <cuda_runtime_api.h><br>
    <b>具体的原因</b>：是由于CUDA路径没有找到，需要在make后添加，以指定路径<br>
    sudo make clean ----------- *清理上一步make之后产生的文件*<br>
    make CUDA_INSTALL_DIR=/usr/local/cuda<br>
>cd TensorRt-4.0.1.6/bin<br>
>./sample_mnist<br>

>详情参考：https://blog.csdn.net/macwinwin/article/details/80177326<br>
>详情参考：https://blog.csdn.net/xll_bit/article/details/78376320<br>