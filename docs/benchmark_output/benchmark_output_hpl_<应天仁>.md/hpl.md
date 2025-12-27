cd hpl-2.3 
#进入hpl-2.3目录
sudo apt-get update
#更新
sudo apt-get install gcc gfortran make libopenblas-dev
#下载依赖
cp setup/Make.Linux_PII_CBLAS
#复制配置文件
nano Make.Linux_OpenBLAS_MPICH
#修改配置文件中的内容(比如路径，编译器设置)
make arch=Linux_OpenBLAS_MPICH
#开始编译(如果有之前的编译,需要先清理 make clean)
mpirun -np 4 ./xhpl
#修改好dat文件后,使用4个进程运行
