## 一. CSS的语法研究



### CSS2.1的语法

- [Grammar of CSS 2.1](https://www.w3.org/TR/CSS21/grammar.html#q25.0)

- - [CSS2.1整体目录](https://www.w3.org/TR/2011/REC-CSS2-20110607/#minitoc)

- - - [1 About the CSS 2.1 Specification](https://www.w3.org/TR/2011/REC-CSS2-20110607/about.html#q1.0)
    - [2 Introduction to CSS 2.1](https://www.w3.org/TR/2011/REC-CSS2-20110607/intro.html#q2.0)
    - [3 Conformance: Requirements and Recommendations](https://www.w3.org/TR/2011/REC-CSS2-20110607/conform.html#q3.0)
    - [4 Syntax and basic data types](https://www.w3.org/TR/2011/REC-CSS2-20110607/syndata.html#q4.0)(语法和基本的数据结构)
    - [5 Selectors](https://www.w3.org/TR/2011/REC-CSS2-20110607/selector.html#q5.0)(选择器)
    - [6 Assigning property values, Cascading, and Inheritance](https://www.w3.org/TR/2011/REC-CSS2-20110607/cascade.html#q6.0)(属性的值，级联，继承)
    - [7 Media types](https://www.w3.org/TR/2011/REC-CSS2-20110607/media.html#q7.0)(媒体类型)
    - [8 Box model](https://www.w3.org/TR/2011/REC-CSS2-20110607/box.html#box-model)(排版相关-盒子模型)
    - [9 Visual formatting model](https://www.w3.org/TR/2011/REC-CSS2-20110607/visuren.html#q9.0)(排版相关-**[BFC](https://www.w3.org/TR/2011/REC-CSS2-20110607/visuren.html#block-formatting)**:正常流布局中的一个概念)
    - [10 Visual formatting model details](https://www.w3.org/TR/2011/REC-CSS2-20110607/visudet.html#q10.0)(排版相关)
    - [11 Visual effects](https://www.w3.org/TR/2011/REC-CSS2-20110607/visufx.html#q11.0)(渲染相关)
    - [12 Generated content, automatic numbering, and lists](https://www.w3.org/TR/2011/REC-CSS2-20110607/generate.html#generated-text)(list的一些特殊处理)
    - [13 Paged media](https://www.w3.org/TR/2011/REC-CSS2-20110607/page.html#the-page)(page)
    - [14 Colors and Backgrounds](https://www.w3.org/TR/2011/REC-CSS2-20110607/colors.html#q14.0)(颜色与背景)
    - [15 Fonts](https://www.w3.org/TR/2011/REC-CSS2-20110607/fonts.html#q15.0)(渲染相关-字体)
    - [16 Text](https://www.w3.org/TR/2011/REC-CSS2-20110607/text.html#q16.0)(渲染相关-文本)
    - [17 Tables](https://www.w3.org/TR/2011/REC-CSS2-20110607/tables.html#q17.0)
    - [18 User interface](https://www.w3.org/TR/2011/REC-CSS2-20110607/ui.html#q18.0)(交互)
    - [CSS产生式](https://www.w3.org/TR/2011/REC-CSS2-20110607/grammar.html#q25.0)

- [CSS Syntax Module Level 3](https://www.w3.org/TR/css-syntax-3/)





### CSS 总体结构

- @charset(基本过时了，因为在写CSS时都要写成ASCII兼容,意思是不会用到超过127的字符，凡是超过127的字符都会用转义去处理)
- @import
- rules

- - @media
  - @page
  - rule(平时用的最多)



**CSS  主要分为 带@的规则和 一般的规则**



#### CSS产生式简介

```
CDO  CDC  是历史包袱， 不需要重视

CDO :  <!--

CDC :   -->
```

## 二. CSS @规则的研究



[at-rules--MDN](https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule)



- [@charset](https://www.w3.org/TR/css-syntax-3/) ：

- - https://www.w3.org/TR/css-syntax-3/#charset-rule

- [@import ](https://www.w3.org/TR/css-cascade-4/)：

- - https://www.w3.org/TR/css-cascade-4/#at-ruledef-import

- [**@media**](https://www.w3.org/TR/css3-conditional/) **：**

- - [**https://www.w3.org/TR/css3-conditional/#at-media**](https://www.w3.org/TR/css3-conditional/#at-media)

- [@page](https://www.w3.org/TR/css-page-3/) ：

- - https://www.w3.org/TR/css-page-3/#at-ruledef-page

- [@counter-style](https://www.w3.org/TR/css-counter-styles-3/) ：

- - https://www.w3.org/TR/css-counter-styles-3/#the-counter-style-rule

- [@keyframes](https://www.w3.org/TR/css-animations-1/) ：

- - https://www.w3.org/TR/css-animations-1/#at-ruledef-keyframes

- [@fontface](https://www.w3.org/TR/css-fonts-3/) ：

- - https://www.w3.org/TR/css-fonts-3/#at-font-face-rule

- [**@supports**](https://www.w3.org/TR/css3-conditional/) **：**

- - [**https://www.w3.org/TR/css3-conditional/#at-supports**](https://www.w3.org/TR/css3-conditional/#at-supports)

- [@namespace](https://www.w3.org/TR/css-namespaces-3/) ：

- - https://www.w3.org/TR/css-namespaces-3/#declaration





这里的每一种 @规则背后，都是一组 CSS 的知识。



兼容性问题

1. postCSS  不是解决兼容问题的万灵药
2. 主要解决兼容性问题不是技术，因为技术与浏览器或手机的更新换代是很快的。  因此，主要是需要快速发现兼容性问题并快速解决
3. rem方案(引入一些运行时的JS代码进行处理)是业界提出较早的方案，目前winter老师建议使用  **VW方案(百分比宽度)来解决兼容性问题**
4. 所有的兼容性处理并不是 挨个的所有元素都使用，不同的元素有不同的语义。比如：

1. 1. 文字

不可能所有的文字都进行缩放，文字是有点阵的位置的.

不同的字体采用的文字大小可能都是不一样的.

文字的兼容性解决方案  应该是 让文字按照正常流去排， 而不是让文字随着屏幕的缩放而保持在一排

1. 真正去解决兼容性问题是 一个规则，  而不是一个单位，单位只是去解决一些关键问题
2. 兼容性问题推荐文章-http://www.html-js.com/article/2402
3. **winter老师推荐的 兼容性最佳实践:  将rem替换为vw**
4. **还原设计图的时候，可以先写成px,然后处理成vw**







## 三. CSS普通规则的结构

### CSS规则

- Selector

- - https://www.w3.org/TR/selectors-3/
  - https://www.w3.org/TR/selectors-4/

- Key

- - Properties
  - Variables-https://www.w3.org/TR/css-variables/

- Value

- - https://www.w3.org/TR/css-values-4/





## 四. 初建CSS知识体系

### 实验:收集标准

```javascript
var lis = document.getElementById("container").children


var result = [];


for(let li of lis) {
    if(li.getAttribute('data-tag').match(/css/))
        result.push({
            name:li.children[1].innerText,
            url:li.children[1].children[0].href
        })
}
console.log(result)
```

### 实验:收集CSS属性相关标准

```javascript
let iframe = document.createElement("iframe");
document.body.innerHTML = "";
document.body.appendChild(iframe);




function happen(element, event){
    return new Promise(function(resolve){
        let handler = () => {
            resolve();
            element.removeEventListener(event, handler);
        }
        element.addEventListener(event, handler);
    })
}




void async function(){
    for(let standard of standards) {
        iframe.src = standard.url;
        console.log(standard.name);
        await happen(iframe, "load");
    }
}();
```

