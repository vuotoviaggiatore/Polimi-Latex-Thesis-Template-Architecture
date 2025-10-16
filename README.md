# Polimi-Latex-Thesis-Template-Architecture
A clean and simple PhD thesis LaTeX template for Politecnico di Milano (POLIMI), especially for architecture students.
# PhD Thesis LaTeX Template for Politecnico di Milano (Architecture)

A clean, simple, and modern LaTeX template for PhD theses at Politecnico di Milano (POLIMI). This template is particularly well-suited for students in architecture and related fields. It is based on the [masterproef-template by galgalesh](https://github.com/galgalesh/masterproef-template) and has been significantly tailored for POLIMI's context, with a focus on typography and structure.

一份简洁、现代的米兰理工大学（POLIMI）博士学位论文LaTeX模板。该模板尤其适合建筑学及相关领域的学生使用。它在 [masterproef-template by galgalesh](https://github.com/galgalesh/masterproef-template) 的基础上进行了大量本地化修改，更注重排版细节与结构。

**Author:** Siqi MIAO (缪思齐)  
**Year:** 2024

## Key Features (主要特性)

  * **Clean and Minimalist Design**: The template is intentionally kept simple and clean, avoiding unnecessary clutter. It's recommended to use it as is.
      * **简洁的设计**：模板刻意保持了干净整洁的风格，不建议进行删减。
  * **Bilingual Support**: Natively supports English, Chinese, and Italian content thanks to the `xeCJK` package.
      * **多语言支持**：通过 `xeCJK` 宏包，原生支持中、英、意三语内容。
  * **Professional Typography**: Uses Arial as the main font and SimSun for Chinese, ensuring readability and a professional look.
      * **专业的字体排版**：默认使用 `Arial` 作为西文主字体，`SimSun` (宋体) 作为中文主字体。
  * **Structured for Architecture Thesis**: The structure is optimized for architecture-related theses which are typically text- and image-heavy but do not contain extensive code blocks.
      * **为建筑学论文优化**：模板结构专为图文混排为主、代码块较少的建筑学论文进行了优化。
  * **Automated Lists**: Automatically generates the Table of Contents, List of Figures, List of Tables, and a Glossary of Acronyms.
      * **自动化目录**：自动生成总目录、图片列表、表格列表以及缩略语词汇表。

## How to Use (如何使用)

### 1\. Compilation (编译)

**This template MUST be compiled with `XeLaTeX`**. This is crucial for font and Unicode support (especially for Chinese characters). The bibliography should be managed with `BibTeX`.

**本模板必须使用 `XeLaTeX` 进行编译**，这是正确显示外挂字体和中文内容的关键。文献管理请使用 `BibTeX`。

Typical compilation workflow (典型的编译流程):

1.  `XeLaTeX`
2.  `BibTeX`
3.  `XeLaTeX`
4.  `XeLaTeX`

### 2\. File Structure (文件结构)

  * `main.tex`: The main file. All document settings and chapter inclusions are managed here.
      * **主文件**。所有的文档设置、宏包调用和章节引入都在这里管理。
  * `personal_data.tex`: Input your personal information here, such as thesis title, author name, supervisor, etc.
      * **个人信息文件**。在此处填写论文标题、作者、导师等信息。
  * `bibliography.bib`: Your BibTeX database file. Add all your references here.
      * **文献数据库**。将您所有的参考文献条目添加到此文件中。
  * `/FrontBackmatter`: Contains files for the front matter of the thesis.
      * `/FrontBackmatter`：存放论文**前言部分**的文件。
      * `Abstract.tex`: Write your abstract here. (摘要)
      * `definitions.tex`: Define your acronyms for the glossary here. (术语/缩写定义)
  * `/chapters`: Contains the main content of your thesis.
      * `/chapters`：存放论文**主体章节**的文件。
      * `chapter1.tex`, `chapter2.tex`, etc.: Your thesis chapters. (论文章节)
      * `bibliography.tex`: This file loads the bibliography style and file. You generally don't need to edit this. (加载参考文献)
  * `/Images`: Place all your figures and images in this folder.
      * `/Images`：存放您所有**图片**的文件夹。

### 3\. Important Notes (重要提示)

  * **Chapter Filenames**: Chapter `.tex` filenames should not contain spaces, as it may cause issues with BibTeX compilation.
      * **章节文件名**：章节的 `.tex` 文件名中**不能包含空格**，否则可能导致 `BibTeX` 编译失败。
  * **Cover Page**: The front cover page needs to be added separately, for example, as a PDF include.
      * **封面**：首页的封面需要您单独制作并加入，例如使用 `\includepdf` 命令插入一个设计好的PDF封面。

## Source Code Preview (`main.tex`)

\<details\>
\<summary\>Click to expand/collapse the main template code\</summary\>

```latex
% PHD thesis template for POLIMI 中英文版本 (2024) by Siqi MIAO （缪思齐）
% 确保使用XeLaTeX，BibTeX编译。
% chapter文件名不能有空格，有空格无法出bib.bbl
% 在该模板的基础上完成：https://github.com/galgalesh/masterproef-template
% 第一页封皮需要单独加上。
% 适合建筑学论文（不支持代码）。
% 该模板非常干净简洁，不建议做任何删减。

\documentclass[12pt,a4paper,openany,italian,chinese,english]{extbook}
\usepackage[a4paper,includeheadfoot,margin=2.50cm]{geometry}
\usepackage{xeCJK}
\setCJKmainfont{SimSun} % 设置中文主字体为宋体
\usepackage{fontspec} %可以有外加字体
\setmainfont{Arial} %设置论文字体
\raggedbottom
\renewcommand{\baselinestretch}{1.2}  % 调整行间距
\usepackage{amsmath}%丰富的数学符号和公式排版功能
\usepackage{amsfonts} 
\usepackage[hyphens]{url} % 允许URL换行，可以在URL中自动添加连字符。
\usepackage{graphicx} % 支持图像插入。
\graphicspath{{Images/}} % 设置图像的默认搜索路径。
\usepackage{pdfpages} % 允许包含整个或部分PDF页面。
\usepackage{pdflscape}
\usepackage{svg} 
\usepackage{enumitem} % 提供更多控制列表（项目符号、编号等）布局的选项。
\usepackage{float} % 提高浮动对象（如图表和图片）的定位控制。
\usepackage{caption} % 提供更多自定义图表标题样式的选项。
\usepackage{subcaption} % 支持子图表和子标题。
\captionsetup[table]{labelfont=bf}%所有caption加粗
\captionsetup[figure]{labelfont=bf}
\usepackage{rotating} % 导入旋转包
%目录
\usepackage[toc,page]{appendix} % 改进附录的管理，包括在目录中的显示。
\usepackage{tocloft} % 提供自定义目录、图表列表和表格列表外观的选项。
\setlength{\cftsecindent}{0pt} % 设置章节在目录中的缩进为0。
\setlength{\cftsubsecindent}{0pt} % 设置小节在目录中的缩进为0。
\setlength{\cftfigindent}{0pt} % 设置图表列表中的图表缩进为0。
\setlength{\cfttabindent}{0pt} % 设置表格列表中的表格缩进为0。
\usepackage{parskip} % 在段落之间添加空间，并取消首行缩进。
\usepackage{lipsum} % 生成随机的Lorem Ipsum文本。
\usepackage{siunitx}%可以在文档中使用\num{}命令了。
\urlstyle{same} % URL使用文档的主字体样式。
\usepackage{color} % 支持颜色。
\definecolor{chaptergrey}{rgb}{0.447, 0.561, 0.647} % 章节数字POLIMI标准色
\usepackage[explicit, pagestyles]{titlesec} % 自定义章节标题和页样式。
\titleformat{\chapter}[display]{\bfseries}{\color{chaptergrey}\fontfamily{pbk}\fontsize{80pt}{100pt}\selectfont\thechapter}{0pt}{\Huge #1}
\titlespacing*{\chapter}{0pt}{-80pt}{30pt} % 自定义章节标题的外观。
\newpagestyle{fancy}{} % 定义一个新的页面样式。
\pagestyle{fancy} % 应用定义的页面样式。
\newpagestyle{numberless}{} % 定义一个无页码的页面样式。
%引用
\PassOptionsToPackage{hyphens}{url} % 向url包传递选项，允许URL自动换行。
\usepackage{hyperref} %交叉引用
\usepackage{cleveref}
\usepackage{csquotes}%\blockquote引用
\crefname{figure}{Figure}{Figures}
\crefname{table}{Table}{Tables}
\usepackage[super]{natbib} % 使用数字风格的文献引用。
\setcitestyle{super,open={},close={}} % 设置引用为上角标，且不使用括号
\bibliographystyle{abbrv} % 文献引用样式设置。
\usepackage[nottoc]{tocbibind} % 将目录、图表列表、表格列表等加入到目录中，但不包括目录本身。
\usepackage{tikz} % 提供创建图形（如绘图、图表、图形）的强大工具。
%表格
\usepackage{tabularx}
\usepackage{caption}  % 导入 caption 宏包
\captionsetup[table]{justification=raggedright, singlelinecheck=false} % 左对齐表格标题
\usepackage{multirow} % 为了使用 multirow 命令
\usepackage{booktabs} % 提供美观的表格线命令（顶线、底线等）。
\usepackage{threeparttable}
\usepackage{array} % 提供额外的表格选项，比如列格式定义。
\renewcommand{\arraystretch}{0.85} % 将行间距设置为默认的0.85倍
\usepackage{longtable}
\usepackage{threeparttablex}%longtable上可以加注释
\AtBeginEnvironment{table}{\footnotesize}%表格字号
\AtBeginEnvironment{tabular}{\footnotesize}
\AtBeginEnvironment{tabularx}{\footnotesize}
\AtBeginEnvironment{threeparttablex}{\footnotesize}
\AtBeginEnvironment{threeparttable}{\footnotesize}
\AtBeginEnvironment{booktabs}{\footnotesize}
\AtBeginEnvironment{longtable}{\footnotesize}
\usepackage{ragged2e} % 提供更灵活的对齐方式，如两端对齐。
\newcolumntype{L}[1]{>{\raggedright\let\newline\\arraybackslash\hspace{0pt}}m{#1}} % 定义一个新的列类型，用于左对齐文本。
\newcolumntype{C}[1]{>{\centering\let\newline\\arraybackslash\hspace{0pt}}m{#1}} % 定义一个新的列类型，用于居中对齐文本。
\newcolumntype{R}[1]{>{\raggedleft\let\newline\\arraybackslash\hspace{0pt}}m{#1}} % 定义一个新的列类型，用于右对齐文本。
%术语表
\usepackage[nomain,acronym]{glossaries}%只使用\newacronym定义的缩写
\makeglossaries % 初始化术语表处理。
\loadglsentries{FrontBackmatter/definitions.tex} % 引入术语定义文件
\input{personal_data} % 引入个人信息文件，通常包含论文标题、作者等信息。

\begin{document}
%前言
    \frontmatter % 文档前言部分，页码使用罗马数字。
    \pagestyle{empty} % 前言部分页面样式为空（不显示页眉页脚）。
    \cleardoublepage\include{FrontBackmatter/Abstract}
    \tableofcontents\newpage % 生成目录并开始新一页。
    \listoffigures\newpage % 生成插图目录并开始新一页。
    \listoftables\newpage % 生成表格目录并开始新一页。
    \printglossaries\newpage
    \mainmatter % 文档主体部分，页码使用阿拉伯数字。
    \pagestyle{fancy} % 主体部分使用自定义的页眉页脚样式。
    
% 引入更多章节文件。
    \include{chapters/chapter1} 
    \include{chapters/chapter2} 
    \include{chapters/chapter3}
% ...
%%%附录   
    \include{chapters/bibliography} % 参考文献。
    \pagestyle{numberless} % 附录部分使用无页码样式。
    \pagestyle{empty} % 选择一个页面样式。

\end{document} % 文档结束。
```

\</details\>

## Copyright Notice (版权声明)

Copyright (c) 2024 Siqi MIAO. All Rights Reserved.

All code, documentation, and related resources in this repository are the property of the author. Without the author's explicit written permission, no one may copy, modify, distribute, or use them for any commercial purpose.
