## Json

Json（javaScript Object Notation）是一种轻量级的数据交换格式，易于人的阅读，同时也易于机器的解析和生成。

JSON采用完全独立于语言的文本格式，很多语言对Json提供了支持（包括C、C++、Java等）

轻量级是和xml进行比较的

数据交换格式：客户端和服务器之间业务数据的传输格式

Json是由键值对组成，由大括号包围，每个键用引号引起来，键和值之间使用冒号分隔，多组键值对之间使用逗号进行分隔

JSON分两种形式：

- 一种是以对象的形式存在，称为JSON对象【一般操作JSON的数据时使用】
- 另一种是以字符串形式存在，称为JSON字符串【一般客户端和服务器进行数据交互时使用】

### Javascript中定义JSON

```json
// Json的定义
var jsonObj = {
  "key1": 123, // 数值
  "key2": "key2_value", // 字符串
  "key3": true, // 布尔值
  "key4": [123, "value", false], // 数组
  "key5": { // json类型
    "key5_1": 123,
    "key5_2": "key5_value"
  },
  "key6": [ // 数组里面包多个json类型
    {
      "id": 1,
      "name": "张三"
    },
    {
      "id": 2,
      "name": "李四"
    }
  ]
}
```

在Javascript中JSON就是一个对象

### Javascript中访问JSON

由于JSON本身就是一个对象，所以在javascript中访问JSON和javascript访问对象一样，**JSON对象.属性**

```javascript
alert(jsonObj.key1); // 123
alert(jsonObj.key2); // key2_value
alert(jsonObj.key3); // true
for (let i = 0; i < jsonObj.key4.length; i++) {
  alert("key4 第" + (i + 1) + "值为：" + jsonObj.key4[i]); // [123, "value", false]
}
alert(jsonObj.key5.key5_1); // 123
for (let i = 0; i < jsonObj.key6.length; i++) {
  alert("key6 第" + (i + 1) + "个JSON，id为：" + jsonObj.key6[i].id + ", name为：" + jsonObj.key6[i].name);
}
```

### Javascript中JSON常用方法

JSON常用方法

- JSON.stringify()：将JSON对象转换为JSON字符串
- JSON.parse()：将JSON字符串转换为JSON对象

```javascript
// 将JSON对象转换为JSON字符串
var jsonString = JSON.stringify(jsonObj);
alert(jsonString);
// 将JSON字符串转换为JSON对象
var jsonObject = JSON.parse(jsonString);
alert(jsonObject);
```

