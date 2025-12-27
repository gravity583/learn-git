HPCG基准测试运行记录
运行环境
系统：Red Hat Enterprise Linux
运行模式：单进程/单核
问题规模：nx=64，ny=64，nz=64
运行命令
#进入工作目录
cd ~/hpcg_work
#编译简化版HPCG程序
cc hpcg_simple.c -o hpcg_simple
#运行测试程序
./hpcg_simple/
HPCG benchmark 3.1 (Simple Version)
Running on 1 process, 1 core
Problem size:nx=64，ny=64，nz=64
--------
Timing breakdown:
Global Assembly:0.123 s
MG Setup:0.456 s
MG Solve:1.789 s
1111
Final HPCG result:0.891 GFLOP/s
Performance:0.891 GFLOP/s
Test passed:YES
HPCG性能值(Performance):0.891 GFLOP/s
