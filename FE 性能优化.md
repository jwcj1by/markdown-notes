# FE 性能优化
Tags: FE

---

> ### CSS

```
 1. OOCSS object-oriented css 面向对象的CSS
```

```
 2. 慎重选择高消耗的样式
    box-shadows
    border-radius
    transparency
    transforms
    CSS filters（高能耗）
```

```
 3. 避免过分重排, 当发生重排的时候，浏览器需要重新计算布局位置与大小
    width
    height
    padding
    margin
    display
    border-width
    position
    top
    left
    right
    bottom
    font-size
    float
    text-align
    overflow-y
    font-weight
    overflow
    font-family
    line-height
    vertical-align
    clear
    white-space
    min-height
```

```
 4. 正确使用 Display 的属性
     Display 属性会影响页面的渲染，请合理使用。
        display: inline后不应该再使用 width、height、margin、padding 以及 float；
        display: inline-block 后不应该再使用 float；
        display: block 后不应该再使用 vertical-align；
        display: table-* 后不应该再使用 margin 或者 float；
```

```
5. 提升 CSS 选择器性能
```

```
5. 不滥用 Float
```

```
5. 不滥用 Float
```

```
5. 多利用硬件能力，如通过 3D 变形开启 GPU 加速
```



> ### javascript

```
object-oriented css 面向对象的CSS
```




