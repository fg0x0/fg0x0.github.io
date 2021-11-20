---
published: true
---
## PHP Hacking Techniques

<p align="center">
🐱‍💻 Зочилсон хүний тоо 🐱‍💻 
</p>
<p align="center">
  <img src="https://profile-counter.glitch.me/{2021-10-03-PHP-Hacking-Techniques}/count.svg">
</p>

##### PHP Weak Type

```php
var_dump('0xABCdef' == ' 0xABCdef');
```

> true

```php
var_dump('0010e2' == '1e3’);
```

> true

```php
strcmp([],[])
```
> 0

```php
sha1([])
```

> NULL

```php
'123' == 123
```

```php
'abc' == 0
```

```php
'123a' == 123
```

```php
'0x01' == 1
```

> var_dump('0x01' == 1) => false

```php
'' == 0 == false == NULL
```

```php
var_dump(md5(240610708));
```

> 0e462097431906509019562988736854

```php
var_dump(sha1(10932435112));
```

> 0e07766915004133176347055865026311692244

```php
$a="123"; $b="456"
```

> $a + $b == "579";
> $a . $b == "123456"

```php
$a = 0; $b = 'x';
```

> $a == false => true
> $a == $b => true
> $b == true => true

```php
$a = 'a'
```

> ++$a => 'b'
> $a+1 => 1
