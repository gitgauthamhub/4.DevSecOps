# 4.DevSecOps
==========================

Command Mode ==>
:q ==> quit the file, 
:wq ==> write and quit, 
:q! ==> exit without saving, 
:wq! ==> Force write and quit

Goto Gitbash
vim editor ==> 3 modes - Esc mode, Command mode, Insect mode

$ vim devops.txt  
  press "i" , press "Esc" , ":q!"      
  Note : WithOut Saving 

$ vim devops.txt 
  press "i" 
  This is joindevops session
  press "Esc" , ":wq!"                 
  Note : Its Saving 

==========================
$ sudo su -
cp /etc/passwd  users
vim users

:/ec2-user                             
Note : Now ec2-user  pop display 

:/sbin                               
==> Search for the word from Top

:?/sbin                                
==> Search for the word from Bottom

:noh                                   
==> No Highlight

:set nu                               
==> Numbers 

:set nonu                             
==> No Number 

:27d                                  
==> Deleted particular 27th row

:%d                                   
==> Total data deleted

:q!                                    
==> Exit without saving

:4s/sbin/SBIN                          
==> Replace sbin place SBIN  Note: 1st occurence 

:7s/sbin/SBIN

:8s/sbin/SBIN/g                      
==> All occurance in that line  will be Captial letters

:%s/sbin/SBIN/g                        
==> All occurance in the file will be Capital letters

U  ==> Escmode

==========================

yy                                    ==> Copy
p                                     ==> Paste
10yy                                  ==> Copy
dd                                    ==> Delete
gg                                    ==> Top
Shift + g                             ==> Bottom

==========================

Linux Administration       
1. User Management                   How to user // CRUD ==> Create, Read, Update, Delete
                                     Note : Doing these i will be Administrator // gautham is a User // & Goto root 

$ sudo su -
# Clear
# Useradd  gautham
# id gautham

In linux two types of groups - Primary group & Secondary group    // 1 Primary group & atleast  1 Secondary group 
group ==> List of Similar Users
devops team have 15 members
create devops group, add team members to the group
In Linux wen you create user, By default group also will be created with the same name

# cat /etc/passwd 
# cat /etc/group

# groupadd devops                    
Note : Now groupadd devops // devops group will be created

# cat /etc/group

# usermod -g devops grk              
Note : usermod -g devops grk   // Here small -g is a primary group
# id grk 

# groupadd testers 
# usermod -aG testers grk           
Note : usermod -aG testers grk  // Here Captial G is a Secondary group 
# id grk

# userdel grk                       
==> Deleted User
# id grk
# cat /etc/group 

# groupdel grk                      
==> Delete Group also

# cd /home/grk                     
==> Delete Directory also
# cd
# id grk 

# useradd grk 
# id grk

# usermod -g devops grk
# usermod -aG devops grk grk
# usermod -aG testers grk
# id grk

# gpasswd -d grk testers
# id grk                         
==> Compulsory One group must 


# usermod -g grk grk
# id grk 
# userdel grk
# cat /etc/group 

   
How to login User ?

# useradd grk
# passwd  grk                 
==> Give password

>> Goto new Duplicate window
$ ssh grk@3.231.56.105
>>  Note : Permission are Denied 

>> Goto old Gitbash Window
>>  Note : In Linux by Default Login to Keys only // Don't use passwords

# vim/etc/ssh/sshd_config            
>> Note : If you change any Behaviour you need to changes Config files // default process
:?Password = xxxx                  

>> Note : " Password Authencation no " 
>>  i
>> Note :  Now change " yes "

 >> esc   >> :wq!   >> enter


# sshd -t                           
Note : Check for testing any changes here done or not

# systemctl restart sshd 

>> Goto new Duplicate window
# ssh grk@3.231.56.105 
:password = xxxx         
                  
