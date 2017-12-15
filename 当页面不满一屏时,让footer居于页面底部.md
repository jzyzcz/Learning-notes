# 当页面不足一个屏幕时,让`footer`位于页面的底部
---
> 在写页面的时候,如果页面的内容不够多,会导致页面的高度不足一个屏幕,

> 这个时候`footer`按照正常定位就不是在页面的底部,会显得比较的难看.  

> 如果用定位的方式把`footer`的位置写死,当页面的高度超过一屏的时候,又得去改变它.

> 这里有两种方法,一种是通过js,一种是通过css

## 代码如下:

```javascript
$(function () {
    function footerLocation() {
        $('.footer').removeClass('footerToBottom');
        let documentHeight = document.body.scrollHeight, // 网页正文的高度
            winHeight = window.innerHeight; // 可视窗口的高度,不包括浏览器顶部工具栏
        /* 当网页正文的高度 < 窗口的可视高度时,就让footer位于页面的底部 */
        if (!(documentHeight > winHeight)) {
            $('.footer').addClass('footerToBottom');
        }
    }
    footerLocation();
    $(window).resize(footerLocation()); // 当窗口大小变化时,调用函数
})
```


[参考答案地址-](https://segmentfault.com/a/1190000004453249)


 #### 另外一个方法
 
> 思路:就是给页面的主体赋予一个最小高度,最小高度=页面的高度-footer的高度

> 假设footer的高度的是100px,那么代码就是:
 
 ```css
 .main-wrapper{
    min-height: calc(100vh - 100px)
}
```
> 注意这个方法只适用于移动端.


#### 2017年12月14日
