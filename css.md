
## css
###初级 
####  css选择器有哪些

1. ***通用选择器**：选择所有元素，**不参与计算优先级**，兼容性IE6+
2. **#X id选择器**：选择id值为X的元素，兼容性：IE6+
3. **.X 类选择器**： 选择class包含X的元素，兼容性：IE6+
4. **X Y后代选择器**： 选择满足X选择器的后代节点中满足Y选择器的元素，兼容性：IE6+
5. **X 元素选择器**： 选择标所有签为X的元素，兼容性：IE6+
6. **:link，：visited，：focus，：hover，：active链接状态**： 选择特定状态的链接元素，顺序LoVe HAte，兼容性: IE4+
7. **X + Y直接兄弟选择器**：在**X之后第一个兄弟节点**中选择满足Y选择器的元素，兼容性： IE7+
8. **X > Y子选择器**： 选择X的子元素中满足Y选择器的元素，兼容性： IE7+
9. **X ~ Y兄弟**： 选择**X之后所有兄弟节点**中满足Y选择器的元素，兼容性： IE7+
10. **[attr]**：选择所有设置了attr属性的元素，兼容性IE7+
11. **[attr=value]**：选择属性值刚好为value的元素
12. **[attr~=value]**：选择属性值为空白符分隔，其中一个的值刚好是value的元素
13. **[attr|=value]**：选择属性值刚好为value或者value-开头的元素
14. **[attr^=value]**：选择属性值以value开头的元素
15. **[attr$=value]**：选择属性值以value结尾的元素
16. **[attr*=value]**：选择属性值中包含value的元素
17. **[:checked]**：选择单选框，复选框，下拉框中选中状态下的元素，兼容性：IE9+
18. **X:after, X::after**：after伪元素，选择元素虚拟子元素（元素的最后一个子元素），CSS3中::表示伪元素。兼容性:after为IE8+，::after为IE9+
18. **:hover**：鼠标移入状态的元素，兼容性a标签IE4+， 所有元素IE7+
19. **:not(selector)**：选择不符合selector的元素。**不参与计算优先级**，兼容性：IE9+


#### display: none;与visibility: hidden;的区别
```
1. display:none;会让元素完全从渲染树中消失，渲染的时候不占据任何空间；visibility: hidden;不会让元素从渲染树消失，渲染师元素继续占据空间，只是内容不可见
2. display: none;是非继承属性，子孙节点消失由于元素从渲染树消失造成，通过修改子孙节点属性无法显示；visibility: hidden;是继承属性，子孙节点消失由于继承了hidden，通过设置visibility: visible;可以让子孙节点显式
3. 修改常规流中元素的display通常会造成文档重排。修改visibility属性只会造成本元素的重绘。
4. 读屏器不会读取display: none;元素内容；会读取visibility: hidden;元素内容
```

#### CSS有哪些继承属性

关于文字排版的属性如：font, word-break, letter-spacing,text-align,text-rendering,word-spacing,white-spacing,text-indent,text-transform,text-shadow
line-height
color
visibility

#### 解释一下外边距折叠(collapsing margins),有什么规则
毗邻的两个或多个margin会合并成一个margin，叫做外边距折叠。规则如下：

 1. 两个或多个毗邻的普通流中的块元素垂直方向上的margin会折叠
 2. 浮动元素/inline-block元素/绝对定位元素的margin不会和垂直方向上的其他元素的margin折叠
 3. 创建了块级格式化上下文的元素，不会和它的子元素发生margin折叠
 4. 元素自身的margin-bottom和margin-top相邻时也会折叠
 
#### link和@import的区别是
　本质上，这两种方式都是为了加载CSS文件，但还是存在着细微的差别。
　
 1.  老祖宗的差别。link属于XHTML标签，而@import完全是CSS提供的一种方式。link标签除了可以加载CSS外，还可以做很多其它的事情，比如定义RSS，定义rel连接属性等，@import就只能加载CSS了。
 2. 加载顺序的差别。当一个页面被加载的时候（就是被浏览者浏览的时候），link引用的CSS会同时被加载，而@import引用的CSS会等到页面全部被下载完再被加载。
 3. 兼容性的差别。由于@import是CSS2.1提出的所以老的浏览器不支持，@import只有在IE5以上的才能识别，而link标签无此问题。
 4. 使用dom控制样式时的差别。当使用javascript控制dom去改变样式的时候，只能使用link标签，因为@import不是dom可以控制的。
 
#### 说说几种清除浮动的方法

###进阶

#### 水平居中和垂直居中
 - 如果需要居中的元素为常规流中的inline元素，为父元素设置`text-align:center`；即可实现
 - 如果需要居中的元素为常规流中的block元素，1）为元素设置宽度，2）设置左右margin为auto。3）IE6下需在父元素上设置`text-align: center`;,再给子元素恢复需要的值

#### 解释css sprites，如何使用
css精灵，把一堆小的图片整合到一张大的图片上，减轻服务器对图片的请求数量
###### -----还有没其他的

#### 优先级算法如何计算
重要性和来源的优先级排序从低到高是：

 1. 浏览器默认样式
 2. 用户在浏览器中定义的普通样式（normal规则，不带important规则）
 3. 开发人员定义的普通样式（ normal规则，不带important规则）
 4. 开发人员定义特殊样式（带important规则）
 5. 用户在浏览器中定义特殊样式（带important规则）

另外还有一些原则：

 1. 相同的样式在CSS规则后添加了!important的优先于没有添加的。
 2. CSS规则在文档中出现的顺序后面定义的的优先于前面定义的。
 3. 内联样式优先于用link引入的样式和页面上<style>里的样式。
 
#### 你了解less吗，有什么好处
#### 对Normalize.css 的了解
#### 对响应式有什么了解