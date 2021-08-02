# Markdown基本语法归纳总结

*初步完成于2021年8月2日16点40分。*

## 预先说明

### 技术说明

1. 本文中的所有英文术语，如果可以，均使用复数形式。
2. 本文中的Markdown代码中的使用`{ }`扩起的成分大多属于可以任意填入的内容（“参数”），其中被扩起的文字属于对可任意填入的内容的描述性名称（“参数名称”）。用于**通用格式**的讲解中。
3. 本文中的Markdown代码中的`...`表示有规律的省略，用于**通用格式**的讲解中。
4. 本文中的Markdown代码中的`{sp}`表示空格（因为空格不可见）。
5. 本文中的Markdown代码中的`{ }`若包含几个用空格分隔的成分，表示该处应当出现列举的几个成分之一。

### 非技术说明

i. 本文的写作意图并非给公众看的教程，而只是笔者写给自己的Markdown知识点归纳。故**可能存在错误**，且**笔者对这些错误不负责**。读者阅读时**请保持谨慎**，本文**仅供参考**。
ii. 本文主要整理自[Markdown基本语法](https://markdown.com.cn/basic-syntax/)，少数整理自[Markdown扩展语法](https://markdown.com.cn/extended-syntax/)。

## I. 标题（headings）

### 1. 标题

使用1\~6个`#`来指定标题。井号数量对应不同级别的标题（1\~6），`#`越多，标题级别数越高，标题显示得越小。

#### 通用格式

`#...# {heading}`（整行）

其中`#`数量在1~6之间。

#### 示例

```
# Heading L1
## Heading L2
#### Heading L4
###### Heading L6
```

#### 效果

> # Heading L1
> ## Heading L2
> #### Heading L4
> ###### Heading L6

⚠ **`#...#`和`{heading}`之间最好留有空格（通常为1个）。**

### 1a. 标题 \[alternative\]

使用任意数量的`=`或`-`，来分别表示一级、二级标题。它们分别相当于1、2个`#`。

#### 通用格式

```
{heading_lev_1}
=...=

{heading_lev_2}
-...-
```

#### 效果

> {heading_lev_1}
> ==

> {heading_lev_2}
> --

## II. 段落（paragraphs）

### 3. 段落

在两段文字之间加入至少1个空行，即可将它们分为不同段落。

#### 通用格式

```
{para 1}

{para 2}
```

#### 效果

> `{para 1}`
>
> `{para 2}`

⚠ **不要用Space/Tab缩进段落。**

## III. 换行（line breaks）

### 4. 换行

在某一行的末尾添加至少2 Spaces，则代码中的下一行内容将会换行显示。

#### 通用格式

```
{line 1}{sp}...{sp}
{line 2}
```

其中`{sp}`至少2个。

#### 效果

> `{line 1}`  
> `{line 2}`

## IV. 强调（emphasis）

### 5~7. 粗体（bold）、斜体（italic）和粗斜体

分别使用一对`*`（或`_`）、`**`（或2`_`）和`***`（或3`_`）对文本进行倾斜、加粗或叠加两种效果。

#### 通用格式

```
*{text_italic}*
_{text_italic}_
**{text_bold}**
__{text_bold}__
***{text_italic_bold}***
___{text_italic_bold}___
```

#### 效果

> *{text_italic}*
> _{text_italic}_
> **{text_bold}**
> __{text_bold}__
> ***{text_italic_bold}***
> ___{text_italic_bold}___


⚠ **开始处的`*`后面不要有空格。下划线表示法可能会比较tricky，不熟练者建议回避使用。晚点再来整理\[TODO\]。**

⚠ **下划线疑似只能使用HTML代码来表达：`<u>{text_underlined}</u>`。**

## V. 块引用（blockquotes）

### 8. 块引用（以下简称为“引用”）

在行首使用`>`来创建引用。

#### 基本格式

`> {quote}`（整行）

#### 效果

>> `{quote}`

ℹ **本文中，*效果*演示有一层固有的引用效果。务必将这层固有引用效果与这里实际上要演示的引用效果区分清楚。下同。**

### 8.a. 引用连续性保持：多段引用

在原先的空行处加入`>`，即可保持引用的连续性。

#### 基本格式

```
> {para 1}
>
> {para 2}
```

#### 效果

>> `{para 1}`
>> 
>> `{para 2}`

### 8.b. 嵌套引用

引用可以嵌套。交替使用数量不等的`>`即可实现嵌套引用，并且`>`的数量决定嵌套层级。

#### 演示

```
Martin Luther King said,
> Washington said firmly,
>> All men are born equal.
```

#### 效果

> Martin Luther King said,
>> Washington once said,
>>> All men are born equal.

ℹ **引用可以带有其他Markdown元素，如强调和列表等。**

## VI. 列表（lists）

### 9. 有序列表（ordered lists？）

在想要纳入列表的每一行开始处加上一个数字和、一个`.`和1个Space，即可创建一个列表。

#### 通用格式

```
{num_1}. {item_1}
{num_2}. {item_2}
...
{num_n}. {item_n}
```

#### 演示

```
1. Ready
2. Set
3. Go

1. California
1. Hawaii
1. Alaska

1. C
3. C++
7. Java
5. Python
```

#### 效果

1. Ready
2. Set
3. Go

1. California
1. Hawaii
1. Alaska

1. C
3. C++
7. Java
5. Python

⚠ **Markdown列表序号逻辑：同一个列表，第一个条目的序号按指定序号显示，之后的条目序号由第一个序号顺延（递增）。因此第二个条目及其之后条目，指定什么序号无关紧要。**

ℹ **使用列表时，不同条目之间将处于不同行，效果相当于换行。但不需要在每一行末尾加至少2 Spaces。

### 10. 无序列表（unordered list？）

与有序列表相似，但更简单，将`{num}.`更换为`-`、`*`或`+`即可。

#### 通用格式

```
{- * +} {item_1}
{- * +} {item_2}
...
{- * +} {item_n}
```

#### 效果

> - {item_1}
> - {item_2}
> ...
> - {item_n}

⚠ **同一个列表，尽量使用同一个`{delim}`贯穿始终。**

### 11. 列表连续性保持：在列表中途插入其他内容

将欲插入的内容缩进4 Spaces / 1 Tab即可。

#### 演示

```
- item 1
- item 2
	a paragraph
- item 3
```

#### 效果

- item 1
- item 2
	a paragraph
- item 3

ℹ **这里所说的“其他内容”种类可以很广泛，如段落、引用、代码块等，甚至另一个列表（且不限有序/无序）。**

⚠ **如果要插入代码块，则需要8 Spaces / 2 Tabs的缩进，因为代码块本身具有4 Spaces / 1 Tab的固有缩进。**

## VII. 代码（code）

### 12. inline代码

Inline代码使用一对`` ` ``扩起。不过如果代码中要使用到`` ` ``字符，可以使用一对` `` `扩起。

#### 通用格式

`` `{inline_code}` ``

` ``{inline_code}`` `

### 13. 代码块（code blocks）

代码块指若干（≥1）整行的代码。对于要当作代码块处理的文字，请在行首保证4 Spaces / 1 Tab的缩进。

#### 通用格式

```
{4s/1t}{code_line_1}
{4s/1t}{code_line_2}
...
{4s/1t}{code_line_n}
```

#### 效果

> 	`{code_line_1}`
> 	`{code_line_2}`
> 	`...`
> 	`{code_line_n}`

ℹ **代码块连续性的保持估计类似于引用。**

### 14. 扩展功能：围栏式代码块（fenced code blocks）

嫌4S/1T的缩进太麻烦，可以使用**围栏式代码块**——使用一对` ``` `将代码行扩起。

#### 通用格式

```
\`\`\`
{code_line_1}
{code_line_2}
...
{code_line_n}
\`\`\`
```

#### 效果

> ```
> {code_line_1}
> {code_line_2}
> ...
> {code_line_n}
> ```

### 14a. 扩展功能：具有语法高亮的围栏式代码块

围栏式代码块可以有语法高亮。在第一组` ``` `后紧跟上一个语言名称（如`java`）即可。

#### 通用格式

```
\`\`\`{lang_code}
...
\`\`\`
```

#### 演示

```
\`\`\`c++
nullptr;
```

#### 效果

```c++
nullptr;
```

## VIII. 分割线（horizontal rules）

### 15. 分割线

在单独一行上使用至少3个`*`、`-`或`_`。

#### 通用格式

```
<content>
{*...* -...- _..._}
<content>
```

其中`*`/`-`/`_`字符的数量应至少为3（且只能使用一种）。

⚠ **分割线前后应当有至少1个空行（否则可能会被解析为标题）。**

## IX. 链接（links）

### 16. 链接

#### 通用格式

`[{hypertext}]({hyperlink})`
`[{hypertext}]({hyperlink} "{link_title}")`

其中`{hypertext}`为显示出来的超链接文字，`{hyperlink}`为超链接，`{link_title}`为超链接的title（即鼠标指针悬浮在超链接文字上时显示的一个小标签上的文字内容）。`{link_title}`可缺省。

#### 示例

```
I prefer [Bing](https://bing.com/ "premium search engine") to [Baidu](https://baidu.com/ "inferior search engine").
```

#### 效果

I prefer [Bing](https://bing.com/ "premium search engine") to [Baidu](https://baidu.com/ "inferior search engine").

### 17. 纯链接

纯链接使用`< >`扩起。

#### 通用格式

`<{link}>`

#### 示例

```
You are currently browsing <https://ambystomamexicanum.github.io/>.
```

#### 效果

You are currently browsing <https://ambystomamexicanum.github.io/>.

ℹ **`< >`其实可能并不是必要的——即使没有它，文本如果具有链接的格式，很可能也会被显示为超链接。**

ℹ **链接可以带格式，如`{hypertext}`可以是代码形式。**

### 18. 引用类型链接

*略，暂且不想写，反正还用不上*

## X. 图片（images）

### 19. 图片

#### 通用格式

``![{image_alt}]({image_link})``
``![{image_alt}]({image_link} "{image_title}")``

#### 示例

```
![An image.](/image.png "Image")
```

#### 效果

![An image.](/image.png "Image")

## XI. 转义字符（escaping characters）

### 20. 转义字符

Markdown中有很多字符有特殊功能，如\*、\#等。若希望将它们作为普通字符显示，而免除它们的特殊功能，在它们前面加上一个\\即可。

⚠ **代码格式的文字中若出现这样的符号，直接写即可，不要用\\进行转义！（若仍然加\\，会导致出现额外的\\！）**

## XII. 内嵌HTML代码

正常写就好了。但注意：**在代码块中，HTML代码无法发挥它们的作用**。

## XII. 表格（tables）

### 21. 表格

*好累啊，暂且懒得写了。\[TODO\]*
