# 🚀 学生党必看！用Markdown彻底告别Word卡顿焦虑

> 💡 当你第5次因为Word崩溃丢失未保存的论文时，当你在凌晨3点还在和格式刷搏斗时，是时候解锁这个改变学术写作的神器了！
# Markdown & R Markdown 完全教学指南

## 一、Markdown核心概念
### 1.1 什么是Markdown？
Markdown是一种轻量级标记语言，通过简单符号实现格式排版，文件后缀为`.md`

### 1.2 核心优势
- **跨平台兼容**：纯文本可在任何设备查看
- **格式稳定性**：避免Word格式错乱问题
- **高效写作**：专注内容而非排版
- **学术友好**：完美支持数学公式与代码块

## 二、环境配置指南
本文仅介绍VS Code和R studio的Markdown配置和使用，适合小白和进阶选手 :books:
### 2.1 VS Code配置
#### VS Code是什么？
Visual Studio Code（VS Code） 是由 Microsoft 开发的一款免费、开源、跨平台的代码编辑器，支持 Windows、macOS 和 Linux，并且具有强大的扩展功能，广泛应用于编程、数据科学、Markdown 编辑等。
#### 安装步骤
1. 访问 [VS Code官网](https://code.visualstudio.com/) 下载安装（可以搜索任何一个安装配置vscode视频跟着安装，不再赘述）
2. 安装必要扩展：
在VS Code左侧"Extensions"(或快捷键Ctrl+Shift+X)，搜索并安装以下扩展
   - Markdown All in One（快捷键支持）
   - Markdown Preview Enhanced（实时预览）
   - Paste Image（图片粘贴插件）
   - Code Spell Checker（拼写检查）

#### 工作流建立
打开 vscode之后,点击 open a folder选择你的文件夹，之后add a new file 起名为 文件名.md 

导出：
用插件[Markdown Preview Enhanced]
点击预览-鼠标右键-export

沉浸式写作：
ctrl+k松开再摁Z可以实现清屏，退出摁两次esc

### 2.2 R Markdown配置
#### R Markdown是什么？
R 语言 是一种专为统计计算和数据分析设计的编程语言，广泛用于数据科学、机器学习和可视化。

RStudio 是 R 语言的集成开发环境（IDE），提供代码编辑、数据可视化、Markdown 支持等功能，使 R 编程更高效直观。

R Markdown 是一个强大的工具，适用于数据科学、学术研究和报告生成。它结合了 **Markdown 的简洁性** 和 **R 语言的强大计算能力**，使数据分析变得更加可读、可复现、可共享。非常建议统计学学子和使用R软件的同学使用。

#### 安装
安装 [R语言](https://www.r-project.org/)
安装 [RStudio](https://posit.co/downloads/)
安装 TinyTeX（TinyTeX(一个轻量级、便捷的 TeX 发行版，由 Yihui Xie 开发，专门为 R Markdown 和 LaTeX 用户设计。体积更小、安装更快，非常适合在 R Markdown 中编译 PDF 文档)
```R
install.packages("tinytex")
```
或者安装LaTeX（太大了，如果不是追求高质量的论文和报告可以不装🤐）
#### 使用
新建文档
File -> New File -> R Markdown...
选择输出格式（HTML/PDF/Word）
一个 R Markdown 文件通常以 .Rmd 作为扩展名，它由三部分组成：  
1. YAML 头部
指定文档标题、作者、输出格式等信息，使用 YAML 语法，写在 --- 之间。一般新建R markdown会自动生成
```r
title: "R Markdown"
author: "张三"
date: "2025-02-27"
output: html_document
```

2. Markdown 语法（文本部分）
   This is an R Markdown document. Markdown is a simple formatting syntax for authoring HTML, PDF, and MS Word documents. For more details on using R Markdown see <http://rmarkdown.rstudio.com>.  

3. 代码块（代码部分）
```{r cars}
summary(cars)
```
#### R Markdown 的工作流程
1. 编写 .Rmd 文件
2. 执行代码并查看结果
3. 渲染（Knit）成最终文档
4. 导出为 HTML/PDF/Word
   
## 三、Markdown语法详解
### 基础语法
1. 标题：
   用多个"#" + 空格 + 文字生成不同级别的标题：

#一级标题
##二级标题
###三级标题
####四级标题
#####五级标题
######六级标题 

实例：
# 一级标题
## 二级标题
### 三级标题


2. 强调文本：
    使用两个星号"**"或者两个下划线"__"包裹文本
    **这句需要强调**
    __这句需要强调__
    快捷键:ctrl+B(需要扩展：Markdown All in One)

3. 斜体：
使用单个星号"*"或单个下划线"_"包裹文本：
*这句是斜体*
_这句是斜体_
快捷键：ctrl+I(需要扩展：Markdown All in One)

4. 引用：在段落前添加 > 即可创建引用块：
 > 这是一段引用

5. 分割线：输入三个或以上的"*"或"-"或"_"，回车后自动生成分割线
---

6. 下划线：使用 HTML 标签`"<u>"`和`"</u>`实现下划线
<u>下划线</u>

7.  插入Emoji:直接插入emoji代码即可显示图标：
:smile:
可参考以下两个网站复制emoji代码
>https://unicode.org/emoji/charts/full-emoji-list.html
>https://www.webfx.com/tools/emoji-cheat-sheet/

8. 下标：下标的文字前后各加"~"
p~value~

9. 上标：上标的文字前后各加"^"
X^2^

10.  高亮文字：文字前后加"=="
==这是一段高亮文字==

11.  删除线：文字前后加"~~"
~~这行字需要删除~~

12.  添加代码：代码前后用反引号`` ` ``
    `print("hello world")`
13.  添加代码块：按三个反引号`` ` ``之后选择语言，或者在三个`` ` ``后直接输入语言
```python
print("hello world")
```

14.  有序列表：输入数字 + "." + 文字
    1. 一级列表
       1. 二级列表
    2.  一级列表
15.  无序列表："-"或者"+" + 空格+文字
    - 无序列表第一行
    - 无序列表第二行
  
3.  插入公式：
    行内数学公式：使用 `$...$` 包裹公式，快捷键：crtl+M $\frac{\partial f}{\partial x} = 2\sqrt{a}x$

   行间数学公式： 使用 `$$...$$` 包裹公式

$$
\frac{\partial f}{\partial x} = 2\sqrt{a}x
$$

17. 矩阵：
\begin{bmatrix}
a & b \\
c & d
\end{bmatrix}

$$
\begin{bmatrix}
a & b \\
c & d
\end{bmatrix}
$$



18.  表格：在每列之间添加"|"用竖线区分，并通过 - 定义表头对齐方式
```
| 名字 | 性别 | 年龄 |
| ---- | ---- | ---- |
| 张三 | 男   | 20   |
| 李四 | 男   | 21   |
| 王五 | 女   | 22   |
```

| 名字 | 性别 | 年龄 |
| ---- | ---- | ---- |
| 张三 | 男   | 20   |
| 李四 | 男   | 21   |
| 王五 | 女   | 22   |

对齐说明：
居中`:---:`
左对齐`:---`
右对齐`---:`

推荐工具Tables Generator：
Tables Generator 是一个在线工具，用于快速创建和格式化 Markdown、LaTeX、HTML、CSV 等格式的表格。
[Tables Generator官网](https://www.tablesgenerator.com/#google_vignette)
选择 Markdown 选项，手动输入数据或复制粘贴数据，点击“Generate” 生成 Markdown 表格，复制 Markdown 代码，粘贴到你的 Markdown 文件中

19. 插入图片:
插入本地或网络图片：
在 VSCode 中建议安装 Paste Image 插件，快捷键：Ctrl+Alt+V
手动插入本文件夹之下的图片：![]()
![](my%20photo.jpg)  
*我的图片*



## 四、R Markdown进阶应用
###  文档结构
可对YAML进行个性化编辑：
YAML:
header-includes:上下行距
linestretch：行间距
toc: table of content 是否根据headings自动生成目录

```r
title: "test"
subtitle: "subtitle"
author: "a"
date: "2024-09-30"
output:
  pdf_document: default
  html_document: default
frontsize: 12pt
header-includes: \usepackage{geometry} \geometry{left = 2cm, right = 2cm, top = 1cm}
linestretch: 1.5
toc: TRUE
```

需要输出中文：
\documentclass: ctexart
(chinese tex article)
\CJKmainfont:某种字体

### 代码块控制输出控制
R代码块一般通过{R}来插入，插入代码段的快捷键：Ctrl+Alt+I 
参数	功能	常用值
echo	是否显示代码	TRUE:输出代码/FALSE:不输出代码
fig.width	图片宽度	7（英寸）
warning	是否显示警告	FALSE
message	是否显示包加载信息	FALSE

---

作为一个统计学硕士，打一些在R markdown里我经常用的公式（之后有空补一下vs code里的，差的不多）
### 常用数学公式：
基础：
x^n  % 上标
x_n  % 下标
根号：
\sqrt{x}, \quad \sqrt[n]{x}  % 开平方和 n 次方根
分数：
\frac{a}{b}  % a/b

组合与排列
{n \choose k}  % 组合
{n \binom k}  % 也可用于组合

极限：\lim_{x \to \infty} f(x)  % 极限
\sum_{i=1}^n i  % 求和
\prod_{i=1}^n i  % 连乘
\frac{dy}{dx}, \quad \frac{\partial y}{\partial x}  % 导数和偏导数
\int_a^b f(x) \, dx  % 定积分
\iint f(x, y) \, dx \, dy  % 二重积分
\oint_\gamma f(z) \, dz  % 环路积分
矩阵
\begin{bmatrix}
    a & b \\
    c & d
\end{bmatrix}
行列式
\begin{vmatrix}
    a & b \\
    c & d
\end{vmatrix}

其他符号：
约等于： \approx b
类似于或成比例于：a \sim b
正负号 \pm
小于等于 \leq less than or equal to
大于等于\geq greater than or equal to

估计值的角标（“hat”）\hat{\theta}


小写希腊字母  输出内容
\alpha       % α
\beta        % β
\gamma       % γ
\delta       % δ
\epsilon     % ε
\zeta        % ζ
\eta         % η
\theta       % θ
\iota        % ι
\kappa       % κ
\lambda      % λ
\mu          % μ
\nu          % ν
\xi          % ξ
\omicron     % ο 
\pi          % π
\rho         % ρ
\sigma       % σ
\tau         % τ
\upsilon     % υ
\phi         % φ
\chi         % χ
\psi         % ψ
\omega       % ω

大写希腊字母
\Gamma       % Γ
\Delta       % Δ
\Theta       % Θ
\Lambda      % Λ
\Xi          % Ξ
\Pi          % Π
\Sigma       % Σ
\Upsilon     % Υ
\Phi         % Φ
\Psi         % Ψ
\Omega       % Ω


### 版本控制小tips
在文件结尾使用代码：
```
sessionInfo()
```
可以输出当前的版本
