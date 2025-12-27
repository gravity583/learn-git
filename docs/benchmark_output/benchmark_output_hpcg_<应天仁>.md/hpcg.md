sudo apt update
#更新
sudo apt install -y build-essential cmake git
#下载依赖
wget https://codeload.github.com/hpcg-benchmark/hpcg/zip/refs/heads/master -O hpcg.zip
#下载 HPCG 源码压缩包
unzip hpcg.zip
#解压
cd hpcg-master
#进入目录
mkdir build
cd build
#创建 build 目录
cmake .. -DCMAKE_CXX_COMPILER=mpicxx
#用 MPI 编译
make -j$(nproc)
#编译
ls
#确认可执行文件xhpcg
cd bin
#进入 bin 目录
nano hpcg.dat
#创建 hpcg.dat写入合适的参数
mpirun -np 4 ./xhpcg
#运行,结果会以txt文件输出



