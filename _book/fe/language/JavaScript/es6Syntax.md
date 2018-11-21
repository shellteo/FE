# ES6/7/8语法

## 一些使用实用的语法
#### 1.Array.prototype.includes()
includes 函数与 indexOf 函数很相似，下面两个表达式是等价的：

```javascript
arr.includes(x)
arr.indexOf(x) >= 0
```

#### 2.Object.values()
Object.values()是一个与Object.keys()类似的新函数，但返回的是Object自身属性的所有值，不包括继承的值。

#### 3.Object.entries
Object.entries()函数返回一个给定对象自身可枚举属性的键值对的数组。

```javascript
for(let [key,value] of Object.entries(obj1)){
    console.log(`key: ${key} value:${value}`)
}
//key:a value:1
//key:b value:2
//key:c value:3
```

#### 4.String padding
在ES8中String新增了两个实例函数`String.prototype.padStart`和`String.prototype.padEnd`，允许将空字符串或其他字符串添加到原始字符串的开头或结尾。
填充字符串的用例包括：
- 以等宽字体显示平整的数据。
- 在文件名或URL中添加计数或ID：’file 001.txt’。
- 对齐控制台输出： ‘Test 001: ✓’。
- 打印具有固定位数的十六进制或二进制数字：’0x00FF’。


参考：https://blog.hypers.io/2018/04/11/es2016-17-18/