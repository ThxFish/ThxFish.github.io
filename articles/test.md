# Markdown语法渲染测试

这篇文章用于测试**Markdown语法支持**，包含所有主流 **Markdown 语法**, 用来测试网站不同元素的渲染外观。

---

## 1. 标题测试 (Headings)

### H3: 这是一个三级标题
#### H4: 这是一个四级标题
##### H5: 这是一个五级标题

---

## 2. 文本格式 (Text Formatting)

这是普通文本。
这是 **加粗文本**。
这是 *斜体文本*。
这是 ***加粗兼斜体***。
这是 ~~删除线~~。
这是一段包含 `内联代码` 的文本。

---

## 3. 列表组件 (Lists)

### 无序列表 (Unordered List)
* 苹果 (Apple)
  * 红富士
  * 嘎啦果
* 香蕉 (Banana)
* 橘子 (Orange)

### 有序列表 (Ordered List)
1. 第一步 (Step 1)
2. 第二步 (Step 2)
   1. 子步骤 2.1
   2. 子步骤 2.2
3. 第三步 (Step 3)

### 任务列表 (Task List)
- [x] 完成 Docsify 框架搭建
- [x] 添加 One Dark Pro 代码高亮主题
- [x] 添加明暗主题自动切换
- [ ] 编写第一篇真实知识库文章

---

## 4. 引用块 (Blockquotes)

> 这是一个基础的引用文本块。引用通常用于展示其他人的格言或者重要的提示信息。
>
> 并且它可以包含多段内容。

**嵌套引用：**
> 第一层引用
>> 第二层引用 (Nested)
>>> 第三层引用 (Deeply Nested)

---

## 5. 表格 (Tables)

| 姓名段 (左对齐) | 年龄段 (居中对齐) | 职业段 (右对齐) |
| :--- | :---: | ---: |
| 张三 (Zhang San) | 24 | 前端工程师 (Frontend) |
| 李四 (Li Si) | 30 | 后端架构师 (Backend) |
| 王五 (Wang Wu) | 28 | 产品经理 (PM) |

---

## 6. 代码块 (Code Blocks)

**Python (使用 Consolas 字体与 One Dark Pro 配色)：**
```python
def fibonacci(n):
    """
    斐波那契数列计算函数
    """
    if n <= 1:
        return n
    else:
        return (fibonacci(n-1) + fibonacci(n-2))

print([fibonacci(i) for i in range(10)])
```

**JSON 数据格式：**
```json
{
  "theme": "darklight",
  "name": "清蒸鱼",
  "features": ["latex", "zoom", "copy-code"]
}
```

---

## 7. 公式渲染 (LaTeX)

**行内公式 (Inline Math)：**
质能等价公式 $E = mc^2$ 非常著名，可以在普通段落里完美嵌入。

**块级公式 (Block Math)：**
一元二次方程的求根公式如下：
$$
x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}
$$

复杂的微积分展示：
$$
f(x) = \int_{-\infty}^\infty \hat f(\xi)\,e^{2 \pi i \xi x} \,d\xi
$$

---

## 8. 超链接与图片 (Links & Images)

**超链接：**
* [回到主页 (首页)](/)
* [Docsify 官方网站](https://docsify.js.org/#/)

**图片 (支持点击放大 Zoom-Image)：**
直接单击下面的图片即可体验全屏灯箱放大效果。

![Docsify Logo](https://docsify.js.org/_media/icon.svg)