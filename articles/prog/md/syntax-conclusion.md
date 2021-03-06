# Markdown基本语法归纳总结

<br />

*初步完成于2021年8月2日16点40分。*

<br />

## 预先说明

### 技术性说明

<br />

1. 本文中的所有英文术语，如果可以，均使用复数形式。

3. 本文中的Markdown代码中的使用`{ }`扩起的成分大多属于可以任意填入的内容（“参数”），其中被扩起的文字属于对可任意填入的内容的描述性名称（“参数名称”），如`{quote}`、`{text}`。用于**通用格式**的讲解中。

5. 本文中的Markdown代码中的`...`一般表示与其之前和之后相同性质内容的省略，用于**通用格式**的讲解中。`...`偶尔也表示该处可填入任意内容（仅出现在[21. 表格]处）。

7. 本文中的Markdown代码中的`{sp}`表示空格（因为空格不可见，故需要用这种方式明确地指出空格的存在）。

9. 本文中的Markdown代码中的`{ }`若包含几个用空格分隔的成分，表示该处应当出现列举的几个成分之一，且这些成分均为**字面值**而非（前文中所说的）**描述性名称**。如`{- * +}`即表示该处应当出现`-`、`*`或`+`之一。

11. 本文中，如果多个相同字符叠加在一起很难辨认具体的字符数量，该字符将只写一次（以inline代码块的形式），并在其前面加上一个数字以表示该字符重复的次数。如3个`_`字符连写将写为「3`_`」（而非「`___`」）。

<br />

⚠ 此外，在本文中有一个技术性细节应当引起读者的注意：文章中一切涉及文本形态的描述（如“换行”等），对象有时是Markdown代码，有时是Markdown代码对应的实际显示情况（可理解为“输出”）。二者可能有区别，故一定要严格区分。

<br />

### 非技术性说明

<br />

i. 本文的写作意图并非给公众看的教程，而只是笔者写给自己的Markdown知识点归纳。故**可能存在错误**，且**笔者对这些错误不负责**。读者阅读时**请保持谨慎**，本文**仅供参考**。

ii. 本文主要整理自[Markdown基本语法](https://markdown.com.cn/basic-syntax/)，少数整理自[Markdown扩展语法](https://markdown.com.cn/extended-syntax/)。

<br />

## I. 标题（headings）

### 1. 标题

<br />

使用1\~6个`#`来指定标题。`#`的数量对应不同级别的标题（1\~6），`#`越多，标题级别数越高，标题显示得越小。

<br />

#### 通用格式

<br />

`#...# {heading}`（整行）

其中`#`数量在1~6之间。

<br />

#### 示例

<br />

```
# Heading L1
## Heading L2
#### Heading L4
###### Heading L6
```

<br />

#### 效果

<br />

> # Heading L1
> ## Heading L2
> #### Heading L4
> ###### Heading L6

<br />

⚠ **`#...#`和`{heading}`之间最好留有空格（通常为1个）。（理由：Undef. behav.）**

<br />

### 1a. 标题（另一种表示法）

<br />

使用任意数量的`=`或`-`，来分别表示一级、二级标题。它们分别相当于1、2个`#`。

<br />

#### 通用格式

<br />

```
{heading_lvl_1}
=...=
```

```
{heading_lvl_2}
-...-
```

<br />

#### 效果

<br />

> `{heading_lvl_1}`
> ==

> `{heading_lvl_2}`
> --

<br />

## II. 段落（paragraphs）

### 3. 段落

<br />

在两段文字之间加入至少1个空行，即可将它们分为不同段落。

<br />

#### 通用格式

<br />

```
{para 1}

{para 2}
```

<br />

#### 效果

<br />

> `{para 1}`
>
> `{para 2}`

<br />

⚠ **不要用Space/Tab缩进段落。**

<br />

## III. 换行（line breaks）

### 4. 换行

<br />

在某一行的末尾添加至少2 Spaces，则代码中的下一行内容将会换行显示。

<br />

#### 通用格式

```
{line 1}{sp}...{sp}
{line 2}
```

<br />

其中`{sp}`至少2个。

<br />

#### 效果

<br />

> `{line 1}`  
> `{line 2}`

<br />

ℹ **换行和分段是有区别的：被分开的两段文字之间的行距不同，且行距：换行 > 分段。**

<br />

## IV. 强调（emphasis）

### 5~7. 粗体（bold）、斜体（italic）和粗斜体

<br />

分别使用一对`*`（或`_`）、`**`（或2`_`）和`***`（或3`_`）对文本进行倾斜、加粗或叠加两种效果。

<br />

#### 通用格式

<br />

`*{text_italic}*`

`_{text_italic}_`

`**{text_bold}**`

`__{text_bold}__`

`***{text_italic_bold}***`

`___{text_italic_bold}___`

<br />

#### 效果

<br />

> *{text_italic}*
> 
> _{text_italic}_
> 
> **{text_bold}**
> 
> __{text_bold}__
> 
> ***{text_italic_bold}***
> 
> ___{text_italic_bold}___

<br />

⚠ **开始处的`*`后面不要有空格。`_`表示法可能会比较tricky，不熟练者建议回避使用。晚点再来整理\[TODO]。**

⚠ **下划线疑似只能使用HTML代码来表达：`<u>{text_underlined}</u>`。**

<br />

## V. 块引用（blockquotes）

### 8. 块引用

<br />

_注：“块引用”以下简称为**引用**。_

<br />

在行首使用`>`来创建引用。

<br />

#### 基本格式

<br />

`> {quote}`（整行）

<br />

#### 效果

<br />

>> `{quote}`

<br />

ℹ **本文中，*效果*演示有一层固有的引用效果。务必将这层固有引用效果与这里实际上要演示的引用效果区分清楚。下同。**

<br />

### 8.a. 引用连续性保持：多段引用

<br />

在原先的空行处加入`>`，即可保持引用的连续性。

<br />

#### 基本格式

<br />

```
> {para 1}
>
> {para 2}
```

<br />

#### 效果

<br />

>> `{para 1}`
>> 
>> `{para 2}`

<br />

### 8.b. 嵌套引用

<br />

引用可以嵌套。交替使用数量不等的`>`即可实现嵌套引用，并且`>`的数量决定嵌套层级。

<br />

#### 演示

<br />

```
Martin Luther King said,
> Washington stated,
>> All men are born equal.
```

<br />

#### 效果

<br />

> Martin Luther King said,
>> Washington stated,
>>> All men are born equal.

<br />

ℹ **引用可以带有其他Markdown元素，如强调和列表等。**

<br />

## VI. 列表（lists）

### 9. 有序列表（ordered lists）

<br />

在想要纳入列表的每一行开始处加上一个数字和、一个`.`和1 Space，即可创建一个列表。

<br />

#### 通用格式

<br />

```
{num_1}. {item_1}
{num_2}. {item_2}
...
{num_n}. {item_n}
```

<br />

#### 演示

<br />

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

<br />

#### 效果

<br />

1. Ready
2. Set
3. Go

<br />

1. California
1. Hawaii
1. Alaska

<br />

1. C
3. C++
7. Java
5. Python

<br />

⚠ **Markdown列表序号逻辑：同一个列表，第一个条目的序号按指定序号显示，之后的条目序号由第一个序号顺延（递增）。因此第二个条目及其之后的条目，指定什么序号无关紧要。**

<br />

ℹ **使用列表时，不同条目之间将处于不同行，效果相当于换行。不需要在每一行末尾加≥2 Spaces。**

<br />

### 10. 无序列表（unordered lists）

<br />

与有序列表相似，但更简单，将`{num}.`更换为`-`、`*`或`+`即可。

<br />

#### 通用格式

<br />

```
{- * +} {item_1}
{- * +} {item_2}
...
{- * +} {item_n}
```

<br />

#### 效果

<br />

> - {item_1}
> - {item_2}
> ...
> - {item_n}

<br />

⚠ **同一个列表，尽量使用`-`、`*`或`+`中的同一个字符贯穿始终，而不要混合使用多种。**

<br />

### 11. 列表连续性保持：在列表中途插入其他内容

<br />

将欲插入的内容缩进4 Spaces / 1 Tab即可。

<br />

#### 演示

<br />

```
- item 1
- item 2

	a paragraph

- item 3
```

<br />

#### 效果

<br />

- item 1
- item 2

	a paragraph

- item 3

<br />

🔨 **这里所说的“其他内容”种类可以很广泛，如段落、引用、代码块等，甚至另一个列表（且不限有序/无序；此即为*列表嵌套*）。**

<br />

⚠ **如果要插入代码块，则需要8 Spaces / 2 Tabs的缩进，因为代码块本身具有4 Spaces / 1 Tab的固有缩进。**

⚠ **空行不会破坏列表的连续性，即有序列表的序号不受影响。（GitHub测试结果）**

<br />

## VII. 代码（code）

### 12. inline代码

<br />

Inline代码使用一对`` ` ``扩起。

<br />

#### 通用格式

<br />

`` `{inline_code}` ``

` ``{inline_code}`` `

<br />

⚠ i. 如果代码中要使用到`` ` ``字符，可以使用一对` ```` `扩起。

⚠ ii. 如果代码中要使用到≥2个连续的`` ` ``字符，仍然使用`` ` ``即可。

⚠ iii. 如果代码开头处就要使用` `` `字符（不管多少个），请在开头处的` `` `字符后空一个格，再使用` `` `（或` `` `）。

⚠ iv. 同理，如果代码结尾处要使用` `` `字符（也不管多少个），请在使用完` `` `（不管多少个）之后，再使用`` ` ``（或` `` `）来完结代码。

<br />

### 13. 代码块（code blocks）

<br />

代码块指连续的、若干（≥1）整行的代码。对于要当作代码块处理的文字，请在行首保证 4 Spaces / 1 Tab 的缩进。

<br />

#### 通用格式

<br />

```
{4sp tab}{code_line_1}
{4sp tab}{code_line_2}
...
{4sp tab}{code_line_n}
```

<br />

#### 效果

<br />

> 	`{code_line_1}`
> 	`{code_line_2}`
> 	`...`
> 	`{code_line_n}`

<br />

### 14. 扩展功能：围栏式代码块（fenced code blocks）

<br />

嫌 4 Spaces / 1 Tab 的缩进太麻烦，可以使用**围栏式代码块**——使用一对` ``` `将代码行扩起。

<br />

#### 通用格式

<br />

``````
```
{code_line_1}
{code_line_2}
...
{code_line_n}
```
``````

<br />

#### 效果

<br />

> ```
> {code_line_1}
> {code_line_2}
> ...
> {code_line_n}
> ```

⚠ 若围栏式代码块中要出现` ``` `，请使用至少4个` `` `来标识围栏式代码块的起始和结束。

<br />

### 14a. 扩展语法：具有语法高亮的围栏式代码块

<br />

围栏式代码块可以有语法高亮。在第一组3`` ` ``后紧跟上一个语言名称（如`java`）即可。

<br />

#### 通用格式

<br />

``````
```{lang_code}
...
```
``````

<br />

#### 演示

<br />

``````
```c++
for (int * pi = get_pointer(); pi != nullptr; pi = get_pointer())
	cout << *pi << endl;
```
``````

<br />

#### 效果

<br />

```c++
for (int * pi = get_pointer(); pi != nullptr; pi = get_pointer())
	cout << *pi << endl;
```

<br />

ℹ **关于编程语言代号（GitHub测试）：C++：`c++`或`cpp`；C#：`c#`、`csharp`或`cs`。大小写不限。**

<br />

## VIII. 分割线（horizontal rules）

### 15. 分割线

<br />

在单独一行上使用至少3个`*`、`-`或`_`。

<br />

#### 通用格式

<br />

```
<content>
{*...* -...- _..._}
<content>
```

<br />

其中`*`/`-`/`_`字符的数量应至少为3（且只能使用一种）。

<br />

⚠ **分割线前后应当有至少1个空行（否则可能会被解析为标题）。**

<br />

## IX. 链接（links）

### 16. 链接

<br />

#### 通用格式

<br />

`[{hypertext}]({hyperlink})`

`[{hypertext}]({hyperlink} "{link_title}")`

<br />

其中：

- `{hypertext}`为显示出来的超链接文字；
- `{hyperlink}`为超链接；
- `{link_title}`为超链接的title（即鼠标指针悬浮在超链接文字上时显示的一个小标签上的文字内容），**可缺省**。

<br />

#### 示例

<br />

```
I prefer [Bing](https://bing.com/ "premium search engine") to [Baidu](https://baidu.com/ "inferior search engine").
```

<br />

#### 效果

<br />

I prefer [Bing](https://bing.com/ "premium search engine") to [Baidu](https://baidu.com/ "inferior search engine").

<br />

🔨 **链接并非必须是通常的URL，也可以是缩略版的，如`/assets/audio.mp3`。甚至可以是一个简单的锚，如`#vii-代码code`。这样可以非常方便地在同一张网页中进行导航。**

<br />

### 17. 纯链接

<br />

纯链接使用`< >`扩起。

<br />

#### 通用格式

<br />

`<{link}>`

<br />

#### 示例

<br />

```
You are currently browsing <https://ambystomamexicanum.github.io/>.
```

<br />

#### 效果

<br />

You are currently browsing <https://ambystomamexicanum.github.io/>.

<br />

ℹ **许多时候，即便没有`< >`，具有链接形式的文字也将会自动以超链接形式显示（这属于Markdown的扩展功能）。**

<br />

🔨 **链接可以带格式，如`{hypertext}`可以是代码形式。**

<br />

### 18. 引用类型链接

<br />

*略，暂且不想写，反正还用不上*

<br />

## X. 图片（images）

### 19. 图片

<br />

#### 通用格式

<br />

``![{image_alt}]({image_link})``

``![{image_alt}]({image_link} "{image_title}")``

<br />

其中：

- `{image_alt}`为图片无法显示时，显示在图片原先应当显示的位置处的文字（alternative text）。
- `{image_link}`为图片的链接。
- `{image_title}`为鼠标悬浮在图片上时出现的一个小标签上的文字内容，**可缺省**。

<br />

#### 示例

<br />

```
![An image.](/image.png "Image")
```

<br />

#### 效果

<br />

![An image.](/image.png "Image")

<br />

## XI. 转义字符（escaping characters）

### 20. 转义字符

<br />

Markdown中有很多字符有特殊功能，如`*`、`#`等。若希望将它们作为普通字符显示，而免除它们的特殊功能，在它们前面加上一个\\即可。

<br />

⚠ **代码格式的文字中若出现这样的符号，直接写即可，不要用\\进行转义！（若仍然加\\，会导致出现额外的\\ ！）**

⚠ **如要在代码块中出现`` ` ``字符，具体方法参见[VII. 代码（code）](#vii-代码code)。**

ℹ **欲显示某些字符，可以进行转义，也可以不进行转义（如`]`）。**

<br />

## XII. 内嵌HTML代码

<br />

Markdown语言支持在其内部（即`.md`文件内部）直接使用HTML代码。

所以，Markdown内部想使用HTML，正常写就好了。

<br />

⚠ **在代码块中，HTML代码无法发挥它们的作用。**。

⚠ **在表格（扩展功能）中，可能也无法使用特定的HTML代码。**

<br />

--------------------------------------------------------------------------------

<br />

好了，以上内容除[14a. 扩展语法：具有语法高亮的围栏式代码块](#14a-扩展语法具有语法高亮的围栏式代码块)外，均为Markdown的**基本语法**（basic syntax）。

接下来的语法则属于Markdown的**扩展语法**（extended syntax）。注意，这些语法并不是在所有场合都可用的——有些场合（如<github.io>，甚至包括GitHub自己）可能不支持使用如下的一些语法。

<br />

## XIII. 扩展语法：表格（tables）

### 21. 表格

<br />

#### 通用格式

<br />

在Markdown中，创建表格的语法如下：

```
| {title 1} | {title 2} | ... | {title n} |
| -...- | -...- | -...- | -...- |
| ... | ... | ... | ... |
| ... | ... | ... | ... |
...
| ... | ... | ... | ... |
```

其中`{heading i}`（`i = 1, 2, ..., n`）为每一列的标题，其将会以粗体显示；第二行的每个单元格中建议至少包含3个`-`字符。

<br />

#### 演示

<br />

```
| Language | Level |
| -------- | ----- |
| ASM | Low |
| C | Medium |
| C++ | Intermediate |
| Java | High |
| Python | Ultra-high |
```

效果：

> | Language | Level |
> | -------- | ----- |
> | ASM | Low |
> | C | Medium |
> | C++ | Intermediate |
> | Java | High |
> | Python | Ultra-high |

<br />

ℹ️ Markdown代码中，每个单元格中都可以在文字的两端插入任意数量的空白（Space/Tab），而不影响最终的显示效果。但为了美观，常常会加入一定数量的Space/Tab以对齐每一行的`|`字符。

ℹ️ 创建Markdown表格可能会有些繁琐，尤其是想对齐Markdown代码中的`|`字符时。这时，可以使用[Markdown Tables Generator](https://www.tablesgenerator.com/markdown_tables)来完成这项工作。

<br />

### 22. 内容文字对齐的表格

<br />

在Markdown表格表示法中的第二行的某个单元格中，在`-...-`的左侧、两侧或右侧添加`:`，则其所属列的文字将分别被左、中、右对齐。

<br />

#### 演示

<br />

```
| Language | Level |
| :------- | ----: |
| ASM | Low |
| C | Medium |
| C++ | Intermediate |
| Java | High |
| Python | Ultra-high |
```

效果：

> | Language | Level |
> | :------- | ----: |
> | ASM | Low |
> | C | Medium |
> | C++ | Intermediate |
> | Java | High |
> | Python | Ultra-high |

<br />

ℹ️ 表格中可以添加部分其他Markdown元素。

<br />

### 23. 表格中的转义：在表格中显示`|`字符

<br />

使用HTML代码`&#124;`，即可在表格中正常显示`|`字符。

<br />

## XIV. 扩展功能：标题编号

### 24. 标题编号

<br />

❌ GitHub疑似不支持此扩展功能。

<br />

在原先的表示标题的Markdown代码末尾加上一个空格，之后一对大括号（`{`和`}`），里面添加一个字符串以表示标题编号。

#### 通用格式

`# {title} {#{id}}`

:warning: 注意这里第一层大括号为**字面意义上的大括号**（即不具有前文那样的特殊含义）。

#### 示例

```
# ID-ed title {#24}
```

效果：

> # ID-ed title {#24}

## XV. 扩展功能：定义列表

### 25. 定义列表

<br />

❌ GitHub疑似不支持此扩展功能。

<br />

翻阅一些网站就会知道，术语的**定义**常常以这种形式给出：

> Definition
> : An explanation of the meaning of a word or phrase, especially in a dictionary; the act of stating the meanings of words and phrases.

使用Markdown的一条扩展语法即可应用这种格式。

#### 通用格式

```
{term}
: {def_1}
: {def_2}
...
: {def_n}
```

#### 效果

<br />

> {term}
> : {def_1}
> : {def_2}
> ...
> : {def_n}

<br />

## XVI. 扩展功能：删除线

### 26. 删除线

<br />

欲让一段文本被打上删除线，可以用一对`~~`将该段文本扩起。

<br />

#### 通用格式

<br />

`~~{text_del}~~`

<br />

#### 效果

<br />

> ~~{text_del}~~

<br />

ℹ️ **在GitHub中，只需要使用一对*单个*的`~`字符，就可以实现上述功能。（但还是建议用2个`~`。）**

<br />

## XVII. 扩展功能：任务列表

### 27. 任务列表

有时候，你可能想模拟一份任务清单，且有一些任务已经完成了。Markdown扩展语法支持模拟一份这样的任务清单。

<br />

#### 通用格式

<br />

```
- {[ ] [x]} item 1
- {[ ] [x]} item 2
...
- {[ ] [x]} item n
```

其中`{[ ] [x]}`表示该处应有`[ ]`或`[x]`。`[ ]`表示空的复选框，而`[x]`表示打了√的复选框。

<br />

#### 演示

<br />

```
- [x] Go running
- [x] Write an article
- [ ] Learn a language
```

效果：

> - [x] Go running
> - [x] Write an article
> - [ ] Learn a language

<br />

## XVIII. 扩展功能：Emoji的使用

<br />

欲在Markdown中输入emoji，可直接输入实际的emoji字符，也可以使用**表情符号简码**（emoji shortcodes）进行输入。

<br />

### 28. 表情符号简码（emoji shortcodes）

<br />

❌ github.io疑似不支持此扩展功能。

<br />

表情符号简码的形式为`:{shortcode}:`。如`:tent:`即表示⛺，`:joy:`即表示😂。

<br />

------------------------------------------------------------

<br />

差不多以上就是主要的Markdown语法了——这么多Markdown语法，基本够用了。

平心而论，这篇文章并不算长的。但你可能会觉得，这篇文章，很长。

我想说，即便你真的这么认为，也没有什么可怕的。以上内容，之所以这么多，只是尽可能地覆盖全部的功能和情形——作为一份Markdown讲解，这是必要的。然而，实际上（一次）会使用到的Markdown知识，可能只是以上内容的一小部分。而且，可以不去阅读这么多内容（静态，类似于C），而是在使用的过程中逐渐发现新问题，再去查找解决方案（动态，类似于Python）。

最后的最后——在告别Markdown学习之际，我还是要提一句——**Markdown虽然语法简单而功能强大，但它不是万能的，有的时候Markdown无能为力。** **故，在必要时，请使用HTML**（可直接在Markdown代码中使用HTML；见[XII. 内嵌HTML代码](#xii-内嵌html代码)）。

其他资料：

[Markdown嵌套可行性表](markdown-nesting-table.md)
