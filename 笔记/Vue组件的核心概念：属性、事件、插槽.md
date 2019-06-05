# Vue组件的核心概念：属性、事件、插槽

## 属性

+ 自定义属性 props 

   组件 props 中声明的属性

+ 原生属性 attrs 

  没有声明的属性，默认自动挂载到组件根元素上，设置 inheritAttrs 为 false 可以自动关闭挂载

+ 特殊属性 class、style 

  挂载到组件根元素上，支持字符串、数组、对象等多种语法

## 事件

+ 普通事件

  @click，@input，@change，@xxx 等事件，通过 this.$emit('xxx', ...) 触发

+ 修饰符事件

  @input.trim，@click.stop，@submit.prevent 等，一般用于原生 HTML 元素，自定义组件需要自行开发支持

## 插槽

+ 普通插槽

  ```vue
  <template slot="xxx">...</template>  
  <template v-slot="xxx">...</template> // 2.6 新语法 
  ```

+ 作用域插槽

  ```vue
  <template slot="xxx" slot-scope="props">...</template>
  <template v-slot:xxx="props">...</template> // 2.6 新语法
  ```

## 大属性

万物皆“属性”，属性、事件、插槽都是“属性”

