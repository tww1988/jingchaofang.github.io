前言
----

使用XML描述的矢量文件，位图基于颜色的描述，矢量图基于数学的描述

W3C标准（http://www.w3.org/TR/SVG11/）

http://caniuse.com/#cats=SVG

http://paletton.com/

http://myst729.github.io/bezier-curve/

http://jsbin.com/

https://github.com/consoles/front-end/tree/master/html5/SVG

https://github.com/consoles/front-end

http://jsbin.com/lekob/5/edit?html,output

SVG动画
http://www.w3.org/TR/SVG/animate.html
http://www.zhangxinxu.com/wordpress/?p=4333


http://www.zhangxinxu.com/wordpress/2014/07/introduce-svg-sprite-technology/   

http://nethub2.iteye.com/blog/2147988   svg转png，jpg，pdf

使用方式
--------

SVG的使用方式：直接浏览器打开、在HTML中使用img标签引用、直接在HTML使用SVG标签、作为CSS背景


基本图形和属性
----------------
基本图形：<rect>(矩形) <circle>(圆形) <ellipse>(椭圆) <line>(直线) <polyline>(折线) <polygon>(多边形)
基本属性：fill(填充色), stroke(描边色), stroke-width(描边宽度), transform(旋转)

<rect>
• x 
• y 
• width  • height  • rx 
• ry


创建图形的接口：document.createElementNS(ns,TagName)
[SVG拥有独立的namespace，故使用js创建元素时使用createElementNS（ns,TagName）接口]
添加图形的接口：element.appendChile(childElement)
设置/获取属性：element.setAttribute(name,value)
element.getAttribute(name)
