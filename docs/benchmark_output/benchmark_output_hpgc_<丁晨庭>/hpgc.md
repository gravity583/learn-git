sudo apt update && sudo apt install -y gcc gfortran openmpi-bin libopenmpi-dev make libopenblas-dev
git clone https://github.com/hpcg-benchmark/hpcg.git && cd hpcg
cp setup/Make.Linux . || cp setup/Make.UNKNOWN Make.Linux
sed -i 's/CC =.*/CC = mpicc/; s/CXX =.*/CXX = mpicxx/; s/FC =.*/FC = mpif90/' Make.Linux
make clean && make arch=Linux CC=mpicc CXX=mpicxx FC=mpif90 BLAS_LIB=-lopenblas
echo -e "128 128 128\n180\n4" > hpcg.dat
mpirun -np 4 ./xhpcg > hpcg_result.txt
