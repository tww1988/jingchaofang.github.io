
```html
<canvas id="canvas"></canvas>
```

当不指定canvas大小时，默认的width:300px;height:150px。同时不建议用css指定canvas宽高，因为css只能指定画布大小，画布内容，包括分辨率就没法定义。在canvas中直接指定大小，同时也就定义了分辨率，注意：canvas指定的大小时没有单位的。

```javascript
var canvas = getElementById('canvas');
var context = canvas.getContext('2d');
//使用context进行绘制
```
