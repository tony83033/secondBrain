Container look like a O.S but actually it is a process

because docker container is just a normal linux process , we can apply all the concept of securing a process to secure a container  line SELinux (MAC) or AppArmor

k8s has it's own selinux resourses , but exactly like seLinux

Note -> any process  just make sysCall to (O.S -> KERNEL) to get things done 

command -> strace   -c cat /etc/passwd  -> this strace command will show how many syscall is being made by a command

In security we never restric any command for example we , restric cat command then someone else will create some cat1 command to do the same 

that's why we restrict sysCall 



