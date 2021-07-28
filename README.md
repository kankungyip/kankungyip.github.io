## 一些用法

### 一般引用
```
{% blockquote [author[, source]] [link] [source_link_title] %}
content
{% endblockquote %}

{% quote [author[, source]] [link] [source_link_title] %}
content
{% endquote %}
```

#### 引用书摘
```
{% blockquote David Levithan, Wide Awake %}
Do not just seek happiness for yourself. Seek happiness for all. Through kindness. Through mercy.
{% endblockquote %}
```

#### 引用 Twitter 内容
```
{% blockquote @DevDocs https://twitter.com/devdocs/status/356095192085962752 %}
NEW: DevDocs now comes with syntax highlighting. http://devdocs.io
{% endblockquote %}
```

#### 引用网络文摘
```
{% blockquote Seth Godin http://sethgodin.typepad.com/seths_blog/2009/07/welcome-to-island-marketing.html Welcome to Island Marketing %}
Every interaction is both precious and an opportunity to delight.
{% endblockquote %}
```

### 带颜色引用
```
{% colorquote [info|success|warning|danger] %}
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Pellentesque hendrerit lacus ut purus iaculis feugiat. Sed nec tempor elit, quis aliquam neque. Curabitur sed diam eget dolor fermentum semper at eu lorem.
{% endcolorquote %}
```

### 评论引用
```
{% pullquote [CSS class] %}
content
{% endpullquote %}
```

### 代码块
```
{% codeblock [title] [lang:language] [url] [link text] %}
code snippet
{% endcodeblock %}
```
或
````
``` [language] [title] [url] [link text]
code snippet
```
````

### jsFiddle
```
{% jsfiddle shorttag [tabs] [skin] [width] [height] %}
```

### Gist
```
{% gist gist_id [filename] %}
```

### iframe
```
{% iframe url [width] [height] %}
```

### 图片
```
{% img [class names] /path/to/image [width] [height] [title text [alt text]] %}
```

### 外部代码文件
文件保存在 `source/downloads/code` 文件夹
```
{% include_code [title] [lang:language] path/to/file %}
``` 

### 外部打开链接
```
{% link text url [external] [title] %}
```

### YouTube
```
{% youtube video_id %}
```

### Vimeo
```
{% vimeo video_id %}
```

### 引用文章
```
{% post_path slug %}
{% post_link slug [title] %}
```

### 引用资源
```
{% asset_path slug %}
{% asset_img slug [title] %}
{% asset_link slug [title] %}
```

### Raw
```
{% raw %}
content
{% endraw %}
```

### 展开文章
```
<!-- more -->
```

### 画廊
```
{% gallery %}
![Elephant](/hexo-theme-minos/gallery/animals/elephant.jpeg)
![Dog](/hexo-theme-minos/gallery/animals/dog.jpeg)
![Birds](/hexo-theme-minos/gallery/animals/birds.jpeg)
![Cat](/hexo-theme-minos/gallery/animals/cat.jpeg)
![Fox](/hexo-theme-minos/gallery/animals/fox.jpeg)
![Horse](/hexo-theme-minos/gallery/animals/horse.jpeg)
![Leopard](/hexo-theme-minos/gallery/animals/leopard.jpeg)
{% endgallery %}
```

### 视频
```
{% owl youtube youtube_id %}
{% owl niconico niconico_id [type] %}
{% owl bilibili bilibili_id [page] [height] [width] %}
{% owl vimeo vimeo_id %}
{% owl tudou tudou_id %}
{% owl youku youku_id [height] [width] %}
{% owl tencent tencent_id [height] [width] %}
{% owl ted ted_id [lang] %}
```

### 拼音
```
{% ruby Base|top %}
```

### 二维码
```
{% qrcode data [alt:text] [title:text] [class] %}
```

### micro:bit 代码
```
{% microbit ID %}
```

### 脑图
```
{% markmap height %}
# Testa
## test1
## test2
# Testb
## test1
## test2
{% endmarkmap %}
```

### 流程图
```flow
st=>start: Start|past:>http://www.google.com[blank]
e=>end: End:>http://www.google.com
op1=>operation: My Operation|past
op2=>operation: Stuff|current
sub1=>subroutine: My Subroutine|invalid
cond=>condition: Yes
or No?|approved:>http://www.google.com
c2=>condition: Good idea|rejected
io=>inputoutput: catch something...|request

st->op1(right)->cond
cond(yes, right)->c2
cond(no)->sub1(left)->op1
c2(yes)->io->e
c2(no)->op2->e
```

### 泳道图
```sequence
Alice->Bob: Hello Bob, how are you?
Note right of Bob: Bob thinks
Bob-->Alice: I am good thanks!
```

### 数学公式
#### TeX 和 LaTeX
```
When $a \ne 0$, there are two solutions to \\(ax^2 + bx + c = 0\\) and they are
$$x = {-b \pm \sqrt{b^2-4ac} \over 2a}.$$
```

#### MathML
```
When<math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi><mo>&#x2260;</mo><mn>0</mn></math>, there are two solutions to <math xmlns="http://www.w3.org/1998/Math/MathML"><mi>a</mi><msup><mi>x</mi><mn>2</mn></msup><mo>+</mo> <mi>b</mi><mi>x</mi><mo>+</mo> <mi>c</mi> <mo>=</mo> <mn>0</mn></math> and they are
<math xmlns="http://www.w3.org/1998/Math/MathML" display="block"><mi>x</mi> <mo>=</mo><mrow><mfrac><mrow><mo>&#x2212;</mo><mi>b</mi><mo>&#x00B1;</mo><msqrt><msup><mi>b</mi><mn>2</mn></msup><mo>&#x2212;</mo><mn>4</mn><mi>a</mi><mi>c</mi></msqrt></mrow><mrow> <mn>2</mn><mi>a</mi> </mrow></mfrac></mrow><mtext>.</mtext></math>
```

#### AsciiMath
```
When \`a != 0\`, there are two solutions to \`ax^2 + bx + c = 0\` and they are<p style="text-align:center">\`x = (-b +- sqrt(b^2-4ac))/(2a) .\`</p>
```
