查看当前版本 ： <code>pkg-config --modversion opencv</code>

下载 ： <code>wget https://github.com/opencv/opencv/archive/3.3.1.zip</code>

解压 ： <code>unzip 3.3.1.zip</code>

<code>mkdir build</code>

<code>cd build</code>

<code>cmake   -D CMAKE_BUILD_TYPE=RELEASE   -D CMAKE_INSTALL_PREFIX=/usr/local   -D WITH_TBB=ON   -D WITH_V4L=ON   -D WITH_QT=OFF   -D WITH_OPENGL=ON   -D WITH_CUDA=ON   -D ENABLE_FAST_MATH=1   -D CUDA_FAST_MATH=1   -D CUDA_NVCC_FLAGS="-D_FORCE_INLINES"   -D WITH_CUBLAS=1 -D CPU_BASELINE=AVX  ..</code>

<code>make -j8</code>

<code>make install</code>