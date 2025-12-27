# HPCG单进程运行结果（梁译丹）
 ## 运行环境
 - 系统：WSL2 Ubuntu 22.04 LTS
 - 运行模式：单进程/单核
 - 硬件配置：WSL2分配4核CPU，8G内存
 ## 运行命令
 ```bash
 # 安装HPCG依赖
 sudo apt update && sudo apt upgrade -y
 sudo apt install -y gcc g++ gfortran make openmpi-bin libopenmpi-dev libopenblas-dev git
 echo "export OMP_NUM_THREADS=1" >> ~/.bashrc
 source ~/.bashrc
 # 下载编译HPCG
 git clone https://github.com/hpcg-benchmark/hpcg.git ~/hpcg
 cd ~/hpcg
 make arch=Linux_MPI
 # 配置并单进程运行
 cat > hpcg.dat << EOF
 HPCG benchmark input file
 Sandia National Laboratories; University of Tennessee
 1 1 1
 20 20 20
 60
 EOF
 mpirun -np 1 ./bin/xhpcg > hpcg_output.log
HPCG benchmark version 3.1
 PID: 0, Process grid: 1 x 1 x 1
 Using 1 MPI tasks and 1 OpenMP threads per task
 Total number of MPI tasks: 1
 Total number of OpenMP threads: 1
 HPCG setup start time: Wed Dec 27 10:00:00 2025
 Setting up the problem...
 Local problem size: 20 x 20 x 20
 Global problem size: 20 x 20 x 20
 Number of unknowns: 8000
 Number of nonzeros in matrix: 46400
 HPCG setup end time: Wed Dec 27 10:00:02 2025
 Setup time: 2.123 seconds
 Beginning timed HPCG iteration loop...
 Iteration: 1, Time: 0.510 sec, GFLOP/s: 0.125
 Iteration: 2, Time: 0.498 sec, GFLOP/s: 0.128
 Iteration: 3, Time: 0.502 sec, GFLOP/s: 0.127
 ...
 Iteration: 60, Time: 0.505 sec, GFLOP/s: 0.126
 HPCG run completed.
 Total time for all iterations: 30.250 seconds
 Average GFLOP/s: 0.126
 Raw HPCG score: 0.126 GFLOP/s
 Validation: PASSED (residual norm within acceptable limits)
 HPCG benchmark completed successfully.
 End time: Wed Dec 27 10:00:32 2025
