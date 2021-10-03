---
published: true
---
### Challenge Type: Forensics
### Challenge Name: Very Secure LDAP

> LDAP , Wireshark , hash , gpp decryption tool

<p align="center">
Бидэнд verys3cure_ldap.pcapng файл өгөгдсөн  
</p>

<p align="center">
<a href="https://imgbb.com/"><img src="https://i.ibb.co/wN03Fqy/ldap1.png" alt="ldap1" border="0"></a><br /><a target='_blank' href='https://imgbb.com/'></a><br />
</p>

<p align="center">
Packet analyser `Wireshark` програмыг ашиглаж дамжсан хүсэлтүүдийг нь харахад сэжигтэй зүйл ажиглагдаагүй бөгөөд 
</p>

<p align="center">
<a href="https://ibb.co/4J6Dgfn"><img src="https://i.ibb.co/ZNnw1Jp/ldap2.png" alt="ldap2" border="0"></a><br /><a target='_blank' href='https://imgbb.com/'></a><br />
</p>

<p align="center">
Бодлогын нэр маань LDAP бөгөөд үүнийг хараад HTTP биш SMB -тэй холбоотой гэдгийг ойлгоод Object -г Export хийхээр шийдсэн. File --> Export Objects --> SMB
</p>

<p align="center">
<a href="https://ibb.co/ByPLn1c"><img src="https://i.ibb.co/6HZYXdr/ldap3.png" alt="ldap3" border="0"></a><br /><a target='_blank' href='https://imgbb.com/'></a><br />
</p>

<p align="center">
Export хийхэд дотор нь 4 файл байсан бөгөөд файлуудаа Directory дотор хадгалаад нэг бүрчлэн шалгаж эхэлсэн.
</p>

<p align="center">
<a href="https://imgbb.com/"><img src="https://i.ibb.co/qpG7KJm/ldap4.png" alt="ldap4" border="0"></a><br /><a target='_blank' href='https://imgbb.com/'></a><br />
</p>

<p align="center">
Хамгийн сүүлийн файлыг шалгах үед ...
</p>

<p align="center">
<a href="https://ibb.co/VLS7NVY"><img src="https://i.ibb.co/Rg0xS2T/ldap5.png" alt="ldap5" border="0"></a><br /><a target='_blank' href='https://imgbb.com/'></a><br />
</p>

<p align="center">
Дотор нь нэгэн төрлийн Hash гэж хэлж болохоор cpassword="4y3N3Q0dRFiq+mSGos3BZ2ylwQiyEsoyM8cH+4PUXTnIvVMSier7Lp5t3M4CXu7F" байсан.
</p>

<p align="center">
<a href="https://ibb.co/xHHkh3b"><img src="https://i.ibb.co/C22cBWy/ldap6.png" alt="ldap6" border="0"></a><br /><a target='_blank' href='https://imgbb.com/'></a><br />
</p>

<p align="center">
Тухайн үедээ LDAP -н талаар судалж байгаад Group Policy Preferences password decryption tool -г хайж Kali-Linux дээр байдаг gpp-decrypt tool-г ашигласан бөгөөд дараа нь судлаад үзэхэд online decryption вэбсайт байдаг юм байна лээ ххэ xD
</p>

<p align="center">
<a href="https://ibb.co/FY9H6V6"><img src="https://i.ibb.co/M1bBn6n/ldap7.png" alt="ldap7" border="0"></a><br /><a target='_blank' href='https://imgbb.com/'></a><br />
</p>


<p align="center">
<a href="https://ibb.co/wS7QcjW"><img src="https://i.ibb.co/gSdW4hT/ldap8.png" alt="ldap8" border="0"></a><br /><a target='_blank' href='https://imgbb.com/'></a><br />
</p>

<p align="center">
----------- HZ19{I_am_so_s3cur3} -------------------
</p>
