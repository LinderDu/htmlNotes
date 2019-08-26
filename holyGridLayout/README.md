# 圣杯布局

圣杯布局

* 两侧宽度固定，中间宽度自适应
* 中间部分在DOM结构上优先，以便先行渲染
* 允许三列中的任意一列成为最高列

## HTML 结构

```html
<header>
  Header
</header>

<div id="continer">
  <div id="content">content</div>
  <div id="left">left</div>
  <div id="right">right</div>
</div>

<footer>
  footer
</footer>
```


## CSS 实现

```css
header,
footer {
  background-color: rgb(212, 212, 212);
  height: 40px;
  line-height: 40px;
}

#continer {
  padding: 0 200px;
}

#left,
#content,
#right {
  float: left;
  height: 80px;
  line-height: 80px;
}

#content {
  width: 100%;
  background-color: burlywood
}

#left,
#right {
  width: 200px;
  background-color: darkolivegreen;
  position: relative;
  top: 0;
}

#left {
  margin-left: -100%;
  left: -200px;
}

#right{
  margin-right: -200px;
  right: 0;
}

footer {
  clear: both;
}
```