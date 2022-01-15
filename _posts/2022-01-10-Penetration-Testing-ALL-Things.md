---
published: true
---
## Penetration testing


### General Enumeration

```
nmap -vv -Pn -A -sC -sS -T 4 -p- 10.0.0.1
```

```
nmap -v -sS -A -T4 x.x.x.x
```

```
nmap –script smb-check-vulns.nse –script-args=unsafe=1 -p445 [host]
```


```
netdiscover -r 192.168.1.0/24
```


### FTP Enumeration

```
nmap –script ftp-anon,ftp-bounce,ftp-libopie,ftp-proftpd-backdoor,ftp-vsftpd-backdoor,ftp-vuln-cve2010-4221,tftp-enum -p 21 10.0.0.1
```

### Smtp Enumeration

```
nmap –script smtp-commands,smtp-enum-users,smtp-vuln-cve2010-4344,smtp-vuln-cve2011-1720,smtp-vuln-cve2011-1764 -p 25 10.0.0.1
```



Chisel.exe

Download --> https://github.com/jpillora/chisel

```
Usage:
./chisel.exe client 10.10.14.15:8000 R:9512:127.0.0.1:9512
```
