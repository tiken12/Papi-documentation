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

