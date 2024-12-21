# Narrative-Visualization-Project
2024-2025 studio 1 project

## 项目使用说明

该项目旨在通过叙事可视化的方式展示内容。用户可以通过滚动页面来查看不同章节的内容，每个章节都包含背景图片、文本和动画效果。

### 章节框架

本项目的章节框架如下：

1. **介绍章节**：介绍辣条的起源与发展，揭示其背后的故事和人们的情感联系。
  - **内容概述**：本章节将介绍辣条的起源、发展历程以及其在平江县的文化意义。通过对辣条的探索，我们将揭示其背后的故事和人们的情感联系。
2. **起源章节 (CHAPTER 1)**：诞生于洪水的滋味，讲述辣条的历史背景和文化意义。
  - **内容概述**：本章节将详细讲述辣条的历史背景，特别是其在洪水后的诞生过程，以及如何在困境中找到生存之道。
3. **帮扶章节 (CHAPTER 2)**：修一条通往外面的路，描述辣条企业在发展过程中遇到的挑战与解决方案。
  - **内容概述**：本章节将探讨辣条企业在发展过程中面临的运输和成本问题，以及如何通过修路来解决这些问题，促进企业的快速发展。
4. **约束章节 (CHAPTER 3)**：分析辣条产业在发展过程中所面临的各种约束因素。
  - **内容概述**：本章节将讨论辣条产业在生产、销售和市场推广中遇到的限制因素，包括政策、市场需求和资源配置等。
5. **转型章节 (CHAPTER 4)**：探讨辣条企业如何进行转型以适应市场变化。
  - **内容概述**：本章节将分析辣条企业在面对市场竞争和消费者需求变化时，如何进行产品创新和市场策略调整。
6. **回顾章节 (CHAPTER 5)**：总结辣条产业的发展历程和经验教训。
  - **内容概述**：本章节将回顾辣条产业的发展历程，分析成功与失败的案例，提炼出可供借鉴的经验和教训。
7. **总结章节 (CHAPTER 6)**：展望辣条产业的未来发展方向。
  - **内容概述**：本章节将讨论辣条产业的未来发展趋势，包括市场前景、技术创新和消费者行为变化等。
### 如何添加新章节

#### 1. 添加背景图片
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

## 后续扩展计划

1. **增加互动性**：计划在未来的版本中添加更多的互动元素，例如用户输入和选择，以增强用户体验。
2. **多语言支持**：将支持多种语言，以便更广泛的用户群体能够使用该项目。
3. **优化性能**：将持续优化页面加载速度和动画性能，确保在各种设备上的流畅体验。
4. **内容更新**：定期更新内容和章节，以保持项目的新鲜感和吸引力。
5. **用户反馈**：收集用户反馈，了解用户需求，以便在后续版本中进行改进。




