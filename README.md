# Papi-documentation

module avail papi
module load papi/6.0.0
module list
papi_avail
papi_avail | grep -c "PAPI"
papi_event_chooser

# checking for counter
papi_component_avail
#verify permission
sudo papi_avail
#check CPU support
cat /proc/cpuinfo | grep "model name"
#Load Performance Monitoring Kernel Modules
lsmod | grep msr
lsmod | grep perf

#If available test specific event
papi_event_chooser PRESET PAPI_TOT_INS PAPI_TOT_CYC

https://github.com/icl-utk-edu/papi/releases/download/papi-7-2-0b1-t/papi-7.2.0b1.tar.gz
 
mkdir papi
 
mv papi-7* papi
 
tar zxf papi-7*
 
more INSTALL.txt
 ls
#Configure script
 ../papi-7.2.0b1/src/configure --prefix=$(HOME)/papi/install
 
# to remove
 rm -rf build 
 
  ./configure --prefix=$HOME/papi/install

  make
  make test
  make fulltest
  make install
  make install-man
  make install-tests

  vim
  vim .bash_profile
  o
  PATH=$HOME/papi/install/bin:$PATH
  . .bash_profile 
  echo $PATH
  which papi_avail
  man papi_avail
  
  cat /proc/sys/kernel/perf_event_paranoid

  ./configure --help | grep papi

    ./configure --prefix=/home/walcius/ovis


   ./packaging/make-all-top.sh

   export CYTHON=cython-3.11 PYTHON=/usr/bin/python3.11 PYTHON_VERSION=3.11


   vim .bash_profile
   . .bash_profile
   which ldmsd
 
  man ldmsd_controller

 module list
module load gcc/13.2.0
module load openblas/0.3.23
module load papi/6.0.0
module load openmpi/4.1.6

mpirun --prefix /opt/openmpi-VERSION -n 4 a.out
mpirun -np 16 ./xhpl
mpirun --debug-daemons -np 16 ./xhpl


NEW 

[walcius@blake ~]$ module list

Currently Loaded Modules:
  1) gcc/13.2.0   2) papi/6.0.0

 

[walcius@blake ~]$ module load openblas/0.3.23
[walcius@blake ~]$ module load openmpi/4.1.6
[walcius@blake ~]$ module list

Currently Loaded Modules:
  1) gcc/13.2.0   2) papi/6.0.0   3) openblas/0.3.23   4) openmpi/4.1.6

 

[walcius@blake ~]$ mpirun --version
mpirun (Open MPI) 4.1.6

Report bugs to http://www.open-mpi.org/community/help/
[walcius@blake ~]$ nano mpi_test.c
-bash: nano: command not found
[walcius@blake ~]$ nano
-bash: nano: command not found
[walcius@blake ~]$ 
[walcius@blake ~]$ nano mpi_test
-bash: nano: command not found
[walcius@blake ~]$ vim mpi_test.c
[walcius@blake ~]$ mpicc -o mpi_test mpi_test.c
[walcius@blake ~]$ mpirun -np 4 ./mpi_test
--------------------------------------------------------------------------
The library attempted to open the following supporting CUDA libraries,
but each of them failed.  CUDA-aware support is disabled.
libcuda.so.1: cannot open shared object file: No such file or directory
libcuda.dylib: cannot open shared object file: No such file or directory
/usr/lib64/libcuda.so.1: cannot open shared object file: No such file or directory
/usr/lib64/libcuda.dylib: cannot open shared object file: No such file or directory
If you are not interested in CUDA-aware support, then run with
--mca opal_warn_on_missing_libcuda 0 to suppress this message.  If you are interested
in CUDA-aware support, then try setting LD_LIBRARY_PATH to the location
of libcuda.so.1 to get passed this issue.
--------------------------------------------------------------------------
Hello from rank 2 out of 4 processes!
Hello from rank 0 out of 4 processes!
Hello from rank 3 out of 4 processes!
Hello from rank 1 out of 4 processes!
[blake:3550496] 3 more processes have sent help message help-mpi-common-cuda.txt / dlopen failed
[blake:3550496] Set MCA parameter "orte_base_help_aggregate" to 0 to see all help / error messages
[walcius@blake ~]$ 
