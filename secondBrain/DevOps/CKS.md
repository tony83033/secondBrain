Container look like a O.S but actually it is a process

because docker container is just a normal linux process , we can apply all the concept of securing a process to secure a container  line SELinux (MAC) or AppArmor

k8s has it's own selinux resourses , but exactly like seLinux

Note -> any process  just make sysCall to (O.S -> KERNEL) to get things done  fdfdf

command -> strace   -c cat /etc/passwd  -> this strace command will show how many syscall is being made by a command

In security we never restric any command for example we , restric cat command then someone else will create some cat1 command to do the same 

that's why we restrict sysCall fippo.io/linux-syscall-table


we only  apply sysCall restrict on base Node or worker node because pod or container is just a process it self

Seccomp (secure computing mode ) Filter a process system call , we apply (seccomp filter to restrict sysCall in worker node )

cd /proc/<processId>

every process had it's status file when you cat statue file you can see syscall

we need to to decode using capsh --decode <sha>

getpcap <process id>

======

kis./example/pods.security/security-context-3
kuer.io/docs/task/confuigur-pod-container/security-context

kubectl creat deployment myweb --image=httpd --dry-run -o yaml > httpd.yaml


kubeltl apply -f httpd.yaml

kubeclt get pod


kubeclt exec -it pode name --bash go inside heood 
=================================================
to remove any capability go to yaml fine add a keywork  call securityContext:

securityContext what you want to apply seLinux or apparmor , or cor seccompot 









