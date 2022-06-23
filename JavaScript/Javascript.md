## JavaScript

控制浏览器弹出一个警告框：

```javascript
alert("Hello World")
```

在计算机页面中输出一个内容

```javascript
document.write("Hello World")
```

在控制台中输出一个内容

```javascript
console.log("Hello World");
```

### JavaScript和html结合方式

#### 方式一：使用script标签来书写代码

```html
<script>
    // html中编写的js
</script>
```

#### 方式二：使用script标签引入js代码文件

```html
<script src="helloworld.js"></script>
```

### 数据类型

六种数据类型：String（字符串）、Number（数值）、Boolean（布尔）、Null（空值）、Undefined（未定义）、Object（对象）

**可以使用typeof来获取变量的类型**

#### 强制类型转化

- 将一个数据类型强制转换为其他数据类型

- 类型转换主要指：String、Number、Boolean

- 转换为String类型
  
  - 方式一：调用数据类型的toString()方法
    
    不会影响到原变量
    
    注意：null 和 undefined没有toString()方法
    
    ```javascript
    var a = 123;
    var b = a.toString()
    ```
  
  - 方式二：调用String()函数，将转换的数据作为参数传递给函数
    
    可以转换null和undefined类型
    
    ```javascript
    var a = 123;
    var b = String(a);
    ```

- 转换为Number类型
  
  - 方式一：使用Number()函数
    
    如果是纯数字的字符串 ==> 数字
    
    如果有非数字的字符串 ==> NaN
    
    如果是空串或者全是空格的字符串 ==> 0
    
    布尔值 true ==> 1，false ==> 0
    
    空值 null ==> 0
    
    undefined ==> NaN
    
    ```javascript
    var a = "123";
    var b = Number(a);
    ```
  
  - 方式二：使用parseInt()、parseFloat()转换为整数和浮点数
    
    ```javascript
    var a = "123px";
    var b = parseInt(a);
    ```

- 转换为Boolean类型，使用Boolean()函数
  
  数值除了0和NaN的情况，其余都是true
  
  字符串除了空串，其余都是true
  
  null和undefined都会转换为false
  
  对喜爱那个会转换成true
  
  ```javascript
  var a = 123;
  var b = Boolean(a);
  ```

### 变量

- 定义变量的格式
  
  ```javascript
  var 变量名;
  var 变量名 = 值;
  ```

### 运算符

#### 算数运算符

对于非Number类型的值进行运算时，会将这些值转换为Number后再运算

任何值和NaN进行运算都会得到NaN

| 运算符 | 描述                                                                                |
| --- | --------------------------------------------------------------------------------- |
| +   | 可以对两个值进行加法运算，并将结果返回<br/>如果两个字符串进行加法运算，则会进行字符串拼接操作<br/>字符串和任何值进行加法运算，会先转换为字符串，再做运算 |
| -   | 可以对两个值进行减法运算，并将结果返回                                                               |
| *   | 可以对两个值进行乘法运算，并将结果返回                                                               |
| /   | 可以对两个值进行除法运算，并将结果返回                                                               |
| %   | 可以对两个值进行取模运算，并将结果返回                                                               |

#### 一元运算符

只需要一个操作数

对于非Number类型的值，会先转换为Number，然后在进行运算

可以对一个其他的数据类型使用 + ，来将其转换为Number类型

| 运算符 | 描述             |
| --- | -------------- |
| +   | 正号，不会对数字产生任何影响 |
| -   | 负号，负号可以对数字进行取反 |

#### 自增和自减

- 自增：可以在变量自身的基础上增加1

- 自减：可以在变量自身的基础上减少1

| 运算符 | 描述      |
| --- | ------- |
| i++ | 先赋值，后加1 |
| i-- | 先赋值，后减1 |
| ++i | 先加1，后赋值 |
| --i | 先减1，后赋值 |

#### 逻辑运算符

| 运算符   | 描述                                                                               |
| ----- | -------------------------------------------------------------------------------- |
| !（非）  | 可以用来对一个值进行非运算<br/>即true ==> false，false ==> true<br/>如果对非布尔值进行运算，则会先转换为布尔值，在进行取反 |
| &&（与） | 可以对符号两侧的值进行与运算，并返回结果<br/>两侧全true则为true，否则为false                                  |
|       | \|（或）                                                                            |

#### 赋值运算符

| 运算符 | 描述                      |
| --- | ----------------------- |
| =   | 可以将符号右侧的值赋值给符号左侧的变量     |
| +=  | 例如：a += 5 等价于 a = a + 5 |
| -=  | 例如：a -= 5 等价于 a = a - 5 |
| *=  | 例如：a *= 5 等价于 a = a * 5 |
| /=  | 例如：a /= 5 等价于 a = a / 5 |
| %=  | 例如：a %= 5 等价于 a = a % 5 |

#### 关系运算符

通过关系运算符可以比较两个值之间的大小关系

关系成立则返回true，关系不成立则返回false

对于非数值进行比较时，会将其转换为数字然后在比较

任何值和NaN进行比较都会返回false

如果符号两侧都是字符串，则会比较字符串中字符的Unicode编码

| 运算符 | 描述                                             |
| --- | ---------------------------------------------- |
| >   | 判断符号左侧的值是否大于右侧的值<br/>成立则返回true，不成立则返回false     |
| <   | 判断符号右侧的值是否大于左侧的值<br/>成立则返回true，不成立则返回false     |
| >=  | 判断符号左侧的值是否大于或者等于右侧的值<br/>成立则返回true，不成立则返回false |
| <=  | 判断符号右侧的值是否大于或者等于左侧的值<br/>成立则返回true，不成立则返回false |

#### 相等运算符

用来比较两个值是否相等，如果相等则返回true，不相等则返回false

NaN不会和任何值进行相等，包括自己本身

如果要对NaN进行判断，需要使用isNaN()函数进行判断是否是NaN

| 运算符 | 描述                                                      |
| --- | ------------------------------------------------------- |
| ==  | 相等运算，并返回运算结果<br/>如果值的类型不同，则会自动进行类型转换为相同类型，则进行比较         |
| !=  | 用来判断两个值是否不相等，如果不相等则返回true，否则返回false                     |
| === | 用来判断两个值是否全等，和相等类似，但是全等不做自动类型转换<br/>如果两个值的类型不同，直接返回false |
| !== | 用来判断两个值是否不全等，和不等类似，但是不做自动类型转换<br/>如果两个值的类型不同，直接返回true   |

#### 条件运算符（三元运算符）

语法：

```javascript
条件表达式 ? 语句1 : 语句
```

执行时，首先对条件表达式进行求值

- 如果该值为true，则执行语句1，并返回执行结果

- 如果该值为false，则执行语句2，并返回执行结果

### 代码块

可以使用 {} 来为语句进行分组

同一组 {} 中的语句，要么都执行，要么都不执行

```javascript
{
    // 执行的逻辑代码
}
```

### 流程控制语句

可以控制程序执行流程，使程序可以根据一定条件来选择执行

#### if语句

- 语法一：
  
  在执行时，会先对条件表达式进行求值判断，如果条件表达式的值为true，则执行if后的语句，如果为false，则不会执行if后的语句
  
  ```javascript
  if(条件表达式){
      语句
  }
  ```

- 语法二
  
  当该语句执行时，会先对条件表达式进行求值判断，如果该值为true，则执行if后的语句，如果该值为false，则执行else后的语句
  
  ```javascript
  if(条件){
      语句...
  }else{
      语句...
  }
  ```

- 语法三
  
  当该语句执行时，会从上到下依次对条件表达式进行求值判断，如果值为true，则执行当前语句，如果值为false，则继续向下判断，如果所有条件都不满足，则执行最后一个else后的语句
  
  ```javascript
  if(条件表达式){
      语句...
  }else if(条件表达式){
      语句...
  }else if(条件表达式){
      语句...
  }else{
      语句...
  }
  ```

#### switch语句

- 在执行时会依次将case后的表达式的值和switch后的条件表达式的值进行全等比较
  
  - 如果比较结果为true，则从当前case处开始执行代码
  
  - 如果比较结果为false，则继续向下比较
  
  - 使用break可以用来退出switch语句

- 语法：
  
  ```javascript
  switch(条件){
      case 表达式:
          语句...
          break;
      case 表达式:
          语句...
          break;
      default:
          语句...
          break;
  }
  ```

#### 循环语句

通过循环语句可以反复的执行一段代码多次

##### for循环

- 第一步：执行时，先初始化表达式，初始化变量【只会执行一次】

- 第二步：执行条件表达式，判断是否执行循环
  
  - 如果为true，则执行循环
  
  - 如果为false，终止循环

- 第三步：执行更新表达式，更新表达式执行完毕继续重复第二步

```javascript
for(初始表达式;条件表达式;更新表达式){
    语句...
}
```

##### while循环

- 执行时，先对条件表达式进行求值判断，如果值为true，则执行循环体
  
  - 循环体执行完毕后，继续对表达式进行判断
  
  - 如果为true，则继续执行循环体，以此类推
  
  - 如果为false，则终止循环

- 可以使用break，来终止循环

```javascript
while(提交表达式){
    语句...
}
```

##### do...while循环

- 执行时，先执行循环体，循环体执行完毕后，对while后的条件表达式进行判断
  
  - 如果结果为true，则继续执行循环体，执行完毕继续判断以此类推
  
  - 如果结果为false，则终止循环

```javascript
do{
    语句
}while(条件)
```

### break和continue

- break关键字可以用来退出switch或者循环语句

- continue关键字可以用来跳过当次循环

### 函数

- 函数也是一个对象

- 函数可以封装一些功能（代码），在需要时可以执行这些功能

- 函数中可以保存一个代码在需要的时候调用
  
  ```javascript
  var fun = new Function("console.log("这是一个")");
  ```

- 调用函数
  
  语法：函数对象()
  
  当调用函数时，函数中封装的代码会按照顺序执行
  
  ```javascript
  fun();
  ```

- 使用函数声明来创建一个函数
  
  语法：function 函数名([形参1,形参2...形参N]){语句}
  
  ```javascript
  function fun(){
      console.log("这是一段函数");
  }
  ```

- 使用函数表达式创建一个函数
  
  语法：var 函数名 = function([形参1,形参2...形参N]){语句...}
  
  ```javascript
  var fun = function(){
      console.log("这是一个匿名函数")
  }
  ```

### 对象（Object）

- 对象属于一种复合的数据类型，在对象中可以保存多个不同数据类型的属性

- 对象分为内建对象、宿主对象和自定义对象
  
  - 内建对象：由ES标准中定义的对象，在任何的ES的实现中都可以使用
    
    比如：Math、String、Number、Boolean、Function、Object
  
  - 宿主对象：由JS的运行环境提供的对象，主要指由浏览器提供的对象
    
    比如：BOM、DOM
  
  - 自定义对象：由自己创建的对象

- 创建对象
  
  使用new关键字调用的函数，是构造函数constructor
  
  构造函数是专门用来创建对象的函数
  
  ```javascript
  var obj = new Object();
  ```

- 在对象中添加属性
  
  语法：对象.属性名 = 属性值;
  
  ```javascript
  obj.name = "张三";
  ```

- 读取对象中的属性
  
  语法：对象.属性名
  
  如果读取对象中没有的属性，不会报错，但是会返回undefined
  
  ```javascript
  console.log(obj.name);
  ```

- 修改对象中的属性值
  
  语法：对象.属性名 = 新值;
  
  ```javascript
  obj.name = "李四";
  ```

- 删除对象的属性
  
  语法：delete 对象.属性名
  
  ```javascript
  delete obj.name;
  ```

- 如果要使用特殊的属性名，不能采用 "." 的方式来操作
  
  语法：对象["属性名"] = 属性值
  
  读取也需要这种方式
  
  ```javascript
  obj["123"] = 789;
  console.log(obj["123"]);
  ```

- in运算符可以检查一个对象中是否含有指定的属性，如果有则返回true，没有则返回false
  
  语法："属性名" in 对象
  
  ```javascript
  console.log("name" in obj);
  ```

- 使用对象字面量来创建一个对象
  
  语法：{属性名:属性值,属性名:属性值...}
  
  属性名可以加引号也可以不加引号，但是使用特殊的名字，则必须加引号
  
  ```javascript
  var obj = {
      name: "张三",
      age: 18
  };
  ```

- 在对象中添加一个方法（即函数）
  
  语法：obj.属性名 = function(){};
  
  ```javascript
  obj.method = function(){
      console.log("这是一个方法");
  }
  ```

- 调用对象的方法
  
  语法：obj.属性名()
  
  ```javascript
  obj.method();
  ```

- for...in循环：对象中有几个属性，循环就会执行几次
  
  语法：for(var 变量 in 对象){}
  
  每执行一次，会将对象中的属性名赋值给变量
  
  ```javascript
  for(var n in obj){
      console.log("属性名：" + n);
      console.log("属性值：" + obj[n]);
  }
  ```

- 构造函数
  
  构造函数就是一个普通的函数，创建方式和普通函数没有区别
  
  不同的是构造函数习惯上首字母大写
  
  构造函数需要使用new关键字来调用
  
  ```javascript
          function Person(){
  
          }
          var person = new Person();
  ```

- 构造函数的执行流程
  
  - 立即创建一个新的对象
  
  - 将新建的对象设置为函数中的this
  
  - 逐行执行函数中的代码
  
  - 将新建的对象作为返回值返回

- 使用 instanceof关键字可以检查一个对象是否是一个类的实例
  
  语法：对象 instanceof 构造函数
  
  如果是，则返回true，否则返回false
  
  ```javascript
  per instanceof Person;
  ```

- 每创建一个函数，解析器都会向函数中添加一个属性prototype
  
  这个属性对应着一个原型对象
  
  如果函数作为普通函数调用prototype时，没有任何作用
  
  当函数以构造函数的形式调用时，所创建的对象中都会有一个隐含属性，可以通过__proto__来访问该属性
  
  原型对象就相当于一个公共的区域，所有同一个类的实例都可以访问到这个原型对象，可以将对象中共有的内容，统一设置到原型对象中
  
  ```javascript
  MyClass.prototype.name = "张三";
  ```

- 当访问对象的一个属性或者方法时，会先在对象自身中寻找，如果有则直接使用，如果没有则会去原型对象中寻找，如果找到则直接使用

- 可以使用in检查对象中是否含有某个属性，如果对象中没有但是原型中有，会返回true
  
  ```javascript
  console.log("name" in obj);
  ```

- 可以使用对象的hasOwnProperty()来检查对象自身是否含有该属性，只有对象自身中含有属性时，才会返回true
  
  ```javascript
  console.log(obj.hasOwnProperty("name");
  ```

- toString()：当直接在页面上打印一个对象时，实际上是输出对象的toString()方法的返回值
  
  ```javascript
  console.log(person.toString();
  ```

- 可以为对象添加一个toString()方法，用于重写
  
  ```javascript
  person.toString = function(){
      return "Person[name=" + this.name + "]";
  };
  ```

### 基本数据类型和引用数据类型

- 基本数据类型
  
  String、Number、Boolean、Null、Undefined

- 引用数据类型
  
  Object

- JS的变量都是保存到栈内存中的，基本数据类型的值是直接在栈内存中存储，修改一个变量不会影响其他的变量

- 对象是保存到堆内存中的，每创建一个新的对象，就会在堆内存中开辟出一个新的空间，修改一个变量修改属性时，另外一个也会收到影响

### this

- 解析器在调用函数时每次都会向函数内部传递进一个隐含的参数，这个隐含的参数就是this

- this指向的是一个对象，这个对象称为函数执行的上下文对象

- 根据函数调用方式的不同，this会指向不同的对象
  
  - 以函数的形式调用时，this永远都是指向window
  
  - 以方法的形式调用时，this就是调用方法的那个对象

### 数组（Array）

- 数组也是一个对象

- 和普通对象功能类似，也是用来存储一些值的

- 不同的是普通对象是使用字符串作为属性名的，而数组是使用数字来作为索引操作元素

- 索引是从0开始的

- 数组中的元素可以时任意的数据类型

#### 创建数组

- 方式一：创建数组对象
  
  ```javascript
  var arr = new Array();
  var arr1 = new Array(1,2,3,4,5,6,7,8,9);
  
  
  ```

```

```

```

// 创建长度为10的数组
var arr2 = new Array(10);

```

- 方式二：使用字面量 [] 来创建数组

```javascript
var arr = [];
var arr1 = [1,2,3,4,5,6,7,8,9];
```

#### 添加数组元素

语法：数组[索引] = 值

```javascript
arr[0] = 10;
arr[1] = 20;
```

#### 读取数组元素

语法：数组[索引]

读取不存在的索引时，不会报错，而是返回undefined

```javascript
console.log(arr[]0);
```

#### 获取数组的长度

可以使用length属性来获取数组的长度

语法：数组.length

对于连续的数组，使用length可以获取到数组的长度

对于非连续的数组，使用length会获取到数组的最大索引 + 1

```javascript
console.log(arr.length);
```

修改length

- 如果修改的length大于原长度，多出来的部分为空出来

- 如果修改的length小于原长度，多出来的元素会被删除

```javascript
arr.length = 10;
```

#### 数组的方法

##### push()方法

- 向数组的末尾添加一个或多个元素，并返回新的长度
  
  ```javascript
  arr.push("新的值");
  ```

##### pop()方法

- 删除并返回数组的最后一个元素，并返回删除的元素
  
  ```javascript
  arr.pop();
  ```

##### unshift()方法

- 向数组的开头添加一个或者多个元素，并返回新的长度
  
  ```javascript
  arr.unshift("新的");
  ```

##### shift()方法

- 删除并返回数组的第一个元素，并返回删除的元素
  
  ```javascript
  arr.shift();
  ```

##### slice()方法

- 从某个已有的数组返回选定的元素
  
  参数一：截取开始位置的索引，包含开始索引
  
  参数二：截取结束位置的索引，不包含结束索引【可选，不写则截取后面所有】
  
  ```javascript
  arr.slice(1,4);
  ```

##### splice()方法

- 删除数组中指定的元素和插入新的元素，并将指定删除的元素从原数组中删除
  
  参数1：表示开始位置的索引
  
  参数2：表示删除的数量
  
  参数3及后面：插入新的元素，这些元素会在开始位置索引前插入
  
  ```javascript
  var result = arr.splice(0, 2);
  ```

##### concat()方法

- 连接两个或者更多的数组，并返回结果
  
  ```javascript
  var arr1 = [1, 2, 3];
  var arr2 = [4, 5, 6];
  var newArr = arr1.concat(arr2);
  ```

##### join()方法

- 该方法可以将数组转换为一个字符串，并将转换后的字符串返回
  
  可以指定一个字符串作为参数，这个参数将会称为数组中元素的连接符
  
  ```javascript
  var result = arr.join();
  var result2 = arr.join("|");
  ```

##### reverse()方法

- 颠倒数组中元素的顺序
  
  ```javascript
  arr.reverse();
  ```

##### sort()方法

- 对数组的元素进行排序
  
  ```javascript
  arr.sort();
  ```

#### 数组的遍历

```javascript
for(var i = 0; i < arr.length; i++){
    console.log(arr[i]);
}
```

使用forEach()方法，用于遍历数组

- 数组中有几个元素函数就会执行几次，每次执行时，浏览器会将遍历的元素以实参的形式传递进来，我们可以定义形参，来接收这些内容
  
  - 参数1：当前正在遍历的元素
  
  - 参数2：当前正在遍历的元素的索引
  
  - 参数3：正在遍历的数组

```javascript
arr.forEach(function(value, index, obj){
    console.log("value:" + value + ",index:" + index + ",obj:" + obj);
});
```

### Date时间对象

- Date对象表示一个时间

- 创建Date对象
  
  ```javascript
  // 直接创建Date对象
  var date = new Date();
  
  // 传递时间字符串的参数
  // 格式：月份/日/年 时:分:秒
  var date2 = new Date("12/12/2000 12:12:12");
  ```

#### 时间的方法

##### getDate()方法

- 获取当前日期对象是几日
  
  ```javascript
  date.getDate();
  ```

##### getDay()方法

- 获取当前日期对象是周几
  
  会返回一个0到6的值，0表示周日，1表示周一，以此类推
  
  ```javascript
  date.getDay();
  ```

##### getMonth()方法

- 获取当前日期对象的月份
  
  会返回0到11的值，0表示1月，1表示2月，以此类推
  
  ```javascript
  date.getMonth();
  ```

##### getFullYear()方法

- 获取当前日期对象的年份
  
  ```javascript
  date.getFullYear();
  ```

##### getTime()方法

- 获取当前日期对象的时间戳（毫秒）
  
  ```javascript
  date.getTime();
  ```

##### 获取当前时间戳

```javascript
Date.now();
```

### Math

- Math和其他的对象不同，它不是一个构造函数，它属于一个工具类

- 封装了数学运算相关的属性和方法

- Math.PI：表示圆周率

- abs()方法：可以用来计算一个数的绝对值
  
  ```javascript
  Math.abs(-1);
  ```

- ceil()方法：用来对数进行向上取整
  
  ```javascript
  Math.ceil(1.4);    // 2
  ```

- floor()方法：用来对数进行向下取整
  
  ```javascript
  Math.floor(1.2);    // 1
  ```

- round()方法：用来对数进行四舍五入
  
  ```javascript
  Math.round(1.4);    // 1
  Math.round(1.6);    // 2
  ```

- random()方法：可以用来生成一个0-1之间的随机数
  
  ```javascript
  Math.random();
  ```

- max()方法：可以获取多个数中的最大值
  
  ```javascript
  Math.max(10, 20, 30);
  ```

- min()方法：可以获取多个数中的最小值
  
  ```javascript
  Math.min(10, 20, 30);
  ```

- pow(x， y)方法：返回x的y次幂
  
  ```javascript
  Math.pow(10, 3);
  ```

- sqrt()方法：获取数的开方
  
  ```javascript
  Math.sqrt(9);
  ```

### 包装类

- Js中提供了三个包装类，通过这三个包装类可以将基本数据类型转换为对象
  
  - String()：可以将基本数据类型字符串转换为String对象
    
    ```javascript
    var str = new String("hello");
    ```
  
  - Number()：可以将基本数据类型的数字转换为Number对象
    
    ```javascript
    var num = new Number(123);
    ```
  
  - Boolean()：可以将基本数据类型的布尔值转换为Boolean对象
    
    ```javascript
    var bool = new Boolean(true);
    ```
