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

      var arr = ["a","b"];

1. 方法
    + arr.push("c");   arr.push("c","d");  向数追加新元素值1个或多个，返回新的数组个数 a b c / a b c d
    + arr.pop(); 删除数组最后一个元素，返回删除的元素 b
    + arr.unshift("A"); 数组开头追加新元素，返回追加后的数组长度 A a b = 3 
    + arr.shift(); 删除数组第一个元素，返回删除的元素 a
    + arr.forEach() 循环数组，详情请看上边 《 js 循环 》
    + arr.slice(0,1); 提取指定元素 从索引0开始，到索引1结束
    + arr.splice(0, 1, "c"); 删除元素并添加新元素，返回删除的元素 a ，arr 变成 c b
    + arr.concat(["c","d"]); 连接两个或多个数组，不会对arr产生影响，返回新的数组 a b c d
    + arr.join(","); 将数组转换成字符串并以括号里的字符串连接符进行连接 返回字符串 a,b
    + arr.reverse(); 数组内值进行翻转 b a
    + arr.sort(); 按照 unicode 编码排序

            排序
            var newArray = [2, 3, 1, 6, 7, 5, 4];
            newArray.sort(function(a, b){
                return a - b;// 升序 1 2 3 4 5 6 7
                return b - a;// 降序 7 6 5 4 3 2 1
            });
2. 例子

        去除重复数据
        var newArray = [1, 2, 1, 3, 4, 5, 4, 3];
        for( var i=0; i<newArray.length; i++){
            for(var j=i+1; j<newArray.length; j++){
                if(newArray[i] == newArray[j]){
                    newArray.splice(j, 1);
                }
            }
        }
        
        去除重复数据，并且有相邻的重复数据
        var newArray = [1, 2, 1, 1, 3, 4, 5, 4, 4, 3];
        for( var i=0; i<newArray.length; i++){
            for(var j=i+1; j<newArray.length; j++){
                if(newArray[i] == newArray[j]){
                    newArray.splice(j, 1);
                    j--;
                }
            }
        }
        
> js call、apply 调用函数的方法

###### call() 方法可以将实参在对象后依次传递
###### apply() 方法需要将实参封装到一个数组中传递

> js arguments 是一个类数组对象，也可以通过索引获取数组数据和长度

> js Date 对象 
        
        var date = new Date("08/01/2019 23:23:23");
        
> js Math

1. Math.abs();  计算一个数的绝对值
2. Math.ceil(); 对一个小数向上取整，小数位有值就进1
3. Math.floor(); 对一个小数向下取整，舍弃小数点以后的值
4. Math.round(); 四舍五入
5. Math.random(); 生成随机数
       
           Math.round(Math.random() * 10) 生成 0-10直接的随机数
           
> js 字符串方法

      var str = "abcdefg";

1. str.charAt(2);  查找指定位置的字符串并返回  c
2. str.concat("h","i"); 连接一个或多个字符串 abcdefghi
3. str.indexOf("g");  检索一个字符串是否存在指定内容（<font color="red">从前往后找</font>），找到返回索引，找不到-1
4. str.lastIndexOf("g"); 检索一个字符串是否存在指定内容（<font color="red">从后往前找</font>），找到返回索引，找不到-1
5. str.slice(0, 2); 截取字符串指定内容   返回 ab
6. str.substring(0, 2); 截取字符串指定内容   返回 ab
7. str.split(","); 将一个字符串拆分成数组
8. str.toUpperCase(); 将一个字符串转换成大写并返回  ABCDEFG
9. str.toLowerCase(); 将一个字符串转换成小写并返回

> js 正则

1. /正则表达式/i &nbsp;&nbsp; /正则表达式/g  &nbsp;&nbsp; /正则表达式/ig &nbsp;&nbsp; 表达式末尾 &nbsp;&nbsp;<font color="red">i</font>忽略大小写，<font color="red">g</font>全局匹配模式
2. 正则表达式.test(需要正则的内容);  用test来检测正则表达式是否符合规则
3. srt.split(正则表达式); 可以写正则拆分字符串，注：不用设置全局匹配模式g

         var str = "abcdefgG";
         str.split(/e/); // 返回 ["abcd", "fgG"]
             
3. srt.search(正则表达式); 搜索字符串是否存在， 注：不用设置全局匹配模式，设置了也不起作用

        var str = "abcdefgG";
        str.search(/b/); // 找到返回字符串b的起始位置 1，找不到返回 -1
              
3. srt.match(正则表达式); 查找匹配的字符串， 可以设置全局匹配

        var str = "abcdefgG";
        str.match(/abc/); // 返回 ["abc", index: 0, input: "abcdefgG", groups: undefined]
        
3. srt.replace(正则表达式查找需要替换的内容, 替换的内容); 替换指定字符串的内容

        var str = "abcdefgG";
        str.replace(/abc/, "123"); // 返回  123defgG
        
4. 量词

    + {n} 出现的次数，只对花括号前边的内容起作用
    
               var str = "abcdefgG";
               var reg = /a{1}/; // true
               var reg = /a{2}/; // false
               console.log(reg.test(str));
               
    + {m-n} 出现 m-n 次
    
            var str = "abbbc";
            var reg = /ab{1,2}c/; // true
            var reg = /ab{4,8}c/; // false
            console.log(reg.test(str));
            
    + {m,} 出现m次以上
        
            var str = "abbbc";
            var reg = /ab{2,}c/; // true
            var reg = /ab{9,}c/; // false
            console.log(reg.test(str));
            
    + {ab+c} 至少一个，相当于{1,}
    
            var str = "abbbbc";
            var reg = /ab+c/; // true
            var reg = /ab+cd/; // false
            console.log(reg.test(str));
    + {ab*c} 0个或多个，相当于{0,}

            var str = "abbbbcabbbbc";
            var reg = /ab*c/; // true
            var reg = /ab+cd/; // false
            console.log(reg.test(str));
    + {ab?c} 0个或1个，相当于{0,1}
    
            var str = "abc";
            var reg = /ab?c/; // true
            
            var str = "abbc";
            var reg = /ab?c/; // false
            console.log(reg.test(str));
    + /^a/ 必须是xxx开头 
    
            var str = "abc";
            var reg = /^a/; // true
            
            var str = "bbc";
            var reg = /^a/; // false
            console.log(reg.test(str));
    + /a$/ 必须是xxx结尾
    
            var str = "bca";
            var reg = /^a/; // true
            
            var str = "fbbcb";
            var reg = /^a/; // false
            console.log(reg.test(str));
    + /./ 任意字符
    
8. 元字符

    + /w/ /W/  小写w匹配字母、数字、_ ， 大写W匹配除了字母、数字、_
    + /d/ /D/  小写d匹配任意数字[0-9] ， 大写D匹配除了任意数字[0-9]
    + /s/ /S/  小写匹配空格， 大写S匹配除了空格
    + /b/ /B/  小写b匹配单词边界， 大写B匹配除了单词边界
    + /^\s*|\s*$/g 匹配开头和结尾的空格
    
9.  简单的手机号验证和qq邮箱验证练习

            var phone = "13599999999";
            var reg = /^1[3-9][0-9]{9}$/;
            console.log(reg.test(phone));
            
            var email = "123333@qq.com";
            var regEmail = /^[0-9]{5,10}@[a-z]{2}\.([a-z]{3})$/;
            console.log(regEmail.test(email));

> js DOM

1. onload 事件会在页面加载完成后执行
2. document.getElementById();  查找id
3. document.getElementByTagName(); 根据标签名获取一组元素的节点对象
4. document.getElementByName(); 根据name获取标签，返回数组
5. document.querySelector(); 可以根据css选择器，查询一个元素的节点对象 
6. 属性介绍
    + childNodes 获取所有子节点
    + firstChild 获取当前节点的第一个子节点
    + lastChild 获取当前节点的最后一个子节点
    + parentNodes 获取当前节点的父节点
    + previousSibling 获取当前节点的前一个兄弟元素
    + nextSibling 获取当前节点的后一个兄弟元素
    + appendChild 向一个父节点中添加一个子节点
    + removeChild 删除子节点
    + replaceChild 替换子节点
   
> js 事件冒泡

###### 就是事件的向上传导，当后代元素的事件触发时，其祖先元素相同事件也会触发
1. addEventListener("click", 回调函数, false)为元素绑定响应函数
2. location.href 跳转
3. history.go 返回上一级

> js 定时器

1. setInterval() 定时调用，可以将一个函数每隔一段时间执行一次，返回number

        setInterval(function(){
            console.log(1);
        }, 1000);
        
2. clearInterval() 关闭一个定时器
3. setTimeout()  延时调用一个函数，不马上执行，隔一段时间在执行，只会执行一次
4. clearTimeout() 关闭一个延时调用

> js json

1. json.parse() 将json字符串转换为js对象
2. json.stringify() 将js对象转json字符串