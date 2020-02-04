#Day15 谈谈你对vuex使用及其理解？

> Vuex 是一个专为 Vue.js 应用程序开发的**状态管理模式**。它采用集中式存储管理应用的所有组件的状态，并以相应的规则保证状态以一种可预测的方式发生变化。

Vuex 的核心由五部分组成：State、Getter、Mutation、Action 和 Module。

- State：**单一状态树**,即用一个对象就包含了全部的应用层级状态。每个应用将仅仅包含一个 store 实例。单一状态树让我们能够直接地定位任一特定的状态片段，在调试的过程中也能轻易地取得整个当前应用状态的快照。
- Getter：相当于vue中的computed计算属性，getter 的返回值会根据它的依赖被缓存起来，且只有当它的依赖值发生了改变才会被重新计算，Getters 可以用于监听、state中的值的变化，返回计算后的结果
- Mutation： 修改store中的值唯一的方法
- Action： Action 类似于 mutation，不同在于：
  - Action 提交的是 mutation，而不是直接变更状态。
  - Action 可以包含任意异步操作。

- Module： 在应用十分复杂时，需要将store分割成模块，即Module