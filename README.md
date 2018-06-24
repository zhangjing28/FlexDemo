# FlexDemo
### 1. flex相关概念

**flex容器(flex container)**：对一个DOM元素添加```display:flex```或者```display:inline-flex```可以将其变成一个flex容器(flex container)  
**flex 项目(flex item)**： 对于一个flex容器内的所有子元素将变成flex项目  
>注： 对于flex容器内的文本节点也将变成flex项目，不连续的文本节点将变成两个不同的flex项目;[相关链接](https://github.com/zhangjing28/FlexDemo/blob/master/page/flexWithText.html)     
[相关代码]((https://github.com/zhangjing28/FlexDemo/blob/master/page/flexWithText.html) )  
![相关结果](https://upload-images.jianshu.io/upload_images/12275615-6ffaa5b0cf20032d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)  
**主轴(main axis)**:flex容器默认的主轴为水平的  
**交叉轴(cross axis)**:flex容器默认的交叉轴为垂直的  
![相关概念示意图.png](https://upload-images.jianshu.io/upload_images/12275615-187a7930c0f5580b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)  
>注：当flex容器的flex-direction属性从默认的row变成column时，主轴为垂直的，交叉轴为水平的  

### 2. flex容器上的属性  
**flex-direction**: row | row-reverse | column | column-reverse;  
**flex-wrap**: nowrap | wrap | wrap-reverse;  
**flex-flow**: flex-driection | flex-wrap;  
**justify-content**: flex-start | flex-end | center | space-between | space-around | space-evenly;  
**align-items**: flex-start | flex-end | center | baseline | stretch;  
**align-content**: flex-start | flex-end | center | space-between | space-around | stretch | space-evenly;  
### 3. flex项目上的属性  
**flex-grow**: number /* default 1 */  
**flext-shrink**: number /* default 1 */  
**flex-basis**: <length> | auto /* default auto */  
**flex**: flex-grow | flex-shrink | flex-basis  
> flex默认值为 0 1 auto  
```flex: 0;```等价于```flex: 0 0 auto;```  
```flex: auto;```等价于 ```flex: 1 1 auto```  
  
**align-self**: auto | flex-start | flex-end | center | baseline | stretch  
**order**: number /*  default  0 */  
### 4. flex-grow计算方式  
**前提**：父元素宽度为400px，item1,item2,item3宽度均为100px; item1的flex-grow设置为2;item2的flex-grow设置为3；计算过程如下:  
flex容器的可分配空间为400 - 100*3 = 100;  
需要分配的总份数为 2+3 = 5;  
一份的宽度为 100 / 5 = 20;  
item1的最终宽度为100 + 20 * 2 = 140;  
item2的最终宽度为 100 + 20 * 3 = 160;   
[具体demo]()  
### 5. flex-shrink计算方式  
父元素宽度为400px，item1,item2,item3宽度均为200px; item1的flex-shrink设置为2;item2的flex-shrink设置为3；计算过程如下：  
flex容器的可分配空间为400 - 200 * 3 = -200；  
总宽度为 200*2 + 200 * 3 + 200 * 1 = 1400;  
第一项的收缩因子：200 * 2 / 1400 = .2  
item1的最终宽度为200 - 2 * 200 / 6 = 133.33;  
item2的最终宽度为 200 - 3 * 200 / 6 = 100；   
item3的最终宽度为 200 - 1 * 200 / 6 = 166.67；  

