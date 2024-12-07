
command -> lshw 

this command will tell about hardware in your system

lshw -c memory



lshw -c storage 

lshw -c network

lshw -businfo

lshw -html -> this command will collect all the info and make a webpage

sudo bash -c "lshw -html > os.html"





/sys/dev / all the hardware programm kernal mentain all the info about hardware in this dir

vim /proc/cpuinfo -> inside this foleder we have alot of subdir one of is cpu0, cpu1 

/proc/ -> is  a spacial dir , all the file present in this dir is on ram not in harddist

vi /cpu1/online  

command -> nproc


13:07 to 19:26 cut -> (redhat anunsiment)

=============================================

userSpace 
KernalSpace/SystemSpace

command -> systemctl -t slice 
command -> systemclt cgls or systemct cgtop

dd if=/dev/dero of=/dev/null -> stress testing
26:00


control time sharing in cpu using cgroup

command -> vmstat 
comand -> yum install mpstat

mpstat -P All

confFile sudo vi /etc/systemd/system.conf -> common or default seeting for systemd 


yum install perf 

sudo peft sched record --sleep 20 
chrt -l -> list all the avaliable sheduling algo in linux
=

==========================================
topic for Future learning . 
In Linux, a NUMA node is ==a group of processors and memory that share local access to a subset of the system's memory==:=
=====================================================

