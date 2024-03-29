---
published: true
---
## Stack Based санах ойн халилт халдлагын тухай
<p align="center">
🐱‍💻 Зочилсон хүний тоо 🐱‍💻 
</p>
<p align="center">
  <img src="https://profile-counter.glitch.me/{2021-10-09-Stack-Based-Buffer-Overflow-x86-Linux}/count.svg">
</p>

<p align="center">
  <img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/stack/stackk.jpeg">
</p>

Буфер халих нь үйлдлийн системийн одоо байгаа програм хангамжийн алдаа эсвэл тэдгээрийг гүйцэтгэх явцад гарсан хариу үйлдэл юм. Сүүлийн 10 жилийн хугацаанд програм хангамжийн дийлэнх бүтэц энэхүү эмзэг байдалтай байдаг. Програмчлалын алдаан дээр ихэвчлэн гардаг бөгөөд энэ нь C эсвэл C ++ гэх мэт abstract хэлийг програмчлах үед анхааралгүй байдлаас болж буфер халихад хүргэдэг.

Эдгээр хэлийг машины код дээр хөрвүүлдэг бөгөөд Java эсвэл Python гэх мэт abstract хэлнүүдээс ялгаатай нь үйлдлийн системийн удирдлагын бүтэц бараг байдаггүй. Буфер халих нь хэт том хэмжээтэй өгөгдлийг хангалттай том биш үйлдлийн системийн санах ойн буферт багтаах боломжийг олгодог алдаанууд бөгөөд ингэснээр энэхүү буфер нь халих болно. Ингэж тооцоололгүй буруу бичсэний үр дүнд ажиллуулсан програмын бусад функцуудын санах ойг дарж бичдэг бөгөөд энэ нь аюулгүй байдлын эмзэг байдлыг үүсгэдэг гэж хэлж болно.

<p align="center">
<img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/stack/buffer.jpg">
</p>

Ийм програм ихэнхдээ хоёртын файл ( binary file ) нь өгөгдөл хадгалах орчинд хадгалагддаг шууд ажиллуулах боломжтой файл юм. Хоёртын файлуудын хувьд хэд хэдэн өөр формат байдаг. Жишээлбэл, PE формат (PE) нь Microsoft платформ дээр ашиглагддаг гэх мэт.

Гүйцэтгэх файлуудын өөр нэгэн бидний мэддэг формат бол бараг бүх орчин үеийн UNIX хувилбаруудаар дэмжигддэг  (ELF - Executable and Linking Format) формат юм. Хэрэв ELF формат нь хоёртын файлыг ачаалж , програмыг ажиллуулах юм бол харгалзах програмын кодыг үндсэн санах ойд ачаалж , дараа нь CPU гүйцэтгэнэ гэсэн үг л дээ.

Програмууд нь эхлүүлэх, гүйцэтгэх явцад өгөгдөл, instruction санах ойд хадгалдаг. Эдгээр нь ажиллуулсан програм хангамж дээр харагдана эсвэл хэрэглэгчийн оруулсан өгөгдөл гэсэн үг юм. Ялангуяа хэрэглэгчийн хүлээгдэж буй оролтын хувьд оролтыг хадгалах замаар урьдчилан буфер үүсгэх зарчимтай байдаг.

<p align="center">
<img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/stack/buffer2.png">
</p>

Stack дээр суурилсан Санах Ойн Халилтын халдлага нь тодорхой програм хангамжийн хувилбарыг тодорхойлсны дараа энэхүү үе халдлагыг хийх шатанд ирдэг. Энэхүү халдлагын зорилго нь олж авсан мэдээлэл болон түүн дээрх задлан шинжилгээнээс гарсан мэдээллийг ашиглан зорилтот системд нэвтрэх боломжит аргуудыг бүрэн олж авах юм.

Энэхүү халдлагыг хийх болон сайжруулж хөгжүүлэх нь маш төвөгтэй бөгөөд CPU-ийн үйл ажиллагаа , програм хангамжийн зорилгыг гүнзгий ойлгохыг тухайн хакераас шаарддаг. Олон халдлага нь өөр өөр програмчлалын хэл дээр бичигдэх боломжтой. Програмчлалын хамгийн түгээмэл ашигладаг хэлнүүдийн нэг бол Python бөгөөд ойлгоход хялбар , бичихэд хялбар байдаг , богино хугацаанд хөгжүүлэх боломжтой байдаг.

Халдлага нь 4 үе шаттай явагддаг:

> Local

> Remote

> DoS

> WebApp

### Local Exploits

Файлыг нээх үед локал эрхийн төвшнөөс шалтгаалаад нээж чадахгүй асуудал үүсдэг. Энэ үед локал санах ойн халдлагыг хийдэг. Энэхүү халдлагыг хийхийн тулд дотоод сүлжээнд байгаа файлууд эсвэл програм хангамжууд эмзэг байдалтай эсэхийг шалгах хэрэгтэй. Ихэнхдээ локал халдлага нь word , pdf файлыг импортолсон програмын аюулгүй байдлын цоорхойг ашиглаж , давуу эрхийн төвшинг дээшлүүлж , хортой кодыг ачааллаж , ажилладаг. Мөн бас үйлдлийн систем дээр бүрхүүл кодыг ( shellcode ) ажиллуулах боломжийг бүрдүүлдэг.

### Remote Exploits

Алсын зайнаас энэхүү халдлагыг хийхдээ санах ойн халилт ( buffer overflow ) аргыг ашигладаг. Энэхүү төрөл нь локал биш алсын зайнаас хаанаас ч хийгдэх боломжтой учраас эрсдэл маш өндөр байдаг.

### DoS Exploits

DoS буюу Denial Of Service төрөл нь програм хангамжийг зогсоох , эвдлэх зорилготой байдаг. Ер нь бол нэрээсээ л үйлчилгээг бусниулах гэсэн утгатайг харж болно ххэ

### WebApp Exploits

Веб аппликейшнруу довтлох төрөл нь вебсайт , системийн эмзэг байдлыг ашиглан өгөгдлийн санруу тушаалыг гүйцэтгэх боломжийг олгодог.

```c
#include <stdlib.h>
#include <stdio.h>
#include <string.h>

int bowfunc(char *string) {

	char buffer[1024];
	strcpy(buffer, string);
	return 1;
}

int main(int argc, char *argv[]) {

	bowfunc(argv[1]);
	printf("Done.\n");
	return 1;
}
```
