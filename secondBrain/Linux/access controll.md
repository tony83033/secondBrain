

In linux user's don't decide which file they can access or not
in LInux files decide which user can access them

In Linux we use Discretionary access controll (DAC)

in SELinux we use MAC (Mandatory access control)

to list file permission use -> ls -l <filename>

Opration we can do in file (rwx) read , write and execute
r -> 4
w -> 2
x -> 1

rwx-rwx-rwx       user,group,otherUser -> total 9 bits

to give permission to only otherUser use -> chmod o+w <filename>

rwx-rwx-rwxt -> Advance
=================================================
there are 3 types of relanship between user and file 
1) user Owner or auther
2) group owner
3) others

=================================================
About group in Linux
command -> groupadd <groupname>
all the info of group store in /etc/group

groupname:groupPassword

Groupname:x::GID:members

-> group password store in /etc/gshadow -> in group file we only store pointer x

command -> useraddd -G <groupname> <username> -> add in group while creating user

command -> usermod -G <group> <username>

command -> groups -> show how meany group membership a user have

note in previous command -> G is capital not small 

by default a user have personal group with same name

To change group of a file or folder

command -> chgrp <groupname> ./project -> project is a dir

chgrp is used to change group ownership of a file or dir

========================================
To change the owner of a folder or file use this command
command -> chown <username> ./project  -> project is a dir 

command -> chmod u-w ./project
=================================================

advance permision

SGID , SUID ,  STICKY BIT , ACL

=============================================
STICKY BIT 
OCTAL VALUE OF STICKY BIT = 1
Sticky bit is used  to restricts file deletion and renaming within a directory , if sticky bit is assign only owner will be able to delete or rename

command -> chmod +t /project

command -> find / -type d -perm -1000 -> this command will show which file or folder have sicky bit

======================================================
SUID -> set user id

A spacial permission flag in Lunux that allows users to run executables with the privileges of the files's owner.  shows as 's' or 'S'

if suid is set then only owner of file will be able to execute it , if any other user execute the the  file, 

command -> chmod u+s /usr/bin/ls   -> set suid in ls file

commad -> chmod u+s <filename> or chmod u-s <filename>

command -> find / -perm /u=s 
=======================================================

SGID

same as SUDI but for group

if set on a dir any file createdi n the dir will have thteir group ownership set to that of the dir owner

command -> chmod g+s <filename>  or chmod g+s <filename>



====================================

ACL (ACCESS CONTROL LIST)

getfacl (get file clt)

setfacl (set file acl)

setfile -m u:harry:xr /dir  -> -m = modify

setfacl -m g:lwgroup /dir -> give specific permission to group

We can give specific permission to every user using ACL

remove all the permission of acl
setfacl -b /dir -> It will remove all the acl

Note -> If you want to apply acl for all user we can use(::)
setfacl -m u:: -> this command will give (rwx) to all the user

setfacl -m g:: -> same for group also give (rwx) to all the group


getfacl --omit-heder /dir -> it mostly user in automation, when we don't want headers in output

Mask in ACL

setfacl -m m::x /dir  -> we are limiting all the user to only (x ) permission , however then may have rw or rwx permission but because of mask they all ther limited to only (x) permission

Defult permission in ACL

using default , all the file will inhirent permission from parent folder 

setfacl -m d:u:vimal /lwdata





=======================================================

















