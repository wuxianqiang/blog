# exercises
练习题

清除浮动的方法
1. 给浮动元素的祖先元素设置：`height: `
2. 给浮动元素的祖先元素设置：`overflow: hidden;`
3. 给浮动元素的祖先元素设置：`overflow: auto;`
4. 给需要清除浮动的元素设置：`clear: both;`
5. 在浮动元素和需要清除浮动的元素之间添加一个元素并且设置：`clear: both;`
6. 给浮动元素的祖先元素的伪类设置：`display: block;content: "";clear: both;`

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
