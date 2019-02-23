 # Best Practice
 
 * `markdown高亮`
 
 * select框的option选项用xxxxOptions
 
 * [Vuex持久化插件](https://www.npmjs.com/package/vuex-persistedstate)
 
 * 在声明props命名时使用驼峰，template模版中使用短横线
 ```
 <my-component my-prop>
 ```
 
 * Vue自定义事件，使用短横线命名
 ```
 this.$emit('my-event')
 ```

 * [浏览器下载文件插件FileSaver](https://github.com/eligrey/FileSaver.js)
 
 * 封装条件语句
 ```
 const isComplexDataType = obj => (typeof obj === 'object' || typeof obj === 'function') && (obj !== null)
 
 if(isComplexDataType(something)){
 //.......
 }
 ```

* [Vue风格指南](https://cn.vuejs.org/v2/style-guide/)
 
* 使用逻辑运算符（&& ||）替换三元运算符（适合不需要第二个条件的情况）
```
hasMoney ? console.log('有钱') : null

hasMoney && console.log('有钱')
```
 
* 尽量不要用取反(!)作为判断条件 
 
* 使用函数默认值替代备用的选项

* 统一把icon-class换成svg的形式

* 验证使用handleValidate,搜索使用handleSearch,提交用handleSubmit

* 路由跳转的函数名使用linkXXX
```
   linkEdit() {
                this.$router.push({
                    name:'hospManagement'
                })
            }
```

* scss写在vue文件里面,创建style文件,放入公共的全局样式,以及mixin封装的样式,以及variables变量单独存储统一颜色,以及elementui自定义的样式

* 日期格式化轻量级库[day.js](https://github.com/iamkun/dayjs)
```
npm install dayjs --S
```

* 减少嵌套，尽早return
```
function test(fruit, quantity) {
  const redFruits = ['apple', 'strawberry', 'cherry', 'cranberries'];
  if (!fruit) throw new Error('No fruit!'); // condition 1: throw error early
  if (!redFruits.includes(fruit)) return; // condition 2: stop when fruit is not red
  console.log('red');
  // condition 3: must be big quantity
  if (quantity > 10) {
    console.log('big quantity');
  }
}
```

* 封装函数时，尽量使用函数表达式取代语句，表达式有返回值，语句没有返回值（尽量使用纯函数，防止影响其他代码）
```
function setBackgroundColor(ele, color) {
    ele.style.backgroundColor = color;
    return color;
}

// 多处使用
var ele = document.querySelector('.test');
setBackgroundColor(ele, 'red');
setBackgroundColor(ele, '#ccc');
```
* ~~currentTableData放在computed里面,值是currentPage和tableData计算后的结果~~

    封装了分页器组件,每次分页向父组件触发currentChange事件

* vuex的store文件创建一个mutations-types
```
 ballInCart({commit}, boolean) {
    commit(types.BALL_IN_CART, boolean);
  }
```

* 如果一个模块下就一个文件，尽量写成 index.vue 。这里文件夹和文件同名，路由是不是很长？你在其他文件中 import 的时候是不是也不方便？ 而且我发现 problemManagement 和 problemRetrieve 都属于问题管理模块，完全可以合并到一个文件夹里啊。还有，文件夹已经表明是问题管理模块了，所以文件名就不要再以 problem*** 开头了。
```
problemManagement
│   ├── index.vue
│   ├── retrieve.vue
qualityCheckAppeal
    └── index.vue
```

* [编辑和创建的界面差不多可以使用同一组件,在路由的meta信息中标注是那个功能](https://juejin.im/post/593121aa0ce4630057f70d35)

![](https://lc-gold-cdn.xitu.io/25969342df96a2000ec6?imageView2/0/w/1280/h/960/format/webp/ignore-error/1)


```
computed: {
  isEdit() {
    return this.$route.meta.isEdit // 根据meta判断
    // return this.$route.path.indexOf('edit') !== -1 // 根据路由判断
  }
}，
created() {
  if (this.isEdit) { 
    this.fetchData();
  }
}
```

* elementui修改框架样式时,可以在外面套一层id选择器(权重100),避免全局样式覆盖组件样式,导致权重不够的问题



# TodoList

* [ ] 了解async/await内部实现原理

* [ ] 看Vue源码(ing!)

* [x] 学习数据结构与算法

* [ ] 刷leetCode(待定)

* [x] 看完这个[前端进阶](https://www.jianshu.com/p/996671d4dcc4)

* [x] ~~使用vue+typescript重构公司项目~~重构公司项目,提取多个公共组件



