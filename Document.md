##  Vue3知识点

* Vue3的Template模板支持多个根标签      
* Vue3通过createApp()创建实例对象，Vue2通过new Vue()创建        
* createApp接受一个组件做参数，new Vue接受一个对象    
* 新增context.emit，与this.$emit作用相同      
* [v-model](https://v3.vuejs.org/guide/migration/v-model.html)新用法：1.属性名任意,如xx；2.事件名必须为"update:xx"
  
  ````js
    <Switch :value="x" @update:value="x=$event">
    可简写为：
    <Switch v-model:value="x">
  `````
* Vue3属性绑定：
  - 默认所有属性都绑定到根元素  
  - 使用inheritAttrs:false可以取消默认绑定    
  - 使用$attrs 或者 context.attrs获取所有属性   
  - 使用 v-bind = "$attrs"批量绑定属性    
  - 使用const {size, ...rest} = context.attrs 将属性分开
* props VS attrs
  - props要先声明才能获取值，attrs不需要声明    
  - props不包含事件，attrs包含   
  - props没有声明的属性会显示到attrs里    
  - props支持string以外的类型，attrs只有string类型    
  

## 踩坑指南     

* 使用Typescript，报找不到xxx.vue模块               
  > Typescript只能理解.ts文件，创建xxx.d.ts文件，告诉TS识别.vue文件     

* UI库的CSS注意事项
  - 不能使用scoped：默认会添加唯一变量；必须输出稳定不变的class选择器，方便使用者覆盖   
  - 必须加前缀：区别使用者常用命名    
  - CSS最小影响原则   

## API设计

### Switch组件
```js
  <Switch v-model:value="value"/>
```

### Button组件
```js
<Button
  @click=?
  @focus=?
  @mouseover=?
  theme="button || link || text"
  level="main || normal || danger"
  size="big || normal || small"
  disabled
  loading
  ></Button>
```

  