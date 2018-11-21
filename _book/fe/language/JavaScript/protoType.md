# 原型链和作用域链

## 原型链
每个对象都会在其内部初始化一个属性，就是prototype(原型)，当我们访问一个对象的属性时，如果这个对象内部不存在这个属性，那么他就会去prototyp e里找这个属性，这个prototype又会有自己的prototype，于是就这样一直找下去，也就是我们平时所说的原型链的概念。


关系：`instance.constructor.prototype = instance.__proto__`


特点：
- JavaScript对象是通过引用来传递的，我们创建的每个新对象实体中并没有一份属于自己的原型副本。当我们修改原型时，与之相关的对象也会继承这一改变。


- 当我们需要一个属性的时，Javascript引擎会先看当前对象中是否有这个属性， 如果没有的话，就会查找他的Prototype对象是否有这个属性，如此递推下去，一直检索到 Object 内建对象。


```javascript
  function Func(){}
  Func.prototype.name = "Sean";
  Func.prototype.getInfo = function() {
  return this.name;
  }
  var person = new Func();//现在可以参考var person = Object.create(oldObject);
  console.log(person.getInfo());//它拥有了Func的属性和方法
  //"Sean"
  console.log(Func.prototype);
  // Func { name="Sean", getInfo=function()}

```

## 作用域链
全局函数无法查看局部函数的内部细节，但局部函数可以查看其上层的函数细节，直至全局细节。


当需要从局部函数查找某一属性或方法时，如果当前作用域没有找到，就会上溯到上层作用域查找，直至全局函数，这种组织形式就是作用域链。

思考：谈谈对js中this的理解