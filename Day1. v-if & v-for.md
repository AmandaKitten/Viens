# Day1. v-if和v-for哪个优先级高？如果两个同时出现，应该怎么优化得到更好的性能？

### 优先级

首先，官方文档不建议我们在同一元素上使用 `v-if` 和 `v-for`

如果一定要放在同一个元素上的话，`v-if` 和 `v-for`在一同使用时，`v-for`优先级更高，在每一次`v-for`的循环中都会执行一次`v-if`的判断。

#### 优化

1. 将`v-if`和`v-for`分开放在不同元素中，根据实际业务需要，将`v-if`（或`v-for`）移动到父元素中，例如

   ```html
   <ul>
       <li v-if="isTrue">
       	<div v-for= "item in list">
               {{item}}
           </div>
       </li>
   </ul>
   ```

   这也是官方文档建议我们使用的方式

2. 我们还可以使用`computed`计算属性替换掉`v-if`的用法，如：



   ```vue
   <ul>
       <li v-for="(item, id) in fooList" :key="id"></li>
   </ul>
   
   computed: {
       fooList: function() {
           return this.list.filter(function(item)) { 
               return item.foo
           }
       }
   }
   ```

