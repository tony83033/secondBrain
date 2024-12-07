/usr/lib/systemd/system/httpd.service

/etc/systemd/system/

control which core of cpu a program wiil use
for this we need to create a unit file

command -> systemd-run date  
command -> systemd-run - MemoryLimit=1G -p CPUAffinity=1  date

this command first create a unit file and then they run date command 
now we can control date command using systemctl

and the unit file will be avaliable for life of command once command is executed (transient file )
it wiil create a new date service unit file

now we can user jurnalctl command to check log of the serviec

jurnalctl -u <servicename.service>


yum install mlocate -> if want to search some file in system we can use this command

first -> we have to create a date base for mlocate command ->

command -> updatedb 

systemd-run -p BLOCKIOWeighth=10 


command -> taskset  -p [pid]  -> this command is similer to tuna command 



