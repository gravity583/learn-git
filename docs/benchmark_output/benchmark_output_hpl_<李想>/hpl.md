                             The executed command
$ sudo apt install build-essential hwloc libhwloc-dev libevent-dev gfortran
$ git clone https://github.com/xianyi/OpenBLAS.git
$ cd OpenBLAS
$ git checkout v0.3.21
$ make
$ make PREFIX=$HOME/opt/OpenBLAS install
$ wget https://download.open-mpi.org/release/open-mpi/v4.1/openmpi-4.1.4.tar.gz
$ tar xf openmpi-4.1.4.tar.gz
$ cd openmpi-4.1.4
$ CFLAGS="-Ofast -march=native" ./configure --prefix=$HOME/opt/OpenMPI
$ make -j 16
$ make install
export MPI_HOME=$HOME/opt/OpenMPI
export PATH=$PATH:$MPI_HOME/bin
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$MPI_HOME/lib
$ wget https://netlib.org/benchmark/hpl/hpl-2.3.tar.gz
$ gunzip hpl-2.3.tar.gz
$ tar xvf hpl-2.3.tar
$ rm hpl-2.3.tar
$ mv hpl-2.3 ~/hpl
$ cd hpl/setup
$ sh make_generic
$ cp Make.UNKNOWN ../Make.linux
$ cd ../
$ nano Make.linux
$ cd bin/linux
$ nano HPL.dat
$ ./xhpl
                                 The HPL Output
- The matrix A is randomly generated for each test.
- The following scaled residual check will be computed:
      ||Ax-b||_oo / ( eps * ( || x ||_oo * || A ||_oo + || b ||_oo ) * N )
- The relative machine precision (eps) is taken to be               1.110223e-16
- Computational tests pass if scaled residuals are less than                16.0

================================================================================
T/V                N    NB     P     Q               Time                 Gflops
--------------------------------------------------------------------------------
WR11C2R4        8192   232     1     1               7.58             4.8340e+01
HPL_pdgesv() start time Sat Dec 27 03:57:44 2025

HPL_pdgesv() end time   Sat Dec 27 03:57:52 2025

--------------------------------------------------------------------------------
||Ax-b||_oo/(eps*(||A||_oo*||x||_oo+||b||_oo)*N)=   2.33031626e-03 ...... PASSED
================================================================================

Finished      1 tests with the following results:
              1 tests completed and passed residual checks,
              0 tests completed and failed residual checks,
