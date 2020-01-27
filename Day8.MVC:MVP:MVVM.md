# Day8： 谈谈你对MVC、MVP和MVVM的理解

**MVC**

![mvc](https://img4.mukewang.com/5bc349f6000164c807060422.jpg)

在图中可以看到，MVC模式的结构分为 Model层、View层和Controller层，在用户从View层发起请求的时候，指令会通过Controller修改Model的数据，再由Model层更新数据过后在View层呈现，View层也可以直接与Model层进行交互而不经过Controller。

这种模式有比较明显的缺点是：

 1、View层与Model层耦合严重，不利于复杂项目的管理，测试难，维护难

2、Activity责任不明、十分臃肿
Activity由于其生命周期的功能，除了担任View层的部分职责（加载应用的布局、接受用户操作），还要承担Controller层的职责（业务逻辑的处理）





 **MVP**

![mvp](https://img.mukewang.com/5bc349f700015b1706980440.jpg)

MVP模式相对于MVC来说，解耦了View层和Model层，都由Presenter层进行数据传输，在此基础上，View层和Presenter层也并没有强耦合，通过调用接口的方式，使得两个模块相互独立，便于测试和维护。



**MVVM**



![img](https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1580150208596&di=2cc8f3741c8fc819a7abaa5b8642f878&imgtype=jpg&src=http%3A%2F%2Fimg1.imgtn.bdimg.com%2Fit%2Fu%3D2450431496%2C408066061%26fm%3D214%26gp%3D0.jpg)

MVVM模式最大的优点是实现了数据绑定，将View层和ViewModel层绑定在一起，当ViewModel层的数据变动时，View将同步更新。由于这个特性，开发过程中可以专注于数据和业务逻辑，UI相关的操作由ViewModel自己决定，也就是我们常说的**数据驱动**