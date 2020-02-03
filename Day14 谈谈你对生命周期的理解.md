1. # Day14 谈谈你对生命周期的理解








![Vue 实例生命周期](https://cn.vuejs.org/images/lifecycle.png)



生命周期成对出现

`beforeCreate()`  ： 在实例创建之前

`created()`：实例创建之后，此时`$el`还不能使用

`beforemount()`：实例挂载之前，相关`render`函数首次被调用

`mounted()`：实例挂载之后，`$el`已经被挂载到真实DOM上。

`beforeUpdate()`:数据更新之前调用，此时数据尚未被更新

`updated()`:数据完成更新后，调用该钩子

`beforedestroy()`：组件销毁前

`destroyed()`：组件被全部销毁后