##  Vue3知识点

* Vue3的Template模板支持多个根标签      
* Vue3通过createApp()创建实例对象，Vue2通过new Vue()创建        
* createApp接受一个组件做参数，new Vue接受一个对象      

## 踩坑指南     

* 使用Typescript，报找不到xxx.vue模块               
  > Typescript只能理解.ts文件，创建xxx.d.ts文件，告诉TS识别.vue文件     

  