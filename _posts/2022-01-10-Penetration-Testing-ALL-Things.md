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


Chisel.exe

Download --> https://github.com/jpillora/chisel

```
Usage:
./chisel.exe client 10.10.14.15:8000 R:9512:127.0.0.1:9512
```
