---
published: true
---
<p align="center">
🐱‍💻 Зочилсон хүний тоо 🐱‍💻 
</p>
<p align="center">
  <img src="https://profile-counter.glitch.me/{2021-10-09-DNS-Enumeration}/count.svg">
</p>

## DNS гэж юу вэ?

DNS нь хостын нэр болон IP хаяг хоорондын орчуулагч юм.

Энгийнээр хэлбэл Домэйн Нэрийн Систем (DNS) нь хост нэрийг IP хаяг руу хөрвүүлдэг өгөгдлийн баазуудын цуглуулга юм.

DNS нь ихэвчлэн интернетийн утасны ном гэж нэрлэдэг бөгөөд энэ нь www.google.com-тэй адил хялбархан нэрлэх хост нэрийг хөрвүүлдэг учраас 216.58.217.46 шиг IP хаяг руу хөрвүүлдэг . Вэб браузерын хаягийн талбарт URL- ыг оруулсны дараа энэ үйл явдлуудын цаана явагддаг.

DNS (ялангуяа Google гэх мэт хайлтын систем), бидний зочлох вэбсайт бүрийн IP хаягийг оруулснаар интернетэд залгах нь амаргүй байх болно.

DNS ажил яаж ажилладаг вэ?
Хэрвээ энэ нь тодорхойгүй байгаа бол DNS хэрхэн ажилладагийг үндсэн ойлголтод тун энгийн юм: вэб хөтөч дээр байрлуулсан вэбсайт болгон (Chrome, Safari, эсвэл Firefox гэх мэт) бүр DNS сервер рүү илгээдэг. энэ нэр зохих IP хаяг руу

Энэ нь өөр хоорондоо харилцахын тулд ашигладаг IP хаяг бөгөөд тэд www.google.com , www.youtube.com гэх мэт нэрээр мэдээлэл дамжуулж чадахгүй тул бид хялбархан нэр өгдөг. Эдгээр вэбсайтууд бол DNS нь бидний хайж буй хуудсыг нээхэд шаардагдах IP хаягууд руу ойрхон хандах боломжийг бидэнд олгодог.

Дахин хэлэхэд www.microsoft.com, www. , www.amazon.com болон бусад бүх вэбсайтын нэрийг зөвхөн бидний тав тухтай байдалд зориулж ашигладаг тул тэдгээрийн IP хаягийг санахаас илүүтэйгээр эдгээр нэрсийг санах нь илүү хялбар байдаг.

Компьютерийн root сервер гэж нэрлэгддэг компьютерүүд нь дээд түвшний домайн бүрт IP хаягуудыг хадгалах үүрэгтэй. Вэбсайтыг хүссэн тохиолдолд хайлт хийх дараагийн алхамыг тодорхойлохын тулд эхлээд мэдээллийг боловсруулдаг root сервер байна. Дараа нь, домэйн нэр нь ISP- д байрлах Домэйн Нэрийн Шүүгч (DNR) -д зөв IP хаягийг тодорхойлох болно. Эцэст нь, энэ мэдээллийг таны хүссэн төхөөрөмж рүү буцаах болно.

- [DNS Enumeration](#dns-enumeration)
  - [DNS Records](#dns-records)
  - [Tools](#tools)
    - [dnsenum](#dnsenum)
    - [nslookup](#nslookup)
    - [dig](#dig)
    - [host](#host)
  - [DNS Zone Transfer](#dns-zone-transfer)
    - [Find Name Server](#find-name-server)  
    - [Find Name Server IP Address](#find-name-server-ip-address)
    - [Transfer Target Zone](#transfer-target-zone)
  - [Subdomain Enumeration Tool](#subdomain-enumerate-tool)
    - [massdns](#massdns)
    - [subfinder](#subfinder)
    
<br>
### Impact

An attacker can use this information to obtain the internal network information if the DNS server is vulnerable to Zone Transfer Attack.
<br>
### DNS Records

| Record | Description |
|--------|-------------|
| A | The record that holds the IP address of a domain. |
| CNAME | Forwards one domain or subdomain to another domain, does NOT provide an IP address |
| MX | Directs mail to an email server |
| TXT | Lets an admin store text notes in the record. |
| NS | Stores the name server for a DNS entry |
| SOA | Stores admin information about a domain |
| SRV | Specifies a port for specific services. |
| PTR | Provides a domain name in reverse-lookups |
<br>
## Tools

### dnsenum
It is a multithread script to enumerate information on a domain and to discover non-contiguous IP blocks, Mainly it is ued to enumerate information about subdomins via custom dns server. 

	--noreverse           Skip the reverse lookup operations.
	-p, --pages <value>   The number of google search pages to process when scraping names,
    -s, --scrap <value>   The maximum number of subdomains that will be scraped from Google (default 15)
    --dnsserver   <server>

	# dnsenum --noreverse example.com

	# dnsenum --noreverse -o out.xml example.com

	# dnsenum --dnsserver <DNS_Server_Address> <Domain> -p <Pages> -s <Subdomain_Scrap>

	# dnsenum --dnsserver 192.168.1.100 example.tk -p 10 -s 50
<br>
### nslookup
nslookup  is  a  program  to query Internet domain name servers.  nslookup has two modes: interactive and non-interactive. Interactive mode allows the user to
query name servers for information about various hosts and domains or to print a list of hosts in a domain.  Non-interactive mode prints just the name and requested information for a host or domain.

	# nslookup <Server_IP/Domain> <DNS_Server_Address>

	# nslookup 192.168.1.100 192.168.1.1

	# nslookup --type=PTR 192.168.1.100 192.168.1.1

	# nslookup --type=A example.tk 192.168.1.1

	# nslookup -type=NS example.tk 192.168.1.1

	# nslookup -type=MX example.tk 192.168.1.1
<br>
### dig
It performs DNS lookups and displays the answers that are returned from  the  name  server(s)  that were  queried

	# dig <domain> @<DNS_Server_Address>

	# dig example.tk @192.168.1.100

	# dig A example.tk @192.168.1.100

	# dig AAAA example.tk @192.168.1.100

	# dig CNAME example.tk @192.168.1.100

	# dig NS example.tk @192.168.1.100
<br>
### host
It is normally used to convert names to IP addresses and vice versa.

	-t specifies the query type

	# host -t A <Domain> <DNS_Server_Address>

	# host -t A example.tk 192.168.1.32

	# host -t NS example.tk 192.168.1.32

	# host -t AAAA example.tk 192.168.1.32

	# host -t CNAME example.tk 192.168.1.32

	# host -t PTR 192.168.1.32 192.168.1.32
<br>
### DNS Zone Transfer

Zone Transfer can be applicable on Both Forward and Reverse Zone, if zone transfer is allow to all ip. It can be done in three steps.

### Find Name Server

	# nslookup -type=ns example.tk 192.168.1.100

	# dig NS example.tk @192.168.1.100

	# host -t ns example.tk 192.168.1.100

	# dig NS zonetransfer.me

### Find Name Server IP Address

	# nslookup -type=A server.example.tk 192.168.1.100

	# dig A server.example.tk @192.168.1.100

	# host -t A server.example.tk 192.168.1.100

	# dig A nsztm2.digi.ninja

### Transfer Target Zone

	# nslookup -type=axfr example.tk 192.168.1.100

	# dig AXFR example.tk @192.168.1.100

	# host -t AXFR example.tk 192.168.1.100

	# dig AXFR zonetransfer.me @nsztm2.digi.ninja

## Subdomain Enumerate Tool

## massdns
MassDNS is a simple high-performance DNS stub resolver targeting those who seek to resolve a massive amount of domain names in the order of millions or even billions. Without special configuration, MassDNS is capable of resolving over 350,000 names per second using publicly available resolvers.

	https://github.com/blechschmidt/massdns

	# git clone https://github.com/blechschmidt/massdns
	
	# cd massdns/

	# make

	# cp bin/massdns /usr/bin/

	# massdns -h
	-r  --resolvers        Text file containing DNS resolvers.
	-t  --type             Record type to be resolved. (Default: A)
	-w  --outfile          Write to the specified output file instead of standard output.
	-o  --output           Flags for output formatting.

	# massdns -r lists/resolvers.txt -t AAAA /dev/shm/domain.txt

	# massdns -r lists/resolvers.txt -t NS /dev/shm/domain.txt > /dev/shm/NS.txt

	# massdns -r lists/resolvers.txt -t SOA /dev/shm/domain.txt -w /dev/shm/SOA.txt

	# massdns -r lists/resolvers.txt -t PTR /dev/shm/domain.txt -w /dev/shm/PTR.txt

	# massdns -r lists/resolvers.txt -t CNAME /dev/shm/domain.txt -w /dev/shm/CNAME.txt
	
	# massdns -r lists/resolvers.txt /dev/shm/domain.txt -t A -o S -w /dev/shm/results.txt

### subfinder
Subfinder is a subdomain discovery tool that discovers valid subdomains for websites by using passive online sources. It has a simple modular architecture and is optimized for speed. subfinder is built for doing one thing only - passive subdomain enumeration, and it does that very well.

	https://github.com/projectdiscovery/subfinder

	# GO111MODULE=on go get -v github.com/projectdiscovery/subfinder/v2/cmd/subfinder

	# cp /root/go/bin/subfinder /usr/bin/subfinder

	# subfinder --help
	-d string        Domain to find subdomains for
	-dL string       File containing list of domains to enumerate
	-nW        Remove Wildcard & Dead Subdomains from output
	-rL string        Text file containing list of resolvers to use
	-silent        Show only subdomains in output
	-o string        File to write output to (optional)
	
	# subfinder -d example.com

	# subfinder -d example.com -v
	
	# subfinder -d example.com -all -v

	# subfinder -d example.com -recursive

	# subfinder -dL /dev/shm/domain.txt

	# subfinder -d example.com -nW

	# subfinder -d example.com -nW -rL /opt/Tools/massdns/lists/resolvers.txt

	# subfinder -d example.com -silent

	# subfinder -d example.com -nW -silent -o /dev/shm/result.txt
