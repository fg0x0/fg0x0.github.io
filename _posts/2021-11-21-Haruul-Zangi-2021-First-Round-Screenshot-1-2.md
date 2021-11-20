---
published: true
---
# Харуул Занги 2021 эхний шат

Даалгаврын төрөл: **Web Exploitation**

Даалгаврын нэр: **Screenshot 1 ( Points 1000 )**

Даалгаврын нэр: **Screenshot 2**

<p align="center">
🐱‍💻 Зочилсон хүний тоо 🐱‍💻 
</p>
<p align="center">
  <img src="https://profile-counter.glitch.me/{2021-11-21-Haruul-Zangi-2021-First-Round-Screenshot-1-2}/count.svg">
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/hzz.png">
</p>

"Харуул Занги 2021" тэмцээний эхний шатанд Screenshot-1 даалгаврыг дангаараа бодож 1000 оноо авсан бөгөөд энэхүү бодлогын талаар яаж бодсоноо бусад багийн гишүүдтэйгээ хуваалцах нь зүйтэй болов уу гэж бодлоо

## Screenshot-1

За энэхүү даалгаврыг тэмцээний явцад амжилттай хийсэн ч тэмцээн дууссаны дараа сервер унтарсан учраас харуул занги тэмцээний Github хуудаснаас Docker файлыг авч локалаар ажиллууж даалгаврыг хийхээр бэлтгэв

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/docker-1.PNG">
</p>

Building хийж байгаа үйл явц

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/docker-2.PNG">
</p>

Өгөгдсөн IP хаяг болон портоор хандаад үзвэл бидэнд "Вэб скрийншот авах үйлчилгээ" нэртэй форм харагдана. Анх харахад URL-ээр дамжуулж хортой код хуулаад веб сервер дээр агуулагдаж байгаа скрийншот файлуудыг татаж аваад тэрэн дотроосоо **flag** агуулсан файлыг олох болов уу гэсэн төсөөлөл надад байсан  

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/screen.PNG">
</p>

Формд ямар нэгэн утга оруулаад үзэхэд энд хадгалагдлаа гэх мэт **random generate URL** өгч байсан бөгөөд энэхүү URL-руу хандаад үзвэл **File Not Found** алдааг өгч байсан учраас **Source Code Analyze** хийж үзэхээр шийдэв. Хайлтын үр дүнд **./feed.php** гэсэн файлыг олов. Магадгүй сэжигтэй байж болох л юм тэ шалгаад үзье

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/screen-2.PNG">
</p>

Файлруу хандаад үзэхэд вебсайтуудын **Comment** бичдэг хэсэгтэй адилхан харагдав. Үүнийг хараад олон ийм формтой таарж байсан хүний хувьд шууд л **Stored XSS** байна шүү дээ гэж бодсон.

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/screen-3.PNG">
</p>

Юу ч гэсэн эхний ээлжинд хамаагүй утга оруулаад үзье гэж бодсон. Магадгүй NoSQL , PHP-тэй холбоотой Bug байх ч юм билүү тэ хэн мэдлээ ххэ

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/screen-4.PNG">
</p>

Мэдээж хүлээлт өндөр байгаагүй учраас **Hello** гэсэн үгийг маань хэвлэж байсан. Өөр аргаар л үзье даа

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/screen-5.PNG">
</p>

Хамгийн энгийн XSS payload-г бичиж тест хийхээр шийдэв. Хэрвээ payload маань ажиллаж байвал окэй миний бүх payload асуудалгүй ажиллах ёстой. Аан ажиллахгүй байвал яг аль хэсгийг нь **replace** хийх байгааг хайж олох шаардлага үүснэ

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/screen-6.PNG">
</p>

Үр дүнд: <script>alert(1);</script> --> <>alert(1); гэсэн л хариу ирэв. Мэдээж скрипт маань бүрэн ажиллаагүй учраас энэхүү **replace** -г **bypass** хийх аргаа бодож эхлэв

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/screen-7.PNG">
</p>

Ер нь бол янз бүрээр л давах боломжтой жишээ нь: `<scr<script>ipt> , <sscriptcript>` гэх мэт миний хувьд яаж шалгалтыг давсан вэ гэхээр `<scRipt>` буюу дан ганц **R** үсгийг томоор бичихэд л болно гэж үзсэн

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/screen-8.PNG">
</p>

Тийм ээ. Скрипт маань амжилттай ажиллаж **pwned by fg0d** гэсэн **alert** мэдээллийг бидэнд харууллаа

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/screen-9.PNG">
</p>



<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/dura.gif">
</p>



<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/screenshot/screen-10.PNG">
</p>