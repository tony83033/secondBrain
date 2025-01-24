
planning of syscall

strace -c cat /etc/passwd -> find total numer of syscall for cammand (cat /etc/passwd)

13:20-> 14:06 -> talk about youtube channel

command -> seccomp

17:22 ->  18:17 -> talk about youtube channel

command -> auditctl -> we can create rule to watch an file
-w - watch
-p -> permission
-k key -> tag for searching 
auditctl -w /etc/passwd -p rwa  -> now this command will start creating log's in /var/audit

22:20
audit -w /etc/passwd -p rwa -k mypasswd -> 

man auditctl

auditclt -l -> it wiil list all the custom rules 

aussearch -k mypasswd

=====================================
add tracking directly on syscall
-p -> process id 
22722 is a procces id of a proces any be changed
command -> strace -p 22722 -> show syscall in real time of any process
command -> strace -p <prcessid> -e write -> only track write syscall

commad -> auditctl -a always,exit -s write -s bind -l mmypasswd -F b64

-a always, exit -> always watch till exit 

-F specy particture of system 