---
published: true
---
### Challenge Type: Web Exploitation
### Challenge Name: Shao Kahn

<p align="center">
🐱‍💻 Зочилсон хүний тоо 🐱‍💻 
</p>
<p align="center">
  <img src="https://profile-counter.glitch.me/{2021-10-02-Haruul-Zangi-2018-final-round-Web-PHP}/count.svg">
</p>

> PHP symlink , base64 , Web Exploitation

<p align="center">

<img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/hz-2018/hz-18-final-round-1.png">

</p>
Харуул Занги 2018 тэмцээний эцсийн шатны Web exploitation төрлийн эхний даалгавар болох “Shao Kahn” даалгаврын writeup — ыг хүргэж байна.

<p align="center">
<img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/hz-2018/hz-18-final-round-2.png">
</p>

Даалгаврыг нээхэд бидэнд /tmp/shaokahnflag.php гэсэн path өгөгдсөн байсан. Бидэнд өгөгдсөн Url → [http://218.100.84.106:8060/]() нэвтрээд харахад

<p align="center">
<img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/hz-2018/hz-18-final-round-3.png">
</p>

Online compiler шиг interface -тэй дотор нь echo буюу хэвлэх коммандаар ShaoKahn гэсэн үгийг хэвлэсэн байлаа.

<p align="center">
<img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/hz-2018/hz-18-final-round-4.png">
</p>

Яг энэ үед надад төрсөн санаа байгаагүй бөгөөд эхний өгөгдөлрүүгээ буцаад сэжигтэй зүйл байгаа эсэхийг лавлаж харлаа. **Их удаан харсан xD** За ерөнхийдөө эхлээд уламжлалт вэбийн шалгах процесуудаа шалгаад үзье гэж бодсон.

<p align="center">
<img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/hz-2018/hz-18-final-round-5.png">
</p>

[http://218.100.84.106]() гэсэн бидэнд өгөгдсөн Url — д robots.txt -г оруулж үзэхэд shao.gif зураг гарч ирсэн. Сүүлийн үед вэбийн даалгаврууд forensics ялангуяа steganography — тай хосолсон маягаар их орж ирдэг болсныг санаад зурган доторх зүйлсийг нилээдгүй хайж үзсэн. Даан ч юу ч олдоогүй учир дан вэб бровсер дээрээ шалгалтуудаа хийнэ гэж ойлгосон.

<p align="center">
<img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/hz-2018/hz-18-final-round-6.png">
</p>

Үүний дараагаар PHP дээрх compiler байсан мөн бидэнд path , link өгөгдсөн тул эхлээд PHP link-г google-ээс хайлт хийсэн.

<p align="center">
<img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/hz-2018/hz-18-final-round-7.png">
</p>

За хайлтын үр дүнд маш их PHP source code -нуудаас хамгийн байж болох хувилбарыг оллоо.($target , $link) Гэхдээ уг code -нд link ээс утгаа аваад хэвлэх үйлдэл гэх мэт зарим функцүүд байгаагүй учир доошлуулаад хартал.

<p align="center">
<img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/hz-2018/hz-18-final-round-8.png">
</p>
<p align="center">
symlink() , readlink() , linkinfo() гэсэн 3 ойлголт байлаа symlink буюу symbolic -ыг үүсгэх боломжтой гэдгийг хараад судлахаар шийдэв.
</p>
<p align="center">
<img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/hz-2018/hz-18-final-round-9.png">
</p>
<p align="center">
symlink() -ээс readlink-н $link -г унших болох кодыг оллоо.
</p>
<p align="center">
<img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/hz-2018/hz-18-final-round-10.jpeg">
</p>

Үүний дараа өмнөх хэсэгт уламжлалт шалгалт хийх үедээ нэг зүйлийг мартсан байснаа санаад хурдан туршихаар болов.

<p align="center">
<img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/hz-2018/hz-18-final-round-11.png">
</p>

Url дотор байгаа файлуудыг шалгаж үзтэл. [http://218.100.84.106:8060/flag]() буюу уг url дотор flag гэсэн файл байгаа эсэхийг шалгахад үр дүнд нь “flag” файл байж таарсан. x))))

<p align="center">
<img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/hz-2018/hz-18-final-round-12.png">
</p>

<p align="center">
flag.php файлаа татаж авлаа.
</p>
  
<p align="center">
<img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/hz-2018/hz-18-final-round-13.png">
</p>
<p align="center">
php файлыг терминал орчноос php flag коммандаар ажиллуулах үед флаг маань гараад ирэх нь тэр xD
</p>
<p align="center">
HZ{fastcg1pack3t.Really!!}
</p>

Эндээс дүгнэхэд CTF -н даалгаврыг уншиж байх үед энэ их хэцүү даалгавар , хэцүү байх болно гэх мэт тайлбартай байхад шууд хүлээж аваад за би чадахгүй юм байна гэж бодоод хэрэггүй шүү xD Ямар ч даалгавар байсан жижиг зүйлсийг нэг бүрчлэн шалгаж үзэх хэрэгтэй юм шиг санагдсан. За тэгээд бүгдэнд нь амжилт хүсье!
