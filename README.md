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

## Copyright Notice (版权声明)

Copyright (c) 2024 Siqi MIAO. All Rights Reserved.

All code, documentation, and related resources in this repository are the property of the author. Without the author's explicit written permission, no one may copy, modify, distribute, or use them for any commercial purpose.
