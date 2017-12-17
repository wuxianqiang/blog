# exercises
练习题

清除浮动的方法
1. 给浮动元素的祖先元素设置：`height: `
2. 给浮动元素的祖先元素设置：`overflow: hidden;`
3. 给浮动元素的祖先元素设置：`overflow: auto;`
4. 给需要清除浮动的元素设置：`clear: both;`
5. 在浮动元素和需要清除浮动的元素之间添加一个元素并且设置：`clear: both;`
6. 给浮动元素的祖先元素的伪类设置：`display: block;content: "";clear: both;`

数组toString()的原理是数组的每一项都会调用toString()
```js
var ary = [[[1,2]],[[3,4]]];
console.log(ary.toString()) //"1,2,3,4"
```
对象存储值的过程
```js
var obj = {
    name: "Qiang",
    fn: (function () {
        return obj.name
    })()
}
console.log(obj.fn);// 报错，对象是先存储值，然后再把内存地址赋值给obj
```
构造函数创建函数的参数
```js
var str = "[1,2,3,4,5]";
var res = new Function("return" + str)();
console.log(res) //[1,2,3,4,5]
```
函数的length属性
```js
function fn(x,y=2,z){}
console.log(fn.length); //1
```
对象存储值的过程
```js
var obj = {
    name: "Qiang",
    fn: (function () {
        return obj.name;
    })()
}
console.log(obj.fn); //报错
```
块级作用域中变量名不能和函数名同名
```js
console.log(AA); //undefined
{
    var AA = 10;
    function AA() {}
}
console.log(AA) //报错
```

关键字定义的区别

|关键字|是否会给window增加属性|是否可以重复声明|是否声明时候必须赋值|是否赋值之后可以修改|是否只在自己的块级作用域里有效|
|-|-|-|-|-|-|
|var|是:white_check_mark:|是:white_check_mark:|否|是:white_check_mark:|否|
|let|否|否|否|是:white_check_mark:|是:white_check_mark:|
|const|否|否|是:white_check_mark:|否|是:white_check_mark:|

变量提升提升情况

|情况|var是否会声明|var是否会定义|function是否会声明|function是否会定义|
|-|-|-|-|-|
|全局作用域|是:white_check_mark:|否|是:white_check_mark:|是:white_check_mark:|
|if判断/for循环（不管条件是否成立）|是:white_check_mark:|否|是:white_check_mark:|否|
|return返回值|否|否|否|否|
|返回值之后的内容|是:white_check_mark:|否|是:white_check_mark:|是:white_check_mark:|

爱奇艺面试题
```js
var m= 1, j = k = 0; 
function add(n) { 
    return n = n+1; 
} 
y = add(m); 
function add(n) { 
    return n = n + 3; 
} 
z = add(m); 
console.log(y + "," + z);
```
答案：4，4
```js
var n=2.toString();
console.log(typeof(n));
```
答案：报错

正则对分组的处理和贪婪性处理
```js
var reg = /(\w)+/g;
console.log(reg.exec("wuxianqiang"))
//[ 'wuxianqiang', 'g', index: 0, input: 'wuxianqiang' ]
var reg = /(\w+)/g;
console.log(reg.exec("wuxianqiang"))
//[ 'wuxianqiang', 'wuxianqiang', index: 0, input: 'wuxianqiang' ]
```
```js
var reg = /(\w+)(\d+)/g;
console.log(reg.exec("hello2018"))
//[ 'hello2018', 'hello201', '8', index: 0, input: 'hello2018' ]
var reg = /(\w+?)(\d+)/g;
console.log(reg.exec("hello2018"))
//[ 'hello2018', 'hello', '2018', index: 0, input: 'hello2018' ]
```
函数参数的默认值会影响函数的length属性，如果指定了默认值，则默认值前面的才属于length
```js
function fn(a,b=1,c) {
    console.log(fn.length); //1
}
fn()
```
多个call的问题
```js
function fn1() {
    console.log(1,this);
}
function fn2() {
    console.log(2,this);
}
let obj = {}
fn1.call.call.call(fn2,obj) //=>fn2.call(obj)
```
