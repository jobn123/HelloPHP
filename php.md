# php 基础

### 基本语法
```php
<!DOCTYPE html>
<html>
    <head>
     <meta http-equiv="Content-Type" content="text/html; charset=utf-8">
        <title>欢迎学习php!</title>
    </head>
	<body>
       <p>
       <?php
        echo 'php学到家';
       ?>
     </p>

	</body>
</html>
```
### 输出语句 echo

```php
<?php echo "Hello world!";?>
```

### 字符串
可以使用单引号，或双引号
```php
<?php echo "Hi, john";?>
```
链接两个字符串用 `.`

```php
<?php echo 'Hi,'.'nihao!';?>
```

### PHP代码行结尾处都会有一个分号；

### 注释
用双斜杠（//）来表示

### 变量

```php
$var = '222';
echo $var;
```
`var_dump`函数可以获取我们的变量的数据类型

```php
<?php
$var_name = "苹果";
$n =10;
var_dump($var_name); //string(6) "苹果"
var_dump($n); //int(10)
?>
```

`memory_get_usage`获取当前PHP消耗的内存。

```php
<?php
echo $m1 = memory_get_usage();

echo "<br />";

$var_string = "123";

echo $m2 = memory_get_usage()-$m1;

?>
```

### php 变量的数据类型

在PHP中，支持8种原始类型，其中包括四种标量类型、两种复合类型和两种特殊类型
布尔、整形、浮点、字符串,资源，空类型NULL、常量

#### 空类型NULL
NULL类型只有一个取值，表示一个变量没有值，当被赋值为NULL，或者尚未被赋值，或者被unset()，这三种情况下变量被认为为NULL。

```php
<?php
 error_reporting(0); //禁止显示PHP警告提示
 $var;
 var_dump($var);
 $varr1=null;
 var_dump($var1);
 $var2 = NULL;
 var_dump( $var2);
 $var3 = "节日快乐！";
 unset($var3);
 var_dump($var3);
?>
```

#### 常量
*语法格式*

```php
bool define(string $constant_name, mixed $value[, $case_sensitive = true])
```

第一个参数“constant_name”为必选参数，常量名称,即标志符，常量的命名规则与变量的一致，但是要注意哦，它可不带美元符号哦。第二个参数“value”为必选参数，它是常量的值。第三个参数“case_sensitive”为可选参数，指定是否大小写敏感，设定为true表示不敏感，一般不指定第三个参数的情况下，默认第三个参数的值为false。

#### 字符串
```php
<?php
$love = "I love you!";
$string1 = "xxx,$love";
$string2 = 'xxx,$love';
echo $string1; //xxx,I love you!
echo "<br />";
echo $string2; //xxx,$love
?>
```

`当双引号中包含变量时，变量会与双引号中的内容连接在一起；当单引号中包含变量时，变量会被当做字符串输出。`
