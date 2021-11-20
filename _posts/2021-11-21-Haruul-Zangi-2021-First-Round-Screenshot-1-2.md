---
published: true
---
# Харуул Занги 2021 эхний шат

Даалгаврын төрөл: **Web Exploitation**

Даалгаврын нэр: **Screenshot 1 ( Points 1000 )**

Даалгаврын нэр: **Screenshot 2**

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/hzz.png">
</p>

`Харуул Занги 2021` тэмцээний эхний шатанд `Screenshot-1` даалгаврыг дангаараа бодож `1000` оноо авсан бөгөөд энэхүү бодлогын талаар яаж бодсоноо бусад багийн гишүүдтэйгээ хуваалцах нь зүйтэй болов уу гэж бодлоо

## Screenshot-1

За энэхүү даалгаврыг тэмцээний явцад амжилттай хийсэн ч тэмцээн дууссаны дараа сервер унтарсан учраас харуул занги тэмцээний `Github` хуудаснаас `Docker` файлыг авч локалаар ажиллууж даалгаврыг хийхээр бэлтгэв

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/docker-1.PNG">
</p>

`Building` хийж байгаа үйл явц

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/docker-2.PNG">
</p>

Өгөгдсөн IP хаяг болон портоор хандаад үзвэл бидэнд `Вэб скрийншот авах үйлчилгээ` нэртэй форм харагдана. Анх харахад URL-ээр дамжуулж хортой код хуулаад веб сервер дээр агуулагдаж байгаа скрийншот файлуудыг татаж аваад тэрэн дотроосоо `flag` агуулсан файлыг олох болов уу гэсэн төсөөлөл надад байсан  

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/screen.PNG">
</p>

Формд ямар нэгэн утга оруулаад үзэхэд энд хадгалагдлаа гэх мэт `random generate URL` өгч байсан бөгөөд энэхүү URL-руу хандаад үзвэл `File Not Found` алдааг өгч байсан учраас `Source Code Analyze` хийж үзэхээр шийдэв. Хайлтын үр дүнд `./feed.php` гэсэн файлыг олов. Магадгүй сэжигтэй байж болох л юм тэ шалгаад үзье

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/screen-2.PNG">
</p>

Файлруу хандаад үзэхэд вебсайтуудын `Comment` бичдэг хэсэгтэй адилхан харагдав. Үүнийг хараад олон ийм формтой таарж байсан хүний хувьд шууд л `Stored XSS` байна шүү дээ гэж бодсон.

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/screen-3.PNG">
</p>

Юу ч гэсэн эхний ээлжинд хамаагүй утга оруулаад үзье гэж бодсон. Магадгүй `NoSQL` , `PHP`-тэй холбоотой `Bug` байх ч юм билүү тэ хэн мэдлээ ххэ

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/screen-4.PNG">
</p>

Мэдээж хүлээлт өндөр байгаагүй учраас `Hello` гэсэн үгийг маань хэвлэж байсан. Өөр аргаар л үзье даа

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/screen-5.PNG">
</p>

Хамгийн энгийн `XSS payload`-г бичиж тест хийхээр шийдэв. Хэрвээ `payload` маань ажиллаж байвал окэй миний бүх payload асуудалгүй ажиллах ёстой. Аан ажиллахгүй байвал яг аль хэсгийг нь `replace` хийж байгааг хайж олох шаардлага үүснэ

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/screen-6.PNG">
</p>

Үр дүнд: `<script>alert(1);</script>` --> `<>alert(1);` гэсэн л хариу ирэв. Мэдээж скрипт маань бүрэн ажиллаагүй учраас энэхүү `replace` -г `bypass` хийх аргаа бодож эхлэв

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/screen-7.PNG">
</p>

Ер нь бол янз бүрээр л давах боломжтой жишээ нь: `<scr<script>ipt> , <sscriptcript>` гэх мэт миний хувьд яаж шалгалтыг давсан вэ гэхээр `<scRipt>` буюу дан ганц `R` үсгийг томоор бичихэд л болно гэж үзсэн

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/screen-8.PNG">
</p>

Тийм ээ. Скрипт маань амжилттай ажиллаж `pwned by fg0d` гэсэн `alert` мэдээллийг бидэнд харууллаа

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/screen-9.PNG">
</p>

<p align="center">
ОДОО БҮГДЭЭРЭЭ ЗҮГЭЭР ДУРААРАА ДУРГИХ БОЛОМЖТОЙ 
</p>

<p align="center">
WE CAN FREE TO FLY
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/dura.gif">
</p>

Хэрэглэгч талаас буюу бид нар тухайн вебсайтын эмзэг байдлаар дамжуулж ард нь ажиллаж байгаа серверлүү хортой хүсэлт илгээнэ. Илгээхдээ дотор нь буцаад холбогдох ямар нэгэн хаяг тавьж өгөх шаардлага үүсэж байгаа биз тэгэхгүй бол эзэнгүй юм шиг таны хортой код хаашаа явахаа мэдэхгүй хүсэлтээ тухайн хэсэгтээ л дамжуулаад байна гэсэн үг л дээ. За тэгэхээр буцаад ирэх хүсэлтийг нь барьж авахын тулд онлайн [webhook](https://webhook.site/) ашиглаж барих боломжтой эсвэл [requestb.in](https://pipedream.com/requestbin) ч юм уу тэ хүссэнээрээ л хий

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/screen-10.PNG">
</p>

XSS хортой кодон дотроо [webhook](https://webhook.site/)-ээс авсан public URL-аа бичээд `Санал Явуулах` дарна

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/screen-11.PNG">
</p>

Script маань амжилттай ажилласан эсэхийг статикаар анализ хийж үзвэл `alert`-н ард хэсэгт зурагны `icon` гарч ирсэн байгааг харж болно. Тэгэхээр скрипт асуудалгүй ажилласан байна гэж ойлгож болно

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/screen-12.PNG">
</p>

[webhook](https://webhook.site/) дээр орж ирсэн хүсэлтийн хариуг харвал нийтдээ 2 `response` ирсэн байна. Эхний хариу нь миний өөрийн Session ID болон мэдээллийг буцааж харуулсан байгаа харж болно 

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/screen-13-backup.PNG">
</p>

Дараагийн хариуг харвал админ хэрэглэгчийн `Cookie` утга байгааг олж харна. Бид вебсайтын цоорхойг ашиглаж ард нь ажиллаж байгаа админ хэрэглэгчийн Session-г амжилттай Hijacking хийчихлээ. 

**Screenshot-1 флаг:** `HZ{ye@h_admin_cook1e_and_fl@g_0f_ScreenShot_1}`

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/screen-14.PNG">
</p>

За дараагийн үргэлжлэл хэсэгрүүгээ орж харвал саяны Hijacking хийсэн хэсэгт `http://screen/god-wisper.php` гэсэн `referer` байгааг харж болно. Энэ мэдээж бидэнд маш том `hint` өгч байна

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/screen-15.PNG">
</p>

Веб хөтөчийнхөө `Proxy`-г асааж байгаад туршилт хийж үзье

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/screen-16.PNG">
</p>

Хамгийн эхний `index.php`-д харагдаж байсан форм дотор тест мэдээллийг оруулаад үзсэн

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/screen-17.PNG">
</p>

Оруулж байх үедээ хүсэлтийг нь дундаас нь барьж аваад харвал `url=hellotest` гэж дамжиж байна. Referer нь: `http://127.0.0.1:1337` буюу өөрийн локал хаяг байв

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/screen-18.PNG">
</p>

Үүнийг олсон мэдээллээрээ `http://screen/admin.php` болгож өөрчлөөд `forward` хийгээд үзвэл

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/screen-19.PNG">
</p>

Эцэст нь бид `Screenshot-2` даалгаврын флагыг оллоо

**Screenshot-2 флаг:** `HZ{2440a6c77ef002838ca441be4a5ec97d}`

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/flagg.jpg">
</p>
