# Markdown基本语法归纳总结

*初步完成于2021年8月2日16点40分。*

## 预先说明

### 技术说明

1. 本文中的所有英文术语，如果可以，均使用复数形式。

3. 本文中的Markdown代码中的使用`{ }`扩起的成分大多属于可以任意填入的内容（“参数”），其中被扩起的文字属于对可任意填入的内容的描述性名称（“参数名称”），如`{quote}`、`{text}`。用于**通用格式**的讲解中。

5. 本文中的Markdown代码中的`...`表示与其之前和之后相同的字符的省略，用于**通用格式**的讲解中。

7. 本文中的Markdown代码中的`{sp}`表示空格（因为空格不可见，故需要用这种方式明确地指出空格的存在）。

9. 本文中的Markdown代码中的`{ }`若包含几个用空格分隔的成分，表示该处应当出现列举的几个成分之一，且这些成分均为**字面值**而非（前文中所说的）**描述性名称**。如`{- * +}`即表示该处应当出现`-`、`*`或`+`之一。

11. 本文中，如果多个相同字符叠加在一起很难辨认具体的字符数量，该字符将只写一次（以inline代码块的形式），并在其前面加上一个数字以表示该字符重复的次数。如3个`_`字符连写将写为「3`_`」（而非「`___`」）。

⚠ 此外，在本文中有一个技术性细节应当引起读者的注意：文章中一切涉及文本形态的描述（如“换行”等），对象有时是Markdown代码，有时是Markdown代码对应的实际显示情况（可理解为“输出”）。二者可能有区别，故一定要严格区分。

### 非技术说明

i. 本文的写作意图并非给公众看的教程，而只是笔者写给自己的Markdown知识点归纳。故**可能存在错误**，且**笔者对这些错误不负责**。读者阅读时**请保持谨慎**，本文**仅供参考**。

ii. 本文主要整理自[Markdown基本语法](https://markdown.com.cn/basic-syntax/)，少数整理自[Markdown扩展语法](https://markdown.com.cn/extended-syntax/)。

## I. 标题（headings）

### 1. 标题

使用1\~6个`#`来指定标题。`#`的数量对应不同级别的标题（1\~6），`#`越多，标题级别数越高，标题显示得越小。

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

⚠ **`#...#`和`{heading}`之间最好留有空格（通常为1个）。（理由：Undef. behav.）**

### 1a. 标题（另一种表示法）

使用任意数量的`=`或`-`，来分别表示一级、二级标题。它们分别相当于1、2个`#`。

#### 通用格式

```
{heading_lvl_1}
=...=
```

```
{heading_lvl_2}
-...-
```

#### 效果

> `{heading_lvl_1}`
> ==

> `{heading_lvl_2}`
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

ℹ **换行和分段是有区别的：被分开的两段文字之间的行距不同，且行距：换行 > 分段。**

## IV. 强调（emphasis）

### 5~7. 粗体（bold）、斜体（italic）和粗斜体

分别使用一对`*`（或`_`）、`**`（或2`_`）和`***`（或3`_`）对文本进行倾斜、加粗或叠加两种效果。

#### 通用格式

`*{text_italic}*`

`_{text_italic}_`

`**{text_bold}**`

`__{text_bold}__`

`***{text_italic_bold}***`

`___{text_italic_bold}___`

#### 效果

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

⚠ **开始处的`*`后面不要有空格。`_`表示法可能会比较tricky，不熟练者建议回避使用。晚点再来整理\[TODO]。**

⚠ **下划线疑似只能使用HTML代码来表达：`<u>{text_underlined}</u>`。**

## V. 块引用（blockquotes）

### 8. 块引用

_注：“块引用”以下简称为**引用**。_

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
> Washington stated,
>> All men are born equal.
```

#### 效果

> Martin Luther King said,
>> Washington stated,
>>> All men are born equal.

ℹ **引用可以带有其他Markdown元素，如强调和列表等。**

## VI. 列表（lists）

### 9. 有序列表（ordered lists）

在想要纳入列表的每一行开始处加上一个数字和、一个`.`和1 Space，即可创建一个列表。

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

❌ 序号连续。TODO。

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

⚠ **Markdown列表序号逻辑：同一个列表，第一个条目的序号按指定序号显示，之后的条目序号由第一个序号顺延（递增）。因此第二个条目及其之后的条目，指定什么序号无关紧要。**

ℹ **使用列表时，不同条目之间将处于不同行，效果相当于换行。不需要在每一行末尾加≥2 Spaces。**

### 10. 无序列表（unordered lists）

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

⚠ **同一个列表，尽量使用`-`、`*`或`+`中的同一个字符贯穿始终，而不要混合使用多种。**

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

🔨 **这里所说的“其他内容”种类可以很广泛，如段落、引用、代码块等，甚至另一个列表（且不限有序/无序；此即为*列表嵌套*）。**

⚠ **如果要插入代码块，则需要8 Spaces / 2 Tabs的缩进，因为代码块本身具有4 Spaces / 1 Tab的固有缩进。**

⚠ **空行不会破坏列表的连续性，即有序列表的序号不受影响。（GitHub测试结果）**

## VII. 代码（code）

### 12. inline代码

Inline代码使用一对`` ` ``扩起。

#### 通用格式

`` `{inline_code}` ``

` ``{inline_code}`` `

⚠ i. 如果代码中要使用到`` ` ``字符，可以使用一对` ```` `扩起。
⚠ ii. 如果代码中要使用到≥2个连续的`` ` ``字符，仍然使用`` ` ``即可。
⚠ iii. 如果代码开头处就要使用` `` `字符（不管多少个），请在开头处的` `` `字符后空一个格，再使用` `` `（或` `` `）。
⚠ iv. 同理，如果代码结尾处要使用` `` `字符（也不管多少个），请在使用完` `` `（不管多少个）之后，再使用`` ` ``（或` `` `）来完结代码。

### 13. 代码块（code blocks）

代码块指连续的、若干（≥1）整行的代码。对于要当作代码块处理的文字，请在行首保证4 Spaces / 1 Tab的缩进。

#### 通用格式

```
{4sp tab}{code_line_1}
{4sp tab}{code_line_2}
...
{4sp tab}{code_line_n}
```

#### 效果

> 	`{code_line_1}`
> 	`{code_line_2}`
> 	`...`
> 	`{code_line_n}`

### 14. 扩展功能：围栏式代码块（fenced code blocks）

嫌4 Spaces / 1 Tab的缩进太麻烦，可以使用**围栏式代码块**——使用一对` ``` `将代码行扩起。

#### 通用格式

``````
```
{code_line_1}
{code_line_2}
...
{code_line_n}
```
``````

#### 效果

> ```
> {code_line_1}
> {code_line_2}
> ...
> {code_line_n}
> ```

⚠ 若围栏式代码块中要出现` ``` `，请使用至少4个` `` `来标识围栏式代码块的起始和结束。

### 14a. 扩展功能：具有语法高亮的围栏式代码块

围栏式代码块可以有语法高亮。在第一组3`` ` ``后紧跟上一个语言名称（如`java`）即可。

#### 通用格式

``````
```{lang_code}
...
```
``````

#### 演示

``````
```c++
for (int * pi = get_pointer(); pi != nullptr; pi = get_pointer())
	cout << *pi << endl;
```
``````

#### 效果

```c++
for (int * pi = get_pointer(); pi != nullptr; pi = get_pointer())
	cout << *pi << endl;
```

ℹ **关于编程语言代号（GitHub测试）：C++：`c++`或`cpp`；C#：`c#`、`csharp`或`cs`。大小写不限。**

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

其中：
- `{hypertext}`为显示出来的超链接文字；
- `{hyperlink}`为超链接；
- `{link_title}`为超链接的title（即鼠标指针悬浮在超链接文字上时显示的一个小标签上的文字内容），**可缺省**。

#### 示例

```
I prefer [Bing](https://bing.com/ "premium search engine") to [Baidu](https://baidu.com/ "inferior search engine").
```

#### 效果

I prefer [Bing](https://bing.com/ "premium search engine") to [Baidu](https://baidu.com/ "inferior search engine").

🔨 **链接并非必须是通常的URL，也可以是缩略版的，如`/assets/audio.mp3`。甚至可以是一个简单的锚，如`#vii-代码code`。这样可以非常方便地在同一张网页中进行导航。**

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

ℹ **许多时候，即便没有`< >`，具有链接形式的文字也将会自动以超链接形式显示（Markdown扩展功能）。**

🔨 **链接可以带格式，如`{hypertext}`可以是代码形式。**

### 18. 引用类型链接

*略，暂且不想写，反正还用不上*

## X. 图片（images）

### 19. 图片

#### 通用格式

``![{image_alt}]({image_link})``

``![{image_alt}]({image_link} "{image_title}")``

其中：

- {image_alt}为图片无法显示时，显示在图片原先应当显示的位置处的文字（alternative text）。
- {image_link}为图片的链接。
- {image_title}为鼠标悬浮在图片上时出现的一个小标签上的文字内容，**可缺省**。

#### 示例

```
![An image.](/image.png "Image")
```

#### 效果

![An image.](/image.png "Image")

## XI. 转义字符（escaping characters）

### 20. 转义字符

Markdown中有很多字符有特殊功能，如`*`、`#`等。若希望将它们作为普通字符显示，而免除它们的特殊功能，在它们前面加上一个\\即可。

⚠ **代码格式的文字中若出现这样的符号，直接写即可，不要用\\进行转义！（若仍然加\\，会导致出现额外的\\ ！）**

⚠ **如要在代码块中出现`` ` ``字符，具体方法参见[VII. 代码（code）](#vii-代码code)。**

## XII. 内嵌HTML代码

正常写就好了。

⚠ **在代码块中，HTML代码无法发挥它们的作用**。

## XII. 表格（tables）

### 21. 表格

*好累啊，暂且懒得写了。\[TODO\]*
