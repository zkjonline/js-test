# js-test
JS 练习

> js数据类型 共6种 其中基本类型(5)和引用数据类型(1)

1.  基本数据类型
	+ String 字符串
	+ Number 数值 包括整数(1,2,3...)和浮点数(小数)
	+ Boolean 布尔值
	+ Null 空值
	+ Undefined 未定义

2.  引用数据类型
    + Object 对象
    
###### 可以用 typeof 检查变量的数据类型 typeof null 返回object ，typeof undefined 返回 undefined

> js类型转换

+ 转换为[string]类型  a、str.toString(); b、String(123); 
+ 转换为[number]类型  Number("123"); paseInt("123px") == 123; paseFloat("12.34px") == 12.34
   <font color=red>注</font> Number("")、Number(true/false)、Number(null) 都返回0
   <font color=red>注</font> paseInt只取整数部分 ， paseFloat只取有效的小数 这两个方法都是先string再转换
+ 转换为[boolean]类型  Boolean(0/123/"123"); 数字转布尔 0/NaN返回false其余都是true，字符串转布尔 除了空字符串都是true， null和undefined 转布尔都是false 

> js运算

1.  当对非number类型进行运算时，会将值转为number再进行运算
2.  任何值和NaN运算，都是NaN

>js 自增/自减

1. a++ a--
   + a++ 等于原变量自增前的值(旧值) 
   + a-- 等于原变量自减前的值(新值) 
2. ++a --a
   + ++a 等于原变量自增后的值(旧值) 
   + --a 等于原变量自减后的值(新值) 
<br>     
      
        例：
            var n1=10, n2=20;
            
            var n = n1++;// n1 = 11 n1++ = 10
            
            console.log('n=' + n);//10
            console.log('n1=' + n1);//11
            
            n = ++n1; // n1 =12 ++n = 12
            
            console.log('n=' + n);//12
            console.log('n1=' + n1);//12
            
            n = n2--; // n2 = 19 n2-- = 20
            
            console.log('n=' + n);//20
            console.log('n2=' + n2);//19
            
            n = --n2; // n2 = 18 --n2 = 18
            
            console.log('n=' + n);//18
            console.log('n2=' + n1);//18           


> js逻辑运算 && / | |

1. && 与运算

  + 如果第一个值为true，则必然返回第一个值
  + 如果第一个值为false，则直接返回第一个值
  + 如果两个值都为true，返回后面的值
  
2. | | 或运算

  + 如果第一个值为true，则直接返回第一个值
  + 如果第一个值为false，则返回第二个值

> js条件运算  ? &nbsp;&nbsp; :
  
###### var a = 1; var b = 3; &nbsp;&nbsp;&nbsp;  a > b ? true : false;
  
> js弹出框 alert 、prompt

###### alert() 弹出一个窗口
###### prompt() 弹出一个窗口，并且窗口可以输入文本，有确定和取消按钮

> 条件分支语句，也叫switch语句

        var a = 1;
        switch (a){
            case 1:
                console.log("to do something");
                break;
            case 2:
                console.log("to do something");
                break;
            case 3:
                console.log("to do something");
                break;
            default:
                console.log("default something");
                break;
        } 
        
> js 循环 while、do{} while()、for、forEach

    例：
        *
        **
        ***
        ****
        *****
    for(var i=0; i<5; i++){
        for (var j=0; j<i+1; j++){
            document.write("*");
        }
        document.write("<br />")
    }
    
    例：
        *****
        ****
        ***
        **
        *
    for(var i=0; i<5; i++){
        for (var j=0; j<5-i; j++){
            document.write("*");
        }
        document.write("<br />")
    }
    
    例：
        9*9 乘法表
    for(var i=1; i<=9; i++){
        for (var p=1; p<=i; p++){
            document.write(p + "*" + i + "=" + i*p + "&nbsp;&nbsp;&nbsp;");
        }
        document.write("<br />");
    }
    
    知识点：
    for(var i=1; i<10; i++){
        break; // 终止当前程序
        continue; // 跳过当次循环，继续下一次循环
    }
    
    var arr = ["a", "b", "c"];
    arr.forEach(function(value, index, obj){
        console.log(value); // 数组的值 a b c
        console.log(index); // 数组的索引 0 1 2
        console.log(obj); // 数组本身
    });
    
    var obj = {
        name:"a",
        age: 18,
        city:"北京",
    };
    for (var n in obj){
        console.log(n);// name age city
        console.log(obj[n]); // a 18 北京
    }

> js对象 复合型数据类型

###### in 检查对象是否存在某个属性  "acb" in obj; 返回 true/false 
###### in 如果对象中没有但是原型对象中有，会返回 true
 
> js 变量和对象存储的空间

1. 变量都是保存到<font color="red">栈内存</font>中，<font color="red">基本数据</font>类型的值也是存在<font color="red">栈内存</font>中，值和值独立存在，修改一个变量不会影响到其他
2. 对象保存在<font color="red">堆内存</font>中，每创建一个new Object() 就会开辟出一个新的空间，如果两个变量调用同一个引用，修改一个另一个也会跟着变

> js 立刻执行函数

      (function fun(){
          console.log("123")
      })();
      
> js作用域 全局作用域、函数作用域

1. 全局作用域
  + 写在script标签中的js代码都在全局作用域中，页面打开创建，页面关闭销毁，在全局作用域中有一个全局对象window
  + 函数声明会提前创建
  + 函数表达式不会被提前创建
2. 函数作用域
  + 调用函数时创建函数作用域，函数执行完毕后作用域销毁
  + 每一次调用函数就会创建一个新的函数作用域，它们直接是互相独立的
  + 在函数作用域中可以访问到全局作用域的变量，但是在全局作用域中无法访问函数作用域的变量
  + 在函数作用域中操作一个变量时，它会先在自身作用域中找 有使用 没有则向上一级找，直到找到全局作用域，如果全局作用域中没有报错
  + <font color="red">变量和函数都会提升，函数的优先级高</font>
  
> js this

1. 以函数形式调用，this永远都是window
2. 以方法形式调用，this就是调用方法
3. 以构造函数调用，this就是新创建的对象
4. 以 call apply 调用，this就是指定的那个对象

> js 工厂方法 通过调用方法可以大批量的创建对象，不用每次都单独 new Object

         function factoryFun(a, b, c){
             var obj = {
                 a:a,
                 b:b,
                 c:c
             };
             return obj;
         }
 
         var factory1 = factoryFun(1,2,3);
         var factory2 = factoryFun(4,5,6);
         
> js 构造函数 

1. new 调用的函数就是构造函数，首字母大写 new Person() new GetName() ........ , 不是大写开头的就是普通函数
2. 用 instanceof 检查一个对象是否是一个类的实例 返回 true / false， 用法： xxxx instanceof Person

> js 原型对象 

1. prototype  MyClass.prototype.name = "原型对象中的name"; 
2. 通过 hasOwnProperty() 来检查自身中是否有该属性，返回 true / false

> js 垃圾回收

1. 针对无用的变量和对象，js拥有自动那个回收机制
2. 一般把变量和对象定义为null，浏览器会自动回收垃圾

        var obj = new Object();
        obj = null;
     
> js数组