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

// 有参数 无返回值得参数。
function sayname($name){
    echo $name."你好";
};
//调用
sayname("小狐狸");

//有参数，参数有默认值的函数。
function sayFood($food='西蓝花'){
    encho $food.'好好吃';
}
sayFood();//不传参数的话，使用默认的参数。
sayFood('potato');//传入了参数，就使用参数值;
//有参数有返回值得参数
function sum($a,$b){
    return $a+$b;
}
//调用
sum(1+2);
````
6. php 允许使用对象这种自定义的数据类型，使用时必须先声明，实例化之后才能使用；
````
//定义最基础的类
class Fox{
    public $name = 'terry';
    public $age = 12; 
}
$fox = new Fox();//实例化对象
$name = $fox->name;//读取对象的属性值
$fox->name = 'terry';
//对象属性赋值

//带构造函数的对象：
class person{
    //私有属性，外部无法访问
    var $name = 'terry';
    //定义方法来获取属性
    function name(){
        return $this->name;
    }
    //构造函数,可以传入参数
    function setName($name){
        $this->name  =$name;
    }
}
//定义了构造函数,需要使用构造函数初始化对象;
$person  = new persion('小刚');
//调用对象方法，获取对象名
$personName = $person->name();
````
6. 内容输出
- echo();
- print_r();输出字符串。输出复杂数据类型，比如数组，对象；
- var_dump();输出详细信息,比如对象，数组；
````
$arr = array(1,1.2,'hello');
echo'123'; 
// 结果为 123

print_r($arr);
// 结果为 Array ( [0] => 1 [1] => 2 [2] => 123 )

var_dump($arr);
/* 结果为 
    array
  0 => int 1
  1 => int 2
  2 => string '123' (length=3)
*/
````
7. 循环语句，这里只列举foreach,和for循环；
````
//for循环
for ($i=0;$i<10;$i++){
    echo '数字是：'.$i."<br/>";
}
//foreach循环
$colors = array('red','green','black');
foreach($colors as $value){
    echo "$value <br>"
}
````
8. header()函数；
- 用来向客户端(浏览器)发送报头，如果出现中文而无法显示，可以尝试在php代码的顶部添加如下代码；
````
//设置文件的编码格式；
header("content-type:text/html;charset=utf-8");
//设置页面跳转
header('location:网址');
//设置页面间隔刷新:
header('refresh:3;url=http://www.baidu.com');
````
9. php表单;
- PHP_GET数据获取
1. 在PHP中如果要获得通过get方法提交的数据，可以通过，$_GET对象来获取，(虽然参数在地址栏中可以查看);
````
//http 代码,将表单提交到01.php,使用get的方式提交；
<form action="01.php" method="get">
 <label for=''>姓名:
 <input type="text" name="userName"></label><br>
 <label for="" >邮箱：<input type="text" name="userEmail"></label><br/>
 <input type="submit" name="">
 </form>
 ````
 - php 代码
 ````
 <?php
 echo "<h1>GET_PAGE</h1>";
 echo 'userName:'.$_GET['userName']; 
 echo '<br/>';
 echo 'userEmail:'.$_GET['userEmail'];
 ?>


