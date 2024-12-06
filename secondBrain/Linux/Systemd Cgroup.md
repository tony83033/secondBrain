
00:23

00:35 00:54 -> cut 

01:31 -> 01:35 cut 
02:16 -> 02:37 cut (screen share)
06:39 -> 08:16 cut

55:24 -> 55:58 cut  -> (break )
sudo data > pop11.txt -> there is 2 command sudo is applyed to data but not > pop11.txt that

sudo bash -c "cat > pop11.txt"


20:32 -> 21:21 cut -> (session close of ssh)

chmod u+s /usr/bin/cat
chmod u-s /usr/bin/cat


netstat -tnlp 

================================================================

start a simple web server using httpd 

now we have to give perticuler ram, cpu , resources to this httpd in 


usr/lib/systemd/system -> location of all the systemd file  we can edit but bot good pratict , we can't role  base to original state 

/etc/systemd/system -> for edit config


jurnalctl -u httpd.service -> show all the logs of unit file 

systemctl cat httpd.service

systemctl edit httpd.service 

systemclt show httpd.service -> show all the cgroup implemented in program


/etc/systemd/system /

make a folder -> httpd.servce.d 
and make a file with conf extencen
examle 

vim vimal.conf
[Service]
MemoryLimit=1G save and exit

how you have to update systemd that you have create a new conf file 

command -> systemclt daemon-reload 

and restart the httpd service also 
command -> systemctl restart httpd 

make grep command case insencetive 

grep -i 

pstree

systemd-delta











