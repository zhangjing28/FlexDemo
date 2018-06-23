# FlexDemo
####1. flex相关概念
**flex容器(flex container)**：对一个DOM元素添加```display:flex```或者```display:inline-flex```可以将其变成一个flex容器(flex container)
**flex 项目(flex item)**： 对于一个flex容器内的所有子元素将变成flex项目
>注： 对于flex容器内的文本节点也将变成flex项目，不连续的文本节点将变成两个不同的flex项目

[相关代码][www.baidu.com]
**主轴(main axis)**:flex容器默认的主轴为水平的
**交叉轴(cross axis)**:flex容器默认的交叉轴为垂直的
>注：当flex容器的flex-direction属性从默认的row变成column时，主轴为垂直的，交叉轴为水平的
####2. flex容器上的属性
**flex-direction**: row | row-reverse | column | column-reverse;
**flex-wrap**: nowrap | wrap | wrap-reverse;
**flex-flow**: flex-driection | flex-wrap;
**justify-content**: flex-start | flex-end | center | space-between | space-around | space-evenly;
**align-items**: flex-start | flex-end | center | baseline | stretch;
**align-content**: flex-start | flex-end | center | space-between | space-around | stretch | space-evenly;

