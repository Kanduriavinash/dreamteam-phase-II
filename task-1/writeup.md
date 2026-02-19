# WRITEUP FOR ALL THE BANDIT LEVELS 

------------------------------------------------
LEVEL-0

used the cat to read the file readme in the level 0 to get the password for level 1.

Level 1 Password : ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If

-------------------------------------------------
LEVEL-01

now 1st i tried to read the file using cat but later realized that it is not the correct way to read it when we see the file name as - because if we use cat - it will think as we are giving input.
I learnt a new thing that when ever the file name starts with - we have to use ./-filename to read the file. so,we have to use 

used cmd : cat ./- to read the file - .

Level 2 Password : 263JGJPfgU6LtdEvgfWU1XP5yac29mFx

---------------------------------------------------
LEVEL-02

Here the file name have spaces and starts with -.so,when we try to read the file directly we can see that it is trying to take input but we want that specific file to be read.we have to use the prior knowldge of task 1 and new thing to overcome to read a file which has spaces in its filename. which is 

used cmd : cat ./--spaces\ in\ this\ filename--

Level 3 Password: MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx

-------------------------------------------------------
LEVEL-03

Here where we have to get the file from a directory.And the file is not visible when we use ls because it is hidden,so if we want to see the hidden files we have to use ls -a which displays the hidden files and also came to know that hidden files names starts with (.) .

used cmd : cat ./...Hiding-From-You

Level 4 Password: 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ

---------------------------------------------------------
LEVEL-04

In this they asked to 1st find out the human readable file so,i used file * which tells us the file type.And i found out a ascii and read using cat which gave me password and all other gave me a machine language code something which we can not read.

use cmd: file ./-*
   cat ./-file07

Level 5 Password: 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

-----------------------------------------------------------------
LEVEL-05

"Find" which help me in this level to get the required file.Explored the Find cmnd and found out how can i use it  with the help of data given in question later found out that we can use type to search for specific type and size and even for bytes to.

used cmd : find . -type f -size 1033c

Level 6 Password : HWasnPhtq9AVKe0dmk45nxy20cvUa6EG

-------------------------------------------------------
LEVEL-06

now i used the find cmnd to search for the file which i required as before i found it using the prior hints given in question.

used cmnd : find / -type f -user bandit7 -group bandit6 -size 33c

Level 7 Password : morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj

-----------------------------------------------------------------
LEVEL-07

comapred to before very easy one.used the grep cmd to find the password with the hint given in question.

used cmnd : cat data.txt | grep millionth

Level 8 Password : dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc

------------------------------------------------------------------
LEVEL-08

in question they told that only line that occurs only once is the password so i thought to use unique and used unique with the sorted data and got the password.

used cmnd : sort data.txt | uniq -u

Level 9 Password : 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM

----------------------------------------------------------------
LEVEL-09

used grep and strings to find the human-readable strings and got the data which have these qualities and i got the required password.

used cmnd : strings data.txt | grep =

Level 10 Password : FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey

------------------------------------------------------------------
LEVEL-10

used base64 -d to decode the data in data.txt file with help of pipe too.

used cmnd :cat data.txt | base64 -d

Level 11 Password : dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr

------------------------------------------------------------------
LEVEL-11

used tr to translate the code to rotate 13 alphabets A-after rottating 13 times A will come again N and so on Z--M and same with small aplhabets. 

used cmnd : cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'

Level 12 Password : 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4

------------------------------------------------------------------
LEVEL-12
This level took 1 hour for me till now this is the hardest level i have faced.So,many new things learnt and how to decompress the files and how to extract the archieved file and how to work on a file which was restricted in the home page by copy of the original file in a temp dir and at last found the file with ascii type after too many decompressed files.

used cmnd : mkdir,cd,cp,xxd -r,file,mv,gzip -d,bzip2 -d,tar -xf,cat.

Level 13 Password : FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn

------------------------------------------------------------------
LEVEL-13

in this level they told we dont have permission to access password.

used cmd :c hmod 600 sshkey.private-> for reading the password to login using this 
ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
 method 

Level 14 Password : MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS

------------------------------------------------------------------
LEVEL-14

used netcat to send the current level password and submitted to a local service running on port 30000. after submiting it we got the level15 password.

used cmd :nc localhost 30000

Level 15 Password : 8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo

-----------------------------------------------------------------
LEVEL-15

they asked us to use ssl/tls so i used openssl a cryptographic tool which is different from before level nc->it just give raw plain text and here 30001 port required an ssl encrypted connection and nc does not ssl encrypted communications so,we used this.

used cmd : openssl s_client -connect localhost:30001

Level 16 Password : kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx

-------------------------------------------------------------------
LEVEL-16

submitted the password of level16 to a port in 31000-32000 in (31790) the port was correct and extracted the rsa private key data and pasted in the nano file and used the ssh based login as before level.
nmap used for posrt scanning between many ports.in a range.

used cmd : openssl s_client -connect localhost:31790

Level 17 Password : EReVavePLFHtFlFsjn3hyzMlvSuSAcRD

-------------------------------------------------------------------
LEVEL-17

we compared the passwords.old and passwords.new using diff and identified the single modified line in passwords.new as the password for bandit 18.

used cmd : diff passwords.old passwords.new

Level 18 Password : x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO

------------------------------------------------------------------
LEVEL-18

We bypassed the modified .bashrc logout behavior by executing cat readme directly via SSH, preventing the interactive shell from starting and successfully retrieving the password.

used cmd :ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme

Level 19 Password : cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8

------------------------------------------------------------------
LEVEL-19

we identified that bandit20-do is a setup binary owned by bandit20 by executing this we can give a command extension to it to complete our work with cat/etc/bandit_pass/bandit20 to read the [password of level 20 and got the password.

used cmd : ./bandit20-do cat /etc/bandit_pass/bandit20

Level 20 Password : 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO

---------------------------------------------------------------------




