# Narrative-Visualization-Project
2024-2025 studio 1 project

## 如何添加新章节

### 1. 添加背景图片
在`main`标签内的背景图片容器组中添加新的背景图片：
```html
<div class="fixed inset-0 w-full h-full opacity-0 transition-opacity duration-1000">
    <img src="img/your-background.png" class="w-full h-full object-cover" alt="背景图片">
</div>
```

### 2. 添加导航链接
在导航菜单中添加新章节的链接：
```html
<div class="hidden md:flex space-x-8">
    <!-- 在这里添加新的导航链接 -->
    <a href="#your-section" class="hover:text-custom transition-colors">你的章节</a>
</div>
```

### 3. 创建章节内容
在`main`标签内添加新的section元素：
```html
<section id="your-section" class="flex flex-col items-center justify-center">
    <div style="height: 50vh;"></div>
    <!-- 添加标题 -->
    <img class="line_new line" src="img/your-title.svg" alt="章节标题" style="width: 40vw; opacity: 0;">
    
    <!-- 添加文本内容 -->
    <div class="line_new line" style="text-align: center; opacity: 0;">
        你的文本内容
    </div>
    
    <!-- 添加动画效果 -->
    <script>
        (function () {
            var controller = new ScrollMagic.Controller();
            var tween = gsap.timeline();
            tween.fromTo(".line_new", 
                { opacity: 0 }, 
                { opacity: 1, duration: 1, stagger: 0.5 }
            )
            .to(".line_new", 
                { opacity: 0, duration: 1, stagger: 0.5, delay: 1 }, 
                1
            );
            
            var scene = new ScrollMagic.Scene({
                triggerElement: "#your-section",
                duration: 1800,
                offset: 300
            })
            .setTween(tween)
            .addIndicators()
            .addTo(controller);
        })();
    </script>
    
    <div style="height: 100vh;"></div>
</section>
```

### 4. 样式说明
- 文本样式类：
  ```css
  .line {
      color: #FFF;  /* 白色文本 */
      font-family: "Alibaba PuHuiTi 2.0";
      font-size: 30px;
      font-weight: 70;
      letter-spacing: 10px;
  }
  
  .line-black {
      color: #000;  /* 黑色文本 */
      /* 其他样式同上 */
  }
  ```

### 5. 注意事项
1. 确保每个section的ID唯一
2. 背景图片需按顺序添加，与section顺序对应
3. 动画类名(如`line_new`)需要唯一，避免与其他章节冲突
4. 建议每个章节保持100vh的最小高度
5. 可以使用`style="height: 50vh;"`来调整内容间距

### 6. 开发建议
- 使用Chrome开发者工具检查动画效果
- 通过调整`duration`和`offset`参数来优化滚动体验
- 可以使用`addIndicators()`来显示动画触发点，方便调试

