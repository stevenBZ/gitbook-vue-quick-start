### 一、打印数据调试

使用场景：出问题时大概知道什么地方有问题，比如知道可能是后台传的那个数据类型与前端所需的数据类型不符。

使用方式：在需要打印数据的地方使用 console.log

示例 ：![](/assets/屏幕快照 2018-11-18 下午7.08.27.png)![](/assets/屏幕快照 2018-11-18 下午7.08.40.png)tips: 由于console.log是浏览器提供的方法，而非JavaScript正式的一部分，因此由于执行顺序问题，可能在输出复杂对象时会有输出与预期不符的情况，使用JSON.parse\(JSON.stringify\(x\)\)的方式可以为输出对象保留快照。

### 二、断点调试

使用场景：大部分debug场景

使用方式：1.先确保webpack的devtool选项使用了 \#source-map

                   2.打断点（方法一、在源文件需要打断点的地方输入debugger。方法二、在控制台中选择一个要打断点的文件，然后点击对应的代码行来打断点）。

![](/assets/import35.png)

                   3. 项目运行后，打开控制台的sources页，即可看到当前的程序运行情况，上面的一排按钮分别是暂停/继续、单步执行、单步跳入、单步跳出、禁用/启用所有断点。 在watch面板可以添加要观察的变量，在call stack面板可以看到当前函数的调用栈。

![](/assets/1e5504a40e884fafbacf015d824ef4ea_1c82789959acfbb585352fef6b998ad0.jpg)

                   4. 还可以给DOM元素和异步请求设置断点，给DOM请求设置断点的方式是在控制中选中DOM元素，右键设置断点。给异步请求设置断点的方式是在XHR breakpoints中点 + 按钮来增添XHR断点。

![](/assets/d4c76cad0c494e15b84d302ecc937de8_fcdd3c51e7ea1317621612b12b257ca0.jpg)



tips: 在vue中的变量一般存放在data中，因此在watch中输入的变量一般是this.xxx

### 三、使用vue-devtools调试

使用场景：基于vue开发的前端项目

使用方式：1、在chrome应用商店中下载dev-tools

2、在main.js中加上Vue.config.devtools = true 开启vue-devtools

3、项目运行后，点击chrome中Vue Devtools按钮，打开vue-devtools控制面板，即可在其中查看项目的组件信息、vuex信息、事件信息。

![](/assets/import38.png)

### 四、样式调试

使用场景：调试项目样式

使用方式：1、在chrome控制台中使用元素选择器选择页面中的元素，在样式栏中更改样式查看元素的样式变化。

tips: 在scoped的style中修改Element UI的样式可能会失败，解决方案是为修改目标加一层带类名的包裹容器，然后在这个页面的

&lt;style&gt;中修改目标的样式。

![](/assets/import39.png)

