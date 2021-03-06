# HelloPHP

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

获取常量值的有两种方法取值。第一种是使用常量名直接获取值。第二种是使用constant()函数。它和直接使用常量名输出的效果是一样的，但函数可以动态的输出不同的常量，在使用上要灵活、方便，其语法格式如下：

```php
mixed constant(string constant_name)
```
**判断常量是否被定义**

```
bool defined(string constants_name)
```

#### 系统常量
 * __FILE__ :php程序文件名。它可以帮助我们获取当前文件在服务器的物理位置
 * __LINE__ :PHP程序文件行数。它可以告诉我们，当前代码在第几行。
 * PHP_VERSION:当前解析器的版本号。它可以告诉我们当前PHP解析器的版本号，我们可以提前知道我们的PHP代码是否可被该PHP解析器解析
 * PHP_OS：执行当前PHP版本的操作系统名称。它可以告诉我们服务器所用的操作系统名称，我们可以根据该操作系统优化我们的代码。

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

#### 赋值运算符
PHP的赋值运算符有两种

  * “=”：把右边表达式的值赋给左边的运算数。它将右边表达式值复制一份，交给左边的运算数。换而言之，首先给左边的运算数申请了一块内存，然后把复制的值放到这个内存中
  * “&”：引用赋值，意味着两个变量都指向同一个数据。它将使两个变量共享一块内存，如果这个内存存储的数据变了，那么两个变量的值都会发生变化。

  ```php
  $b = $a;  
  $c = &$a;
  ```

#### 逻辑运算符
```php
$a and $b  逻辑与  如果$a与$b都为TRUE，返回TRUE；

$a or $b   逻辑或  如果$a或$b任一为TRUE，返回TRUE；

$a xor $b  逻辑异或  如果$a与$b有且仅有一个为TRUE，返回TRUE；

!$a        逻辑非  如果$a不为TRUE，返回TRUE；

$a&&$b     逻辑与  如果$a与$b都为TRUE，返回TRUE；

$a||$b     逻辑或  如果$a与$b任一为TRUE，返回TRUE。
```

#### 连接运算符
（1）连接运算符(“.”)：它返回将右参数附加到左参数后面所得的字符串。

（2）连接赋值运算符(“.=”)：它将右边参数附加到左边的参数后。


#### 错误控制运算符

PHP中提供了一个错误控制运算符“@”，对于一些可能会在运行过程中出错的表达式时，我们不希望出错的时候给客户显示错误信息，这样对用户不友好。于是，可以将@放置在一个PHP表达式之前，该表达式可能产生的任何错误信息都被忽略掉；


```php
$conn = @mysql_connect("localhost","username","password");
 echo "出错了，错误原因是：".$php_errormsg;
```

#### foreach循环
foreach循环语句，常用于遍历数组，一般有两种使用方式:不取下标、取下标。

（1）只取值，不取下标

```php
<?php
 foreach (数组 as 值){
//执行的任务
}
?>
```

2）同时取下标和值

```php
<?php
foreach (数组 as 下标 => 值){
 //执行的任务
}
?>
```
