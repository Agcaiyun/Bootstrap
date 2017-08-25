## 一些基础知识记录
* ```Bootstrap``` 中设置了一个全局的正文文本样式：字号 ```14px``` ; 行高大约 ```20px``` ; 颜色 深灰色（```#333```）
* 颜色类强调类名

    * ```.text-muted```：提示，使用浅灰色（```#999```）
    * ```.text-primary```：主要，使用蓝色（```#428bca```）
    * ```.text-success```：成功，使用浅绿色(```#3c763d```)
    * ```.text-info```：通知信息，使用浅蓝色（```#31708f```）
    * ```.text-warning```：警告，使用黄色（```#8a6d3b```）
    * ```.text-danger```：危险，使用褐色（```#a94442```）

* 文本对齐风格
    * ```css``` 中经常使用 ```text-align``` 来实现，其中取值可以为
        * ```left   ```       左对齐
        * ```center ```       居中对齐
        * ```right  ```       右对齐
        * ```justify```       两端对齐
        * **但是目前两端对齐在各浏览器下解析各有不同，特别是应用于中文文本的时候，所以项目中要慎用**
    * ```bootstrap``` 中 ，为了方便使用，通过定义四个类名来控制文本的对齐风格
        * ```.text-left```
        * ```.text-center```
        * ```.text-right```
        * ```.text-justify```
        * **但是目前两端对齐在各浏览器下解析各有不同，特别是应用于中文文本的时候，所以项目中要慎用**
        > ```<p class="text-left">我居左</p>```

* Bootstrap 中提供的三种编码风格

    * 使用```<code></code>```来显示单行内联代码          一般是针对于单个单词或单个句子的代码
    * 使用```<pre></pre>```来显示多行块代码              一般是针对于多行代码（也就是成块的代码）
    * 使用```<kbd></kbd>```来显示用户输入代码            一般是表示用户要通过键盘输入的内容
    * **虽然不同的类型风格不一样，但是使用方法都是一样的
        > ```<div>```请输入```<kbd>``` ```ctr+c``` ```</kbd>```来复制代码，然后使用```<kbd>``` ```ctrl+v``` ```</kbd>```来粘贴代码 ```</div>```

    > 正如前面所示,```<pre>``` 元素一般用于显示大块的代码，并保证原有格式不变。但有时候代码太多，而且不想让其占有太大的页面篇幅，就想控制代码块的大小。```Bootstrap```也考虑到这一点，你只需要在```pre```标签上添加类名“```.pre-scrollable```”，就可以控制代码块区域最大高度为 **340px** ，一旦超出这个高度，就会在 **Y** 轴出现滚动条

* 表格
    * 表格是 ```Bootstrap``` 的一个基础组件之一， ```Bootstrap```  为表格提供了 **一种基础样式** **四种附加样式** 和 **一个支持响应式的表格** 
    * 具体类名及含义为：
        * ```table```              基础表格
        * ```table-striped```      斑马线表格
        * ```table-bordered```     带边框的表格
        * ```table-hover```        鼠标悬停高亮的表格
        * ```table-condensed```    紧凑型表格
        * ```table-responsive```   响应式表格
        * 如果需要多种样式，则在基础样式的基础上，加上需要的样式即可

* 表格行的类 
    * ```Bootstrap```  还为表格的行元素 ```<tr>``` 提供了五种不同的类名，每种类名控制了行的不同背景颜色
    > 特别提示：除了```”.active”```之外，其他四个类名和 ```”.table-hover”``` 配合使用时，```Bootstrap``` 针对这几种样式也做了相应的悬浮状态的样式设置，所以如果需要给```tr```元素添加其他颜色样式时，在```”.table-hover”```表格中也要做相应的调整

    > 注意要实现悬浮状态，需要在```<table>```标签上加入```table-hover```类
* 表单控件（复选框 ```checkbox``` 和 ```radio``` ）
    * 优点：当 ```checkbox``` 和 ```radio``` 与 ```label``` 标签配合使用的时候，会出现一些小问题（比如对齐问题），使用 ```Bootstrap``` 框架可以解决这个问题
    * 具体用法为:
    ```
    <div class="checkbox">
        <label>
            <input type="checkbox" value="">
            记住密码
        </label>
    </div>
    <div class="radio">
        <label>
            <input type="radio" name="optionsRadios" id="optionsRadios1" value="love" checked>
            喜欢
        </label>
    </div>

    ```
    * 上面示例的特点：
        * 不管是```checkbox```还是```radio```都使用```label```包起来了

        * ```checkbox```连同```label```标签放置在一个名为“```.checkbox```”的容器内

        * ```radio```连同```label```标签放置在一个名为“```.radio```”的容器内

        * 在```Bootstrap```框架中，主要借助“```.checkbox```”和“```.radio```”样式，来处理复选框、单选按钮与标签的对齐方式

* 表单状态的作用
    * 每一中状态都能给用户传递不同的信息
        * 表单有焦点的装填可以告诉用户可以输入或选择东西
        * 禁用状态可以告诉用户不可以输入或选择东西
        * 表单控件验证状态，可以告诉用户的操作是否正确

* 表单控件状态（禁用状态）
    * 在 ```Bootstrpa``` 框架中，如果 ```fieldset``` 设置了 ```disabled``` 属性，整个域都将处于被禁用状态，**但是** 如果 ```fieldset``` 后面紧跟着的是 ```legend```标签，那么```legend``` 内部的 ```input```在表面看是 颜色变成灰色的了，但是 并没有被禁用，还是可以进行输入的。**注意** 只有 ```fieldset``` 后面第一个就是 ```legend``` (而不是其他的标签，比如 ```label```) 的时候，才会出现 变灰但不禁用 的情况，而且只有**第一个**  ```legend``` 是 灰色不禁用 的状态，后面的```legend``` 照样是 灰色禁用  的。
        * 比如：
        >   <form role="form">
                <fieldset disabled>
                    <legend>
                        <input type="text" id="a" class="form-control" placeholder="显然我颜色变灰了，但是我没被禁用，不信？单击试一下" />
                    </legend>
                </fieldset>
            </form>

* 按钮状态 -- 禁用状态
    * 在 ```Bootstrap``` 中，禁用按钮有两种实现方式
        * 在标签中添加  ```disabled``` 属性
        * 在元素便签中添加类名 ```disabled```
    ```
    <button class="btnbtn-primary btn-lgbtn-block" type="button" disabled="disabled">通过disabled属性禁用按钮</button>
    <button class="btnbtn-primary btn-block disabled" type="button">通过添加类名disabled禁用按钮</button>
    <button class="btnbtn-primary btn-smbtn-block" type="button">未禁用的按钮</button>
    ```

    * 两种方法的区别
        * ```.disabled``` 样式不会禁止按钮的默认行为
        > 比如：提交和重置行为等
        > 如果想要让这样的禁用按钮也能禁止按钮的默认行为，则需要通过 JS 这样的语言来处理
        > 对于 ```a``` 标签也存在类似的问题。如果通过类名 ```.disabled``` 来禁用按钮，其链接行为是无法禁止的。

        * 而在元素标签中添加 ```disabled```  属性的方法是可以禁止元素的默认行为的

* ```Bootstrap``` 的响应式效果
    * ```Bootstrap```  框架的网格系统中带有响应式效果，其带有四种类型的浏览器（超小屏 ```xs``` , 小屏 ```sm``` ，中屏 ```md```  ，大屏 ```lg``` ),其断电（像素的分界点） 是：  768px、992px 、 1220px

* 列偏移
    * eg. ```.col-md-offset-4``` ：该列向右偏移  四个列 的宽度
    **注意**
        * 使用   ```col-md-offset-* ```对列进行向右偏移时，要保证列与偏移列的总数不超过```12```，不然会致列断行显示
    ```
    <div class="row">
        <div class="col-md-3">.col-md-3</div>
        <div class="col-md-3 col-md-offset-3">col-md-offset-3</div>
        <div class="col-md-4">col-md-4</div>
    </div>
    ```

* 下拉菜单
    * 在 ```Bootstrap``` 框架中的 *下拉菜单组件* 是一个独立的组件，我们子啊使用 ```Bootstrap``` 框架的下拉菜单时。必须调用     ``` Bootstrap``` 框架提供的 ```bootstrap.js``` 文件（或者使用 未编译的版本 。
    **注意**
        * ```Bootstrap``` 的组件交互效果都是依赖于 jQuery 库写的，所以在使用 ```bootstrap.min.js``` 之前一定要先加载 ```jquery.min.js ``` 才会生效

    
* 下拉菜单使用方法
    * 使用一个名为 ```dropdown``` 的容器包裹了整个下拉菜单元素。
        * 比如：```<div class="dropdown"></div>```
    * 使用一个 ```<button>``` 按钮作为父菜单，并且定义类名为```dropdown-toggle``` 和自定义 ```data-toggle``` 属性，且值必须和最外层容器类名一致，
        * 比如：```data-toggle="dropdown" ```
    * 下拉菜单项使用一个 ```ul```列表，并且定义一个类名为 ```dropdown-menu``` 
        * 比如：```<ul class="dropdown-menu">```

* 下拉菜单的原理分析
    * 通过```js```技术手段，给父容器```div.dropdown```添加或移除类名```open```来控制下拉菜单显示或隐藏。也就是说，默认情况```div.dropdown```没有类名```open```，当用户第一次点击时，```div.dropdown```会添加类名```open```；当用户再次点击时，```div.dropdown```容器中的类名```open```又会被移除。我们可以通过浏览器的firebug查看整个过程

    [默认没有 open 属性](http://img.mukewang.com/53e314020001537208700352.jpg)

    [第一次点击之后添加 open 属性 ](http://img.mukewang.com/53e314360001a81808720333.jpg)

    [再次点击 open 属性被移除](http://img.mukewang.com/53e31461000180e608710333.jpg)

* 面包屑导航
    **作用**
        * 面包屑(```Breadcrumb```)一般用于导航，主要是起的作用是告诉用户现在所处页面的位置（当前位置）
    ```
        <ol class="breadcrumb">
            <li><a href="#">首页</a></li>
            <li><a href="#">我的书</a></li>
            <li class="active">《图解CSS3》</li>
        </ol>
    ```
    **注意**
        * ```li``` 与 ```li``` 之间的分隔符是使用 ```li + li :before``` 来实现的，所以这种方案在 IE 低版本是不支持的
    
    * [关于面包屑的简介](http://lchseo.com/archives/106)

* 导航条 与 导航 的区别
    * 导航条```navbar``` 中有一个背景色、而且导航条可以是纯链接（类似导航），也可以是表单，还有就是表单和导航一起结合等多种形式

    * 制作导航条的步骤
        * 首先在制作导航的列表```<ul class="nav">``` 的基础上添加类名 ```navbar-default```
        > ```.navbar``` 样式的主要功能就是设置左右 ```padding``` 和 圆角等效果，但它和颜色相关的样式没有进行任何的设置
        * 然后在列表外部添加一个容器 ```div``` ，并且使用类名 ```.navbar ``` 和 ```navbar-default``` 
        > 导航条的颜色是通过 ```.navbar-default``` 来进行控制的 

    ```
        <div class="navbar navbar-default" role="navigation">
            <ul class="nav navbar-nav">
                <li class="active"><a href="##">网站首页</a></li>
                <li><a href="##">系列教程</a></li>
                <li><a href="##">名师介绍</a></li>
                <li><a href="##">成功案例</a></li>
                <li><a href="##">关于我们</a></li>
            </ul>
        </div>
    ```

* 导航条中的按钮、文本和链接
    * ```Bootstrap```框架的导航条中除了使用```navbar-brand```中的```a```元素和```navbar-nav```的```ul```和```navbar-form```之外，还可以使用其他元素。框架提供了三种其他样式：
        * 导航条中的按钮```navbar-btn```
        * 导航条中的文本```navbar-text```
        * 导航条中的普通链接```navbar-link```
    
    **注意**
    但这三种样式在框架中使用时受到一定的限制，需要和```navbar-brand```、```navbar-nav```配合起来使用。**而且对数量也有一定的限制，一般情况在使用一到两个不会有问题，超过两个就会有问题**

* 固定导航条
    * ```.navbar-fixed-top```：导航条固定在浏览器窗口顶部
    * ```.navbar-fixed-bottom```：导航条固定在浏览器窗口底部
    * 原理 
        * 就是在```navbar-fixed-top```和```navbar-fixed-bottom```使用了```position：fixed```属性，并且设置```navbar-fixed-top```的```top```值为```0```,而```navbar-fixed-bottom```的```bottom```值为```0```
    * Bug
        * 当内容足以撑满在 ```top```  和 ```bottom``` 之间的高度时（假设顶部 底部 都有导航条） ,**页面主内容顶部和底部部分的内容都会被 固定导航条 给遮挡住了

    * 解决 ```Bug``` 的方法1
        * 给 ```body``` 设置 ```padding-top``` ```padding-bottom``` （根据是 顶部导航 还是 底部导航 进行适当的设置） 
    * 解决 ```Bug``` 的方法2

        〉 把固定导航条都放在页面内容前面
        ```
            <div class="navbar navbar-default navbar-fixed-top" role="navigation">
        　…
            </div>
            <div class="navbar navbar-default navbar-fixed-bottom" role="navigation">
            　…
            </div>
            <div class="content">我是内容</div>
        ```

* 响应式导航条（使用方法）
    * 保证在 窄屏幕时**需要折叠的内容**必须包裹在一个 ```div``` 内，并且为 ```div``` 加入 ```collapse```、```navbar-collapse``` 两个类名。最后为这个 ```div``` 添加一个 ```class``` 类名  或者 ```id ```名
    * 保证在 窄屏 时要显示的图标样式（固定写法）
    ```
    <button class="navbar-toggle" type="button" data-toggle="collapse">
        <span class="sr-only">Toggle Navigation</span>
        <span class="icon-bar"></span>
        <span class="icon-bar"></span>
        <span class="icon-bar"></span>
    </button>
    ```
    * 并为 ```button``` 添加 ```data-target = .类名/#id名``` ，究竟是 类名 还是 id名，要根据需要折叠的 ```div ``` 来决定