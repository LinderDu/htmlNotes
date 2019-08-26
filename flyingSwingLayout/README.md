# 双飞翼布局

双飞翼布局

* 两侧宽度固定，中间宽度自适应
* 中间部分在DOM结构上优先，以便先行渲染
* 允许三列中的任意一列成为最高列

## HTML 结构

```html
<header class="header">header</header>
<section class="container">
  <section class="contentContainer">
    <div class="content">content</div>
  </section>
  <section class="left">left</section>
  <section class="right">right</section>
</section>
<footer class="footer">footer</footer>
```


## CSS 实现

```css
.header,
.footer {
  background-color: bisque;
  height: 40px;
  line-height: 40px;
}

.container {
  margin: 0 auto;
  width: 100%;
}

.contentContainer {
  float: left;
  width: 100%;
  padding: 0 10px;
  box-sizing: border-box;
}

.content {
  margin-left: 190px;
  margin-right: 290px;
  background-color: #c15716;
}

.left {
  width: 190px;
  float: left;
  background-color: #289ad2;
  margin-left: -100%;
}

.right {
  float: left;
  background-color: #abc444;
  width: 290px;
  margin-left: -290px;
}

.footer {
  clear: both;
}
```

## 双飞翼布局对比圣杯布局

双飞翼布局还是圣杯布局都是实现同样的效果

圣杯布局通过父容器的左右边边距和两个从列`position:relative`实现，圣杯布局从代码结构上看更加直观和清晰

双飞翼通过`margin-left`实现定位，双飞翼从代码上来看更加简洁