### 1. typeof可以判断哪些类型

1. 虽有值类型
2. 函数，所有函数都输出function
3. 对象，所有对象输出Object

### 2. ==和===区别，何时使用

==要求值相同，存在类型隐式转换，===要求不仅值相同，而且类型相同。

> 大部分都是使用===，==仅仅用在判断null和undefined

### 3. 如何判断一个对象是否是空对象

```
Object.keys(obj).length===0;
```

### 4.如何判断一个数据是数组

**1.数组 instanceof Array**

```
let arr = [];
console.log(arr instanceof Array);//true
```

**2.Array.isArray(数组)**

```
let arr = [];
console.log(Array.isArray(arr));//true
```

### 5.如何判断一个对象类型

### 6. 闭包的应用场景

1. 函数作为返回值
2. 函数作为参数传递
3. 开发中可以用于数据隐藏，只提供修改数据的接口，无法直接修改数据

**闭包缺陷**

变量不能及时释放，消耗内存

### 7. http状态码

1开头 ：服务器收到请求

2开头：200成功	

3开头：重定向

```
301:永久重定向，域名更换了，输入旧的域名，浏览器默认以后不再访问旧的，直接访问新的域名
302:临时重定向，只是临时的去访问新的地址，后面继续请求还是会访问当前的地址
304:有缓存，资源未修改，服务端告诉客户端当前有缓存，可以直接使用，我不会处理你。
```

4开头：前端错误

5开头：后端错误

### 8. http header

**request header**

```
Accept:浏览器可以接受的数据格式
Accept-Encoding:压缩算法
Connection:	keep-alive 一次tcp连接多次使用，不间断	
cookie：携带
User-Agent:浏览器标识信息，识别不同浏览器
```

**response header**

```
content-type:返回的数据的格式
set-cookie:服务端设置cookie返回
Expriex:设置过期时间
Catch-control:缓存机制
```

### 9. 缓存（重难点）

**强缓存**

> 强缓存是服务端决定哪类资源可以缓存到客户端本地（通常是图片，js等静态资源）服务端在responsed heder设置Catch-control:max-age操控强缓存的过期时间。

```
Catch-control:max-age:21211  强制缓存时间
Catch-control:max-age:no-catch 不设置强缓存
```



![](E:\董泽平\Desktop\demo\company\js\1.jpg)

**协商缓存**

> 协商缓存也是服务端决定，是服务端缓存（不是将资源缓存到服务端的意思）。是客户端向服务端请求资源时，服务端判断本次请求的资源和上次是否相同，如果相同，不发送资源发送状态码304。否则发送资源，状态吗200。

1. 通过Last-Modified：资源最后修改时间

![](E:\董泽平\Desktop\demo\company\js\2.jpg)

假设服务端采取了协商缓存机制，客户端第一次请求资源，服务端成功发送资源并携带last-modified。当客户端第二次访问服务端时会携带last-modify，服务端会判断这个last-modif和自己最新的last-modif是否相等，如果相等表示服务端资源未更新，直接给客户端发304。否则表示服务端资源已经更新，重新发送新资源，返回状态码200.

2. 通过Etag：资源唯一标识

   ![](E:\董泽平\Desktop\demo\company\js\3.jpg)

   

假设服务端采取了协商缓存机制，客户端第一次请求资源，服务端成功发送资源并携带Etag。当客户端第二次访问服务端时会携带Etag，服务端会判断这个Etag和自己最新的Etag是否相等，如果相等表示服务端资源未更新，直接给客户端发304。否则表示服务端资源已经更新，重新发送新资源，返回状态码200

**整个缓存流程**

牢记，先判断是否强缓存，再判断是否弱缓存。

![](E:\董泽平\Desktop\demo\company\js\4.jpg)

**三种刷新方式**

1.直接访问url,前进，后退   (强缓存+弱缓存都存在)

2.F5 （强缓存失效，弱缓存存在）

3.Ctrl+F5 (强缓存和弱缓存都失效)

### 10.输入url,页面加载过程

1. DNS解析，域名-->ip地址转换
2. ip地址向服务器发http请求
3. 服务器处理http请求，返回浏览器结果
4. 根据html生成Dom树
5. 根据css生成cssom
6. 将html Dom树和cssom整合加载

window.onload：等待页面资源全部加载才成功，包括图片和视频

DomContentLoaded：Dom渲染完就成功，不等图片和视频	

### 11.css为什么放头部

css放在头部目的是和html的dom树直接整合渲染，如果放在底部，会造成二次渲染，并且用户体验不好。

### 12.js为什么放底部

**js渲染过程**

js的渲染是阻塞式的，如果页面遇到js会停止页面渲染，等待js运行结束才继续渲染。因此js放在底部

### 13.如何性能优化

1. 防抖和节流
2. 图片懒加载
3. 代码压缩
4. 图片优化-雪碧图（所有图片放一张）
5. 浏览器缓存

### 14.Web安全

1. xss攻击

   页面文本输入框嵌入js脚本，获取用户关键信息cookie等

   可以通过字符替换预防

2. xsrf攻击

​	 攻击者盗用了你的身份，以你的名义发送恶意请求

​	使用post验收加强防御	 	

### 
