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
 
