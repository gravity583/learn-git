#Week 2 learning record -应天仁

#What I did this week?
This week, I learned about HPL and HPCG. I studied their purposes, main parameters, and
configuration files (such as the HPL.dat file), as well as their functions in benchmarking
high-performance computing systems.

#The main parameter
HPL: N(Matrix Size) NB(Block Size) P(Process Grid) Q(Process Grid) Gflops(Performance 
Metrics)

HPCG: nx,ny,nz(Local Grid Dimensions) runtime(Target Runtime) npx,npy,npz(Process Grid) 
Gflops(Performance Metrics)

#The difference between HPCG and HPL
HPL is used to show the maximum speed of the computer's computational performance under
ideal conditions. But HPCG​ shows the practical speed​ under real-world constraints.

The HPCG Efficiency​ (HPCG Gflops/HPL Gflops) is a percentage that shows how much of the 
computer's top speed it can actually use for real work. A high percentage means it's 
efficient in practice.

#Problem
I still do not fully understand the internal computation and execution processes of
HPL and HPCG.

