##### 实例开始

每个Vue应用都是从一个`new Vue(options)`开始，
```
var vm = new Vue({
  // 选项
})
```

##### Vue的设计思想 MV*  

专注状态的处理，而Vue帮你处理视图和状态的联系，Vue的设计受到MVVM模型的大量启发，但是Vue并没有完全遵守的MVVM模型。

这里官网上说，Vue不是完全遵守MVVM模型。

首先我们看看什么是MVVM模型：

1. M（模型）：模型是指代表真实状态内容的领域模型（面向对象），或指代表内容的数据访问层（以数据为中心）

2. V（视图）：就像在MVC和MVP模式中一样，视图是用户在屏幕上看到的结构、布局和外观（UI）。

3. VM（视图模型）：视图模型是暴露公共属性和命令的视图的抽象。MVVM没有MVC模式的控制器，也没有MVP模式的presenter，有的是一个绑定器。在视图模型中，绑定器在视图和数据绑定器之间进行通信。有点绕，简单来说，视图和模型只与视图模型进行交互，而View 层不直接和 Model 层通信（划重点）。

我们再来看看Vue。

Vue让我们专注于状态的变化，进行业务逻辑开发，而*自动*处理状态到视图的变化，这部分由Vue给我们处理。所以 （data,props） 是MVVM中的M模型，tempate属于View,Vue充当着视图模型的角色。

Vue无疑参考了很多MVVM的设计思想，但是与传统意义中的MVVM不一样，Vue并没有完全断绝V和M的直接联系，反而提供了一些使用的api来让我们进行操作，所以有了官网上那一句：
> 虽然没有完全遵循 MVVM 模型，但是 Vue 的设计也受到了它的启发。

典型示例：`$refs` 。

 `$refs`访问的时候绑定的是DOM或者组件，提供了我们在操作状态的时候直接操作DOM的接口，这就很不MVVM了，虽然官网上也提示不要过度依赖他，但是通过`$refs`调用子组件的方法，用过的都知道多棒（手动滑稽--，）。

当然统称mv*的前端框架是毫无问题的。



