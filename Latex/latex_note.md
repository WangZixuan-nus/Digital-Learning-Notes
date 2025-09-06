# LaTeX 入门教程

## 认识 LaTeX

### 基础语法
- **注释**：使用 `%`（快捷键：Ctrl+/，Mac：Command+/）
- **命令或特殊符号**：以 `\` 开头，可以把特殊符号变成普通符号
- **普通文本**：直接输入即可显示

### LaTeX 中的特殊符号

以下符号在 LaTeX 中有特殊含义，不能直接作为普通文本使用：

```latex
% 注释符号：在LaTeX中，百分号用作注释标记
& 对齐符号：用于表格或数学公式中的位置对齐
$ 数学公式标记：框在两个$符号中间的内容将被解释为数学公式
~ 强制空格：保持不可分割的空格
^ 和 _ 上下标标记：用作上标和下标
{ } 分组符号：将其中的内容作为一个整体对待
# 参数分隔符：主要在编写宏包时使用
\ 转义符号：用于输入命令和特殊符号
```

**如何输入特殊符号**：
- `\%` → %
- `\&` → &
- `\$` → $
- `\{` → {
- `\}` → }
- `\#` → #
- `\textasciitilde` → ~
- `\textbackslash` → \

## 文档结构

### 设定区域（导言区）
```latex
\documentclass{...}
\usepackage{...}
```
- 规定文档类型和格式
- 导入相关宏包
- 定义全局设置
- 通常不会直接影响PDF的可见内容
  
[Latex常用宏包](https://zhuanlan.zhihu.com/p/43981639)

**常用文档类型**：
- `article`：文章
- `report`：报告
- `book`：书籍
- `beamer`：演示文稿

**常用宏包**：
- `ctex`：中文支持
- `geometry`：页面布局
- `amsmath`：数学公式
- `graphicx`：图片插入
- `hyperref`：超链接
- `biblatex`：参考文献

### 正文区域
```latex
\begin{document}
...
\end{document}
```
所有在最终PDF文件中的可见内容均在此区域添加，包括文字、图表、公式等。

### 正文各级标题

**标题层级**（按重要性递减）：
- `\part{}`：部分（仅book类可用）
- `\chapter{}`：章（仅report和book类可用）
- `\section{}`：节
- `\subsection{}`：小节
- `\subsubsection{}`：小小节
- `\paragraph{}`：段落标题
- `\subparagraph{}`：子段落标题

### 换行、换段、换页命令

- **换行**：
  - `\\`：强制换行
  - `\newline`：换行（不允许分页）
  - `\\[距离]`：换行并增加额外距离
- **分段**：
  - 空行：自然分段
  - `\par`：显式分段
- **分页**：
  - `\newpage`：强制分页
  - `\clearpage`：清除浮动体并分页
- **首行缩进**：
  - `\setlength{\parindent}{2em}`：设置首行缩进距离
  - `\noindent`：取消当前段落首行缩进

## 基本文档示例

### 最简示例
```latex
\documentclass{article}
\begin{document}
Hello world! from \LaTeX
\end{document}
```

### 完整示例
```latex
\documentclass{article}
\usepackage[UTF8]{ctex} % 中文支持
\title{我的第一个LaTeX文档}
\author{Zixuan}
\date{\today} % 或指定日期：2025年1月8日
\begin{document}
\maketitle
\tableofcontents % 目录

\section{引言}
这是我的第一个LaTeX文档。

\section{正文}
这里是正文内容。

\end{document}
```

## 字体设置
```latex
\setmainfont{Times New Roman}
```

### 字体族
```latex
\textrm{罗马字体} % 或 {\rmfamily 罗马字体}
\textsf{无衬线字体} % 或 {\sffamily 无衬线字体}
\texttt{打字机字体} % 或 {\ttfamily 打字机字体}
```

### 字体形状
```latex
\textup{直立} % 或 {\upshape 直立}
\textit{意大利} % 或 {\itshape 意大利}
\textsl{倾斜} % 或 {\slshape 倾斜}
\textsc{小型大写} % 或 {\scshape 小型大写}
```

### 字体权重
```latex
\textmd{中等粗细} % 或 {\mdseries 中等粗细}
\textbf{粗体} % 或 {\bfseries 粗体}
```

### 字体大小
```latex
\tiny        % 最小
\scriptsize  % 很小
\footnotesize % 脚注大小
\small       % 小
\normalsize  % 正常（默认）
\large       % 大
\Large       % 更大
\LARGE       % 很大
\huge        % 巨大
\Huge        % 最大
```

## 数学公式

### 行内公式
```latex
这是行内公式：$a+b=c$，继续文本。
```

### 行间公式

**无编号**：
```latex
\[
    \alpha^2+\beta^2=\gamma^2
\]
```
或
```latex
$$\alpha^2+\beta^2=\gamma^2$$
```

**带编号**：
```latex
\begin{equation}\label{eq:pythagorean}
    \alpha^2+\beta^2=\gamma^2
\end{equation}
```

### 公式引用
自动引用```\autoref{公式标签}```（需要导入依赖包\usepackage{hyperref}）

```latex
根据公式~\eqref{eq:pythagorean} 或 \autoref{eq:pythagorean}
```
（需要 `\usepackage{hyperref}`）

### 多行公式
使用```\begin{split}...\end{split}```(需要导入依赖包\usepackage{amsmath},有的环境可能自带)

**对齐公式**：
```latex
\begin{align}
    a + b + c + d &= e + f + g \\
    &= h + i + j \\
    &= k
\end{align}
```

**拆分公式**（单个编号）：
```latex
\begin{equation}
\begin{split}
    a + b + c + d + e &= f + g + h + i \\
    &= j + k + l \\
    &= m
\end{split}
\end{equation}
```

### 分情况讨论
属于多行公式一种,使用```\begin{cases}... end{cases}```(需要导入依赖包\usepackage{amsmath},有的环境可能自带)

```latex
\begin{equation}
    F(x) = \begin{cases}
        0 & \text{若 } x < 0 \\
        x + 1 & \text{若 } x \geq 0 \\
        1 & \text{其他情况}
    \end{cases}
\end{equation}
```

### 常用数学符号

**上下标**：
```latex
x^{上标} % 上标
x_{下标} % 下标
x^{上标}_{下标} % 同时有上下标
```

**分式**：
```latex
\frac{分子}{分母} % 普通分式
\dfrac{分子}{分母} % 显示样式分式
\tfrac{分子}{分母} % 文本样式分式
```

**根式**：
```latex
\sqrt{被开方数} % 平方根
\sqrt[n]{被开方数} % n次根
```

**求和与求积**：
```latex
\sum_{i=1}^{n} x_i % 求和
\prod_{i=1}^{n} x_i % 求积
\int_{a}^{b} f(x) dx % 定积分
\oint_{C} f(z) dz % 环路积分
```

**向量**：
```latex
\vec{a} % 向量箭头
\overrightarrow{AB} % 从A到B的向量
\mathbf{v} % 粗体向量
```

**其他符号**：
```latex
\cdots % 横向省略号
\vdots % 竖向省略号
\ddots % 斜向省略号
\infty % 无穷大
\partial % 偏微分
\nabla % 梯度算子
```

**括号**：
```latex
\underbrace{表达式}_{说明} % 下括号
\overbrace{表达式}^{说明} % 上括号
\overline{表达式} % 上划线
\underline{表达式} % 下划线
```
常用数学符号的latex表示方法[https://mohu.org/info/symbols/symbols.htm]
AXMATH 软件

## 插入图片
依赖包graphicx(有的环境可能自带)
### 基本语法
```latex
\usepackage{graphicx} % 导言区添加

\begin{figure}[htbp]
    \centering
    \includegraphics[width=0.8\textwidth]{图片路径}
    \caption{图片标题}
    \label{fig:example}
\end{figure}
```

### 参数说明
[图片大小]
图片大小使用height和width规定,单位可以采用cm或in(inch),如果只规定高或宽其中一个,图片将保持高宽比插入,所以一般只需要规定图片宽度。

[图片路径]
图片相对于tex文件的路径，注意把'\' 换成 '/'

部分双栏显示的模板图片如果需要跨栏显示把```\begin{figure}... \end{figure}```替换为```\begin{figure*}... \end{figure*}```

**位置参数 [htbp]**：
- `h`：here，尽量放在当前位置
- `t`：top，页面顶部
- `b`：bottom，页面底部  
- `p`：page，单独一页
- `!`：忽略一些限制（如 `[!htb]`）

这些选项可以组合使用,例如ht表示首选放置在页面顶部,个但如果不行就放置在代码所在的位置。

默认情况下,如果你不提供任何选项,LaTeX会使用tbp作为默认值。

例如,\begin{figure}[htbp]表示在尽量放在当前位置,如果不行就放在页面顶部,底部,或者单独一页。


**图片大小设置**：
```latex
[width=0.5\textwidth] % 文本宽度的50%
[height=5cm] % 指定高度
[scale=0.8] % 按比例缩放
[width=8cm,height=6cm] % 同时指定宽高（可能变形）
```

### 子图
```latex
\usepackage{subcaption}

\begin{figure}[htbp]
    \centering
    \begin{subfigure}{0.45\textwidth}
        \includegraphics[width=\textwidth]{图片1}
        \caption{子图1}
        \label{fig:sub1}
    \end{subfigure}
    \hfill
    \begin{subfigure}{0.45\textwidth}
        \includegraphics[width=\textwidth]{图片2}
        \caption{子图2}
        \label{fig:sub2}
    \end{subfigure}
    \caption{总标题}
    \label{fig:main}
\end{figure}
```

### 跨栏图片（双栏文档）
```latex
\begin{figure*}[htbp]
    \centering
    \includegraphics[width=0.8\textwidth]{图片路径}
    \caption{跨栏图片}
    \label{fig:wide}
\end{figure*}
```

## 插入表格
```latex
\begin{table}[htb]表示Table的参数
```

### 基本表格
```latex
\begin{table}[htbp]
    \centering
    \caption{表格标题}
    \label{tab:example}
    \begin{tabular}{|c|c|c|}
        \hline
        \textbf{算法} & \textbf{复杂度} & \textbf{开销} \\
        \hline
        算法1 & 高 & 低 \\
        \hline
        算法2 & 高 & 低 \\
        \hline  
        算法3 & 低 & 低 \\
        \hline
    \end{tabular}
\end{table}
```

### 列对齐方式
```latex
\begin{tabular}{lcr} % 左对齐、居中、右对齐
\begin{tabular}{|l|c|r|} % 带竖线的版本
\begin{tabular}{p{3cm}|m{2cm}|b{2cm}} % 固定宽度列
```

**列类型说明**：
- `l`：左对齐
- `c`：居中对齐  
- `r`：右对齐
- `p{宽度}`：固定宽度，顶部对齐
- `m{宽度}`：固定宽度，中部对齐（需要array宏包）
- `b{宽度}`：固定宽度，底部对齐（需要array宏包）
- `&`:列分隔符
- `\\`:换行
- `\hline`:一条水平直线
- `\newline`:在单元格内(在段落列内)新建一行
- `|`：竖线
- `||`：双竖线

### 表格命令
```latex
& % 列分隔符
\\ % 换行
\hline % 水平线
\cline{i-j} % 从第i列到第j列的水平线
\multicolumn{列数}{对齐方式}{内容} % 合并列
\multirow{行数}{宽度}{内容} % 合并行（需要multirow宏包）
```

### 长表格
```latex
\usepackage{longtable}

\begin{longtable}{|c|c|c|}
\caption{长表格} \\
\hline
表头1 & 表头2 & 表头3 \\
\hline
\endfirsthead

\multicolumn{3}{c}{表格续} \\
\hline
表头1 & 表头2 & 表头3 \\
\hline
\endhead

\hline
\multicolumn{3}{r}{续下页} \\
\endfoot

\hline
\endlastfoot

数据1 & 数据2 & 数据3 \\
% 更多行...
\end{longtable}
```


工具：目前有很多Latex表格在线生成工具,可视化制作表格,生成LaTex代码

常用网站:
LaTeX表格编辑器(latex-tables.com)(支持excel导入)

在线创建LaTeX表格-TablesGenerator.com

## 参考文献

### 简单方法（手动输入）

**文中引用**：
```latex
根据文献\cite{ref1}和\cite{ref2}的研究...
```

**文末参考文献**：
```latex
\begin{thebibliography}{99}
\bibitem{ref1} 
作者. 文章标题[J]. 期刊名称, 年份, 卷号(期号): 页码.

\bibitem{ref2} 
作者. 书名[M]. 出版地: 出版社, 年份: 页码.
\end{thebibliography}
```

### BibTeX 方法（推荐）

**设置**：
```latex
% 导言区添加
\bibliographystyle{plain} % 或 alpha, unsrt, abbrv 等
```

**文中引用**：
```latex
根据研究\cite{author2019title}显示...
```

**文末添加**：
```latex
\bibliography{文献库文件名} % 不含.bib扩展名
```

**bib 文件示例**：
```bibtex
@article{author2019title,
  title={文章标题},
  author={作者姓名},
  journal={期刊名称},  
  volume={卷号},
  number={期号},
  pages={页码范围},
  year={2019},
  publisher={出版社}
}

@book{author2020book,
  title={书名},
  author={作者姓名},
  year={2020},
  publisher={出版社},
  address={出版地}
}
```

### 上标引用
```latex
% 导言区添加
\newcommand{\upcite}[1]{\textsuperscript{\cite{#1}}}

% 使用
根据研究\upcite{ref1}显示...
```

### 现代参考文献管理（Biblatex）
```latex
\usepackage[style=numeric,backend=biber]{biblatex}
\addbibresource{文献库.bib}

\begin{document}
根据\cite{ref1}的研究...
\printbibliography
\end{document}
```

## 列表环境

### 无序列表
```latex
\begin{itemize}
    \item 第一项
    \item 第二项
    \item 第三项
\end{itemize}
```

### 有序列表
```latex
\begin{enumerate}
    \item 第一项
    \item 第二项  
    \item 第三项
\end{enumerate}
```

### 描述列表
```latex
\begin{description}
    \item[术语1] 解释1
    \item[术语2] 解释2
    \item[术语3] 解释3
\end{description}
```

## 常用工具推荐

- **在线编辑器**：Overleaf
- **本地编辑器**：TeXstudio, VS Code + LaTeX Workshop
- **表格生成器**：
  - [LaTeX表格编辑器](https://www.latex-tables.com)
  - [TablesGenerator](https://www.tablesgenerator.com)
- **数学公式编辑**：AXMATH, MathType
- **符号查询**：[LaTeX符号大全](https://mohu.org/info/symbols/symbols.htm)
- **文献管理**：Zotero, Mendeley, EndNote

## 编译命令

```bash
# 基本编译
pdflatex 文档名.tex

# 包含参考文献的完整编译流程
pdflatex 文档名.tex
bibtex 文档名.aux  # 或 biber 文档名.bcf (使用biblatex时)
pdflatex 文档名.tex
pdflatex 文档名.tex

# 中文文档编译
xelatex 文档名.tex
```
