## 鼠标事件
- click：单击
- dblclick：双击
- mousedown：鼠标上的按钮被按下触发的事件
- mouseup：鼠标按下后，松开时触发的事件
- mouseover：鼠标悬浮
- mouseout：鼠标离开
- mousemove：鼠标移动
- mouseenter：鼠标进入
- mouseleave：鼠标离开

## 鼠标悬停事件
- link通常表示未点击链接的状态
- :visited则为已点击的状态
- :hover为鼠标悬停
- :active为鼠标按下到放开时链接或按钮的状态，
- :disabled常用于表示元素不可用时的状态。

### Vue属性 7个
1. el属性
- 用来指示vue编译器从什么地方开始解析 vue的语法，可以说是一个占位符。
2. data属性
- 用来组织从view中抽象出来的属性，可以说将视图的数据抽象出来存放在data中。
3. template属性
- 用来设置模板，会替换页面元素，包括占位符。
4. methods属性
- 放置页面中的业务逻辑，js方法一般都放置在methods中  方法
5. render属性
- 创建真正的Virtual Dom
6. computed属性
- 用来计算  属性
7. watch属性
- watch:function(new,old){}
- 监听data中数据的变化
- 两个参数，一个返回新值，一个返回旧值，

-  computed用来监控自己定义的变量，该变量不在data里面声明，直接在computed里面定义，然后就可以在页面上进行双向数据绑定展示出结果或者用作其他处理；

### methods,watch,computed的区别
* computed 属性的结果会被缓存，除非依赖的响应式属性变化才会重新计算。主要当作属性来使用；
* methods 方法表示一个具体的操作，主要书写业务逻辑；
* watch 一个对象，键是需要观察的表达式，值是对应回调函数。主要用来监听某些特定数据的变化，从而进行某些具体的业务逻辑操作；可以看作是 computed 和 methods 的结合体；

### 计算属性  computed
- 计算属性默认只有 getter，不过在需要时你也可以提供一个 setter：

        computed: {
        fullName: {
            // getter
            get: function () {
            return this.firstName + ' ' + this.lastName
            },
            // setter
            set: function (newValue) {
            var names = newValue.split(' ')
            this.firstName = names[0]
            this.lastName = names[names.length - 1]
            }
        }
        }

### class

- JS中的false： false，0，“”，null，undefined和NaN 

### display:none与visible:hidden的区别
1. display:none和visible:hidden都能把网页上某个元素隐藏起来，但两者有区别:
2. display:none ---不为被隐藏的对象保留其物理空间，即该对象在页面上彻底消失，通俗来说就是看不见也摸不到。
3. visible:hidden--- 使对象在网页上不可见，但该对象在网页上所占的空间没有改变，通俗来说就是看不见但摸得到。

###  v-if和v-show 什么区别
区别
1. 手段：v-if是通过控制dom节点的存在与否来控制元素的显隐；v-show是通过设置DOM元素的display样式，block为显示，none为隐藏；
2. 编译过程：v-if切换有一个局部编译/卸载的过程，切换过程中合适地销毁和重建内部的事件监听和子组件；v-show只是简单的基于css切换；
3. 编译条件：v-if是惰性的，如果初始条件为假，则什么也不做；只有在条件第一次变为真时才开始局部编译（编译被缓存？编译被缓存后，然后再切换的时候进行局部卸载); v-show是在任何条件下（首次条件是否为真）都被编译，然后被缓存，而且DOM元素保留；
4. 性能消耗：v-if有更高的切换消耗；v-show有更高的初始渲染消耗；
