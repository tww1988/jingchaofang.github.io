
```html
<canvas id="canvas" width="100" height="100">当前浏览器不支持Canvas，请更换浏览器后再试</canvas>
```

当不指定canvas大小时，默认的width:300px;height:150px。同时不建议用css指定canvas宽高，因为css只能指定画布大小，画布内容，包括分辨率就没法定义。在canvas中直接指定大小，同时也就定义了分辨率，注意：canvas指定的大小时没有单位的。

```javascript
var canvas = getElementById('canvas');
var context = canvas.getContext('2d');
//使用context进行绘制
```
canvas是一种状态绘图，先进行绘图设置，再进行绘图。
canvas进行绘图时是基于状态的，先规定状态，再执行绘制的动作

var canvas = document.getElementById("canvas");
var context = canvas.getContext("2d");

context.beginPath();
context.moveTo(100,100);//起笔移动到该坐标
context.lineTo(700,700);//连接上一个坐标，画出连接线
context.fillStyle="red";//填充块的样式
context.fill(); // 绘制填充颜色块
context.lineWidth = 8;//线条的宽度
context.strokeStyle="red";//线条的样式
context.stroke();//绘制以上图案，绘制线条
context.closePath();

context.beginPath();
context.moveTo(200,100);
context.lineTo(700,600);
context.strokeStyle="black";
context.stroke();
context.closePath();


context.arc(centerx, centery, radius, startingAngle, endingAngle, anticlockwise = false)；
context.arc(圆心x坐标，圆心y坐标，半径的值，从哪一个弧度值为开始，到哪一个弧度值结束，可选参数：是顺时针方向绘制（false） 还是 逆时针方向绘制（true）)

beginPath与closePath并不一定要成对出现，beginPath是重新绘制路径，closPath结束当前的路径，如果当前的路径不封闭的话，closePath自动封闭该路径
