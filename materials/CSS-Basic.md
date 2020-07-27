## CSS 学习参考

### What is CSS?

CSS, or Cascading Style Sheets,  is a language that web developers use to *style* the HTML content on a web page. CSS can define styles and change the layout and design of a sheet. (colors, font types, font sizes, shadows, images, element positioning, and more)



### Add CSS Stylesheet to HTML Page

**1. Use `<link>` Element** (recommended)

CSS code can be written in its own files to keep it separate from the HTML code. The extension for CSS files is **.css**. These can be linked to an HTML file using a `<link>` tag in the `<head>` section.

The `<link>` element is used to link HTML documents to external resources like CSS files. It commonly uses:

- `href` attribute to specify the URL to the external resource
- `rel` attribute to specify the relationship of the linked document to the current document
- `type` attribute to define the type of content being linked

```html
<head>
  <link href="style.css" type="text/css" rel="stylesheet">
</head>
```



**2. Write CSS in HTML File**

CSS code can be written in an HTML file by enclosing the code in `<style>` tags. Code surrounded by `<style>` tags will be interpreted as CSS syntax.

```css
<head>
  <style>
    h1 {
      color: blue;
    }
  </style>
</head>
```



**3. Inline Style**

CSS styles can be directly added to HTML elements by using the `style` attribute in the element’s opening tag. Each style declaration is ended with a semicolon. Styles added in this manner are known as *inline styles*.

```html
<h2 style="text-align: center;">Centered text</h2>
<p style="color: blue; font-size: 18px;">Blue, 18-point text</p>
```



### CSS Expression

```css
selector {
  property : value
}
```



### CSS Selectors

选择器是一种模式，用于选择需要添加样式的元素

选择器	例子	例子描述	CSS
.class	.intro	选择 class="intro" 的所有元素。	1
#id	#firstname	选择 id="firstname" 的所有元素。	1
*	*	选择所有元素。	2
element	p	选择所有 <p> 元素。	1
element,element	div,p	选择所有 <div> 元素和所有 <p> 元素。	1
element element	div p	选择 <div> 元素内部的所有 <p> 元素。	1
element>element	div>p	选择父元素为 <div> 元素的所有 <p> 元素。	2
element+element	div+p	选择紧接在 <div> 元素之后的所有 <p> 元素。	2
[attribute]	[target]	选择带有 target 属性所有元素。	2
[attribute=value]	[target=_blank]	选择 target="_blank" 的所有元素。	2
[attribute~=value]	[title~=flower]	选择 title 属性包含单词 "flower" 的所有元素。	2
[attribute|=value]	[lang|=en]	选择 lang 属性值以 "en" 开头的所有元素。	2
:link	a:link	选择所有未被访问的链接。	1
:visited	a:visited	选择所有已被访问的链接。	1
:active	a:active	选择活动链接。	1
:hover	a:hover	选择鼠标指针位于其上的链接。	1
:focus	input:focus	选择获得焦点的 input 元素。	2
:first-letter	p:first-letter	选择每个 <p> 元素的首字母。	1
:first-line	p:first-line	选择每个 <p> 元素的首行。	1
:first-child	p:first-child	选择属于父元素的第一个子元素的每个 <p> 元素。	2
:before	p:before	在每个 <p> 元素的内容之前插入内容。	2
:after	p:after	在每个 <p> 元素的内容之后插入内容。	2
:lang(language)	p:lang(it)	选择带有以 "it" 开头的 lang 属性值的每个 <p> 元素。	2
element1~element2	p~ul	选择前面有 <p> 元素的每个 <ul> 元素。	3
[attribute^=value]	a[src^="https"]	选择其 src 属性值以 "https" 开头的每个 <a> 元素。	3
[attribute$=value]	a[src$=".pdf"]	选择其 src 属性以 ".pdf" 结尾的所有 <a> 元素。	3
[attribute*=value]	a[src*="abc"]	选择其 src 属性中包含 "abc" 子串的每个 <a> 元素。	3
:first-of-type	p:first-of-type	选择属于其父元素的首个 <p> 元素的每个 <p> 元素。	3
:last-of-type	p:last-of-type	选择属于其父元素的最后 <p> 元素的每个 <p> 元素。	3
:only-of-type	p:only-of-type	选择属于其父元素唯一的 <p> 元素的每个 <p> 元素。	3
:only-child	p:only-child	选择属于其父元素的唯一子元素的每个 <p> 元素。	3
:nth-child(n)	p:nth-child(2)	选择属于其父元素的第二个子元素的每个 <p> 元素。	3
:nth-last-child(n)	p:nth-last-child(2)	同上，从最后一个子元素开始计数。	3
:nth-of-type(n)	p:nth-of-type(2)	选择属于其父元素第二个 <p> 元素的每个 <p> 元素。	3
:nth-last-of-type(n)	p:nth-last-of-type(2)	同上，但是从最后一个子元素开始计数。	3
:last-child	p:last-child	选择属于其父元素最后一个子元素每个 <p> 元素。	3
:root	:root	选择文档的根元素。	3
:empty	p:empty	选择没有子元素的每个 <p> 元素（包括文本节点）。	3
:target	#news:target	选择当前活动的 #news 元素。	3
:enabled	input:enabled	选择每个启用的 <input> 元素。	3
:disabled	input:disabled	选择每个禁用的 <input> 元素	3
:checked	input:checked	选择每个被选中的 <input> 元素。	3
:not(selector)	:not(p)	选择非 <p> 元素的每个元素。	3
::selection	::selection	选择被用户选取的元素部分。	3

- **标签选择器 **（h1, p, div ...）

  ```css
  /* Selects all p elements */
  p {
  }
  ```

- **类选择器** （can be **reusable** and applied to many elements）

  ```css
  /* Selects all elements with class="column" */
  .column {
  }
  ```

- **ID选择器** （should be **unique** and used to style only a single element）

  ```css
  /* Selects element with id="first-item" */
  #first-item {
  } 
  ```

- 伪类选择器 （a:hover ...）

  ```css
  a:hover {
  }
  ```

- 伪元素选择器  

  ```css
  /* selects the first line of P element */
  p::first-line {
  }
  ```

- 分组选择器 

  ```css
  /* the text for both `h1` and `h2` is set to red. */
  h1, h2 {
    color: red;
  }
  ```

- 子选择器 （ .header > h1 ）

- 包含（后代）选择器 （ .header  h1 ）

- 属性选择器 （ input[disable] ）

- 通配选择器 （ * ）



### CSS 属性书写顺序 （参考）

1. 位置属性 （position, top, right, z-index, display ...）
2. 大小 (width, height, padding, margin)
3. 文字系列 (font, color, text-align, line-height, letter-spacing ...)
4. 背景 (background, border ...)
5. 其他 (animation, transition ...)



### CSS Cascade Order (层叠顺序)

详细介绍：http://w3help.org/zh-cn/kb/005/#header_3

1.对于目标媒介类型 (media type)，找到存有疑问的元素和属性的所有声明。如果相关联的选择器匹配存有疑问的元素，并且目标媒介匹配包含声明并且和样式表的路径在所有链接上达到一致的 @media 规则中所有的媒介列表。
2.根据 CSS 样式的来源和重要性(是否含 !important )，给出了优先级的升序排列：
    a.用户端声明( UA declarations )
    b.一般用户声明( user normal declarations )
    c.一般作者声明( author normal declarations )
    d.加了 '!important' 的作者声明( author important declarations )
    e.加了 '!important' 的用户声明( user important declarations )
3.拥有相同重要性和来源的规则，按照 CSS specificity 来排序。此处，需要注意一下层叠顺序和选择器的特殊性1的关系。 选择器的特殊性是在相同来源，相同重要性的规则之间判定最终哪个规则会起作用。 比如， 同是开发者自己定义的样式，并且，没有使用 "!important" 规则，这样的样式才可以计算特殊性。
4.最后，根据先后次序来排列：如果两条规则具有相同的权重，相同的来源和相同的选择器特殊性，则后出现的规则超越先出现的规则。 引入的样式表( @import )中的规则被认为出现在样式表本身的所有规则之前。



### CSS Selector's Specificity （选择器的权重计算）

The most specific selector type is the **ID selector**, followed by **class selectors**, followed by **tag selectors**.

The CSS `!important` rule is used on declarations to override any other declarations for a property and ignore selector specificity. However, generally it is good to avoid using `!important` as bad practice.

选择器特殊性的计算规则: http://w3help.org/zh-cn/kb/005/#header_4

*             {}  /* a=0 b=0 c=0 d=0 -> specificity = 0,0,0,0 */
li            {}  /* a=0 b=0 c=0 d=1 -> specificity = 0,0,0,1 */
li:first-line {}  /* a=0 b=0 c=0 d=2 -> specificity = 0,0,0,2 */
ul li         {}  /* a=0 b=0 c=0 d=2 -> specificity = 0,0,0,2 */
ul ol+li      {}  /* a=0 b=0 c=0 d=3 -> specificity = 0,0,0,3 */
h1 + *[rel=up]{}  /* a=0 b=0 c=1 d=1 -> specificity = 0,0,1,1 */
ul ol li.red  {}  /* a=0 b=0 c=1 d=3 -> specificity = 0,0,1,3 */
li.red.level  {}  /* a=0 b=0 c=2 d=1 -> specificity = 0,0,2,1 */
#x34y         {}  /* a=0 b=1 c=0 d=0 -> specificity = 0,1,0,0 */
style=""          /* a=1 b=0 c=0 d=0 -> specificity = 1,0,0,0 */

### CSS inheritance  (继承)

部分属性可以被子元素继承



### CSS 盒模型 （box model）

http://w3help.org/zh-cn/kb/006/

https://developer.mozilla.org/zh-CN/docs/Web/CSS/CSS_Box_Model/Introduction_to_the_CSS_box_model



## 调试 CSS 

https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Building_blocks/Debugging_CSS
