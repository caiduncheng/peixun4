# JavaScript 基础



## 任务目的

通过使用原生JS完成以下练习，掌握`JavaScript`基础知识

## 参考资料

-  [MDN](https://developer.mozilla.org/en-US/ )

-  [W3C](https://www.w3cschool.cn/javascript/ )

## 开始

## 1.JavaScript语言基础

### 1.1 任务

- 写一个能按照要求的格式输出当前时间的函数，格式：

  今天是：星期三

  当前时间：22:39:50

  ```javascript
  function fn() {
      //...
  }
  ```

  

- 写一个函数，要求能替换URL中的参数，如果参数不存在，则在URL后面添加

  ```javascript
  function updateURLParameter(url, param, val) {
      //...
  }
  
  updateURLParameter('www.baidu.com', 'lang', 'en_US') //www.baidu.com?lang=en_US
  updateURLParameter('www.baidu.com?lang=en_US', 'lang', 'zh_CN') 
  //www.baidu.com?lang=zh_CN
  updateURLParameter('www.baidu.com?lang=en_US', 'type', 'a') 
  //www.baidu.com?lang=en_US&type=a
  ```

  

- 实现各种判断数据类型的方法，返回布尔值。

  ```javascript
  // 不能用Array.isArray()
  function isArray(arr) {
      //...
  }
  
  function isFunction(fn) {
      //...
  }
  ```

- 掌握值类型和引用类型的区别，了解对象的遍历方式。在`util.js`实现方法：

  使用**递归**实现深度克隆，复制一个目标对象，返回一个完整拷贝

  ```javascript
  function cloneObject(src) {
      //...
  }
  
  var obj = {
      a: 1,
      b: {
          b1: ['javascript', 'java'],
          b2: 'hello world'
      }
  };
  var obj2 = obj;
  var clonedObj = cloneObject(obj);
  
  obj.a = 2;
  obj.b.b1[0] = 'js';
  
  console.log(obj2.a); // 2
  console.log(obj2.b.b1[0]); // js
  
  console.log(clonedObj.a); // 1
  console.log(clonedObj.b.b1[0]) // "javascript"
  ```

- 学习数组、字符串、数字等方法

  对数组进行去重操作，数组中的元素为数字或字符串，返回一个去重后的数组。

  ```javascript
  function uniqArray(arr) {
      //...
  }
  
  var a = [1, 3, 5, 7, 5, 3];
  var b = uniqArray(a);
  console.log(b); // [1, 3, 5, 7]
  ```

  自己实现一个trim方法，去除字符串头尾的空格，返回去除后的字符串，可以试着用正则表达式完成题目。

  ```javascript
  function trim (str) {
      // ...
  }
  
  var str = '    js     ';
  str = str.trim(str);
  console.log(str); // 'js'
  ```

  自己实现遍历数组的方法，针对数组中每一个元素执行函数，并将数组索引和元素作为参数传递（类似map）

  ```javascript
  function each () {
      //...
  }
  // 示例一
  var arr = ['a', 'b', 'c', 'd'];
  function output (item) {
      console.log(item)
  }
  each(arr, output) // a,b,c,d
  
  //示例二
  var arr = ['a', 'b', 'c', 'd'];
  function output (item, index) {
      console.log(index + ':' + item)
  }
  each(arr, output); // 0:a, 1:b, 2:c, 3:d
  
  ```

  获取一个对象里面第一层元素的数量，返回一个整数
  
  ```javascript
  function getObjectLength(obj) {
      // 你的代码
  }
  
  var obj = {
  	a: 1,
      b: 2,
      c: {
          c1: 3,
          c2: 4
      }
  };
  
  console.log(getObjectLength(obj));
  ```
  
  写出一个能从对象数组中返回某个指定对象的索引值的函数
  
  ```javascript
  function findIndex(src, target) {
      // 你的代码
  }
  
  var arr = [
      {
          id: 123,
          name: 'a'
      },
      {
          id: 456,
          name: 'b'
      }
  ]
  
  console.log(findIndex(arr, {id: 123, 'a'})) // 0
  ```

- 学习正则表达式

  判断某个字符串是否是邮箱地址

  ```javascript
  function isEmail(emailStr) {
      // 你的代码...
  }
  
  function isMobilePhone(phone) {
      //你的代码...
  }
  ```

## 3. DOM

### 3.1 任务

- 为元素增加一个样式名为className的样式。

  ```javascript
  function addClass(element, className) {
      //你的代码...
  }
  ```

- 移除元素中的样式className。

  ```javascript
  function removeClass(element, className) {
      //你的代码
  }
  ```

- 判断某个元素是否为同一个父元素下的同一级的元素，返回布尔值。

  ```javascript
  function isSiblingNode(element, siblingNode) {
      //你的代码
  }
  ```

- 获取元素相对于浏览器窗口的位置，返回一个对象{x, y}

  ```javascript
  function getPosition (element) {
      //你的代码
  }
  ```

- 不使用document.querySelector的情况下，实现一个简单的jQuery的$()

  ```javascript
  function $(selector) {
      //...
  }
  
  $('#test') //返回id为test的DOM对象
  $('a') //返回第一个<a>对象
  $('.container') //返回第一个样式名为container的对象
  $('[type]') //返回第一个包含属性type的对象
  $('[type=text]') //返回第一个包含属性type，值为text的对象
  ```

## 4. Ajax

- 封装一个自己的Ajax方法。

  ```javascript
  function ajax(url, options) {
      //...
  }
  
  ajax('http://www.baidu.com/server/ajax',
      {    
          data: {
              name: 'johnson',
              password: '123456'
          },
          onsuccess: function(response) {
              console.log(response)
          }
      }
  );
  ```

  