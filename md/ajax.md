## 服务器软件
1. 文件服务器：Server-u、FileZilla、VsFTP等；
2. 数据库服务器：Oracal、MySQL、PostgreSQL、MSSQL等；
3. 邮件服务器：Postfix、SendMail等；
4. http服务器：Apache、Nginx、IIS、Tomcat、nodeJS;
## 服务端开发的语言有，3p( php jsp asp ),ruby python  Erlang等；
### 数据库软件有 Oracle MySQL MSSQL
这些软件的特点：
- 数据共享：多用户访问数据库的稳定性；
- 故障恢复：数据库软件提供了一套方法，可以用来发现错误，并且修复错误。
- 减少数据冗余：由于大家都可以使用同一套数据库，没必要创建重复的数据；
## amp Apache MySQL PHP (Hypertext  preprocessor)
# 简单的php
1.  PHP 代码的执行方式：服务端web编程，写好的代码，需要通过浏览器来访问服务器，在服务器端执行，然后返回用户结果，如果直接以浏览器打开，会解析成文本；
## PHP常见语法：
1. PHP书写的文件已.php结尾，注释的写法与js一致.
```` 
<?php code //单行注释 /* 多行注释*/  ?>;
````
2. PHP 变量规则：
- 变量以$开头，其后是变量的名称，
- 变量必须是以字母或者下划线开头。
- 变量名称不能以数字开头。
- 变量们称只能是\w*
- 变量名称对大小写敏感；
````
$a;
$b;
$A;
// $a和$A是两个不同的变量；
````
3. 数据类型
- PHP数据类型包括，字符串，整数，浮点数，布尔，数组，对象，NULL；
````
$str = '123';//定义字符串123并初始化赋值，注意：''之内只是作为字符串，""双引号内部如果是变量，会将该变量解析；   字符串是用.来进行连接；
$str = '123'.'balaa';//连接字符串；
$num = 1;//定义一个整数变量；
$num2 = 2.3;//定义一个浮点数；
$res = true;
$res = false;//定义bool值；
$arr = array('123',123);//数组
````
4. 运算符：PHP中，运算符跟javaScript中的基本一致，用法也基本一致。
````
<?php 
$a = 10;
$b = 23;
echo($a +$b);
echo($a-$b);
echo($a*$b);
echo($a/$b);
echo($a%$b);
?>
````
5. 函数：php虽然系统键了一些函数，但是这是不影响我们定义自己的，函数的作用就是可以在代码总重复运行的代码块，页面加载的时候不会执行，只有被调用的时候才会被执行；
````
function functionName(){
    //code...
}//基础语法；

//无参数 无返回值的函数
function sayHi(){
    echo hello world;
}
//调用
sayHi();





