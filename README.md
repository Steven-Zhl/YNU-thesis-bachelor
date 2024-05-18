# YNU-thesis-bachelor

[![Sync to Gitee](https://github.com/Astro-Lee/YNU-thesis-bachelor/actions/workflows/Sync%20to%20Gitee.yml/badge.svg)](https://gitee.com/Astro-Lee/YNU-thesis-bachelor) 
[![Compile LaTeX document](https://github.com/Astro-Lee/YNU-thesis-bachelor/actions/workflows/Compile%20LaTeX%20document.yml/badge.svg)](https://github.com/Astro-Lee/YNU-thesis-bachelor/actions/workflows/Compile%20LaTeX%20document.yml)
![Repo Size](https://img.shields.io/github/repo-size/Astro-Lee/YNU-thesis-bachelor?label=Repo%20size)

## 编者按

> 这一小节内容并非来自原作者，而是我在使用该模板撰写毕业论文时发现的一些注意事项。根据使用反馈，除了以下问题之外，该模板可以完全满足云南大学本科毕业论文的要求。

- 关于**参考文献著录格式**的问题：
  - 根据[《云南大学本科毕业论文(设计)写作规范(试行)》](https://github.com/Astro-Lee/YNU-thesis-bachelor/releases/download/v0.0.1/pre-release.pdf)中的规定，参考文献格式参考自[GB/T 7714-2015](https://lib.tsinghua.edu.cn/wj/GBT7714-2015.pdf)。在当前LaTeX模板中，参考文献的格式由[gbt7714-numerical.bst](./references/gbt7714-numerical.bst)(v2.1.3)实现，但其中文献期刊名的样式为斜体。
  - 由于国标中并未规定字体及样式，因此这种情况并不算错。但无论是[GB/T 7714-2015](https://lib.tsinghua.edu.cn/wj/GBT7714-2015.pdf)还是[云南大学本科毕业论文（设计）写作模板](https://github.com/Astro-Lee/YNU-thesis-bachelor/files/15282806/default.docx)中，参考文献的示例均为正体，因此是否采用斜体请以导师意见为准。
  - 如不希望以斜体强调期刊名，可换用[gbt7714-numerical-v216.bst](./references/gbt7714-numerical-v216.bst)(v2.1.6)，在该版本中参考文献已均为正体。
  - 换用方法为将[YNUbachelor.cls](./YNUbachelor.cls)中，`\bibliographystyle{references/gbt7714-numerical.bst}%gbt7714-author-year,gbt7714-numerical`中的文件名改为`gbt7714-numerical-v216.bst`。或者直接把[gbt7714-numerical-v216.bst](./references/gbt7714-numerical-v216.bst)重命名为gbt7714-numerical.bst。
- 关于**封底页码**的问题：
  - 在当前LaTeX模板中存在封底页，但[《云南大学本科毕业论文(设计)写作规范(试行)》](https://github.com/Astro-Lee/YNU-thesis-bachelor/releases/download/v0.0.1/pre-release.pdf)中并未对其是否编入页码作出规定，目前是计入页码的。但按照规定，归档的论文中封面和封底由学校发放，也许不应当计入页码，因此这部分同样以导师意见为准。
  - 若不希望封底计入页码，最简单的方法是直接在[main.tex](./main.tex)中注释掉位于文末的`\backcover%封底`一行。

## 联系方式
邮箱：liruizhi0871[AT]gmail.com

## 介绍
云南大学本科毕业论文(设计) LaTeX 模板根据[《云南大学本科学生毕业论文(设计)工作要求及规范》](http://www.jwc.ynu.edu.cn/info/1003/2052.htm)和[《云南大学本科毕业论文(设计)写作规范(试行)》](https://github.com/Astro-Lee/YNU-thesis-bachelor/releases/download/v0.0.1/pre-release.pdf)编写，**个人能力、精力有限，不保证完全符合规范！此外，该模板未经学校官方核准，如有顾虑，请不要使用！**

## 建议
- 入门推荐阅读[lshort-zh-cn](http://mirrors.ctan.org/info/lshort/chinese/lshort-zh-cn.pdf)
- 任务期限在三个月以内不推荐新手使用 LaTeX


## 编辑
### [在线：Overleaf](https://cn.overleaf.com/login)
### [本地：安装发行版软件](http://mirrors.ctan.org/info/install-latex-guide-zh-cn/install-latex-guide-zh-cn.pdf) + [Visual Studio Code 编辑器](https://code.visualstudio.com/) + LaTeX Workshop 插件

在Visual Studio Code中使用快捷键`Ctrl+p`调出搜索框，搜索`settings.json`，并在其中添加如下代码：
```json
"latex-workshop.view.pdf.viewer":"tab",
"latex-workshop.view.pdf.internal.synctex.keybinding": "double-click",
"latex-workshop.intellisense.package.enabled": true,
"latex-workshop.latex.autoClean.run": "onFailed",
"latex-workshop.message.error.show": false,
"latex-workshop.message.warning.show": false,

"latex-workshop.latex.recipes": [
    {
      "name": "latexmk 🔃",
      "tools": ["latexmk"]
    },],

"latex-workshop.latex.tools": [
    {
        "name": "latexmk",
        "command": "latexmk",
        "args": [],
        "env": {}
    },],
```
更多配置参考[LaTeX Workshop WiKi](https://github.com/James-Yu/LaTeX-Workshop/wiki/)。

## 编译
仅支持**XeLaTeX**编译器，可使用 [latexmk](https://zhuanlan.zhihu.com/p/256370737) 命令进行编译：
- 编译命令：`latexmk`
- 清除编译过程中产生的辅助文件：`latexmk -c`

## PDF转Word
 可使用 [Adobe PDF to Word](https://www.adobe.com/acrobat/online/pdf-to-word.html) 转换 `*.pdf` 文件。第二次转换文件时需要登录 Adobe 账号才能下载，建议在浏览器的“无痕浏览”、“隐私模式”等模式下访问以跳过强制登录(via. [hnuthesis](https://github.com/yusanshi/hnuthesis))。

## 压缩PDF文件
[![压缩PDF文件](https://www.ilovepdf.com/img/ilovepdf.svg)](https://www.ilovepdf.com/zh-cn/compress_pdf)

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=Astro-Lee/YNU-thesis-bachelor,Astro-Lee/YNUthesis&type=Date)](https://star-history.com/#Astro-Lee/YNU-thesis-bachelor&Astro-Lee/YNUthesis&Date)

