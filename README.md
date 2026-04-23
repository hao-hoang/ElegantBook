<!-- Author : Dongsheng Deng & Liam Huang & Ran Wang-->
<!-- Program Email: elegantlatex2e@gmail.com (inactive) & ranwang.osbert@outlook.com -->

[Github](https://github.com/ElegantLaTeX/ElegantBook) | [CTAN](https://ctan.org/pkg/elegantbook) | [Download](https://github.com/ElegantLaTeX/ElegantBook/releases) | 

![License](https://img.shields.io/ctan/l/elegantbook.svg) ![CTAN Version](https://img.shields.io/ctan/v/elegantbook.svg) ![Github Version](https://img.shields.io/github/release/ElegantLaTeX/ElegantBook.svg) ![Repo Size](https://img.shields.io/github/repo-size/ElegantLaTeX/ElegantBook.svg)

-------

# ElegantBook: 优美的 LaTeX 书籍模板 An Elegant LaTeX Template for Books 

ElegantBook 是为 LaTeX 书籍写作而设计的模板，由 [Ethan Deng](https://github.com/EthanDeng) 和 [Liam Huang](https://github.com/Liam0205) 创立，而后由 [Ethan Deng](https://github.com/EthanDeng)、[乙醇](https://github.com/syvshc)和[死抠](https://github.com/sikouhjw)维护。自2026年起，由[啸行](https://github.com/OsbertWang)负责维护和发行。如果你有其他问题、建议或者报告 bug，可以提交 issues 或者加入我们的 QQ 用户交流群：692108391。

ElegantBook is a template designed for LaTeX book writing, created by [Ethan Deng](https://github.com/EthanDeng) and [Liam Huang](https://github.com/Liam0205), and later maintained by [Ethan Deng](https://github.com/EthanDeng), [ethanol](https://github.com/syvshc), and [sikouhjw](https://github.com/sikouhjw). Since 2026, [Osbert Wang](https://github.com/OsbertWang) has been responsible for its maintenance and distribution. If you have any questions, suggestions, or need to report bugs, feel free to submit issues or join our QQ user group: 692108391.

**本模板自 2023 年 1 月 1 日起停止维护，并不建议使用，但鉴于用户群体庞大，自 2026 年起重新发布。为保证之前版本的用户仍能查阅说明文档，本说明文档保留了过往信息。**

**This template was discontinued as of January 1, 2023, and its use was not recommended. However, due to its large user base, it has been re-released since 2026. To ensure that users of previous versions can still access the documentation, this documentation retains past information.**

## 致谢 Acknowledgement

特别感谢 [sikouhjw](https://github.com/sikouhjw) 和 [syvshc](https://github.com/syvshc) 长期以来对于 Github 上 issue 的快速回应，以及各个社区论坛对于 ElegantLaTeX 相关问题的回复。特别感谢 ChinaTeX 以及 [LaTeX 工作室](http://www.latexstudio.net/)对于本系列模板的大力宣传与推广。

Thank [sikouhjw](https://github.com/sikouhjw) and [syvshc](https://github.com/syvshc) for their quick response to Github issues and continuously support work for ElegantLaTeX community. Thank ChinaTeX and [LaTeX Studio](http://www.latexstudio.net/) for their promotion. 

## 协议 License

本模板发布遵循 LaTeX 项目公共许可证 1.3 c 或更高版本。
如果是衍生作品，请务必加入协议声明和模板信息（github、CTAN 地址）。

This work is released under the LaTeX Project Public License, v1.3c or later.

## 衍生品 Derivative Works

+ [ElegantBookdown](https://github.com/XiangyunHuang/ElegantBookdown)：[XiangyunHuang](https://github.com/XiangyunHuang) 开发并维护的基于 ElegantBook 的 Bookdown 模板。
+ [bookdownplus](https://github.com/pzhaonet/bookdownplus)：应网友要求，[pzhaonet](https://github.com/pzhaonet) 在 bookdownplus 收录了 ElegantPaper 模板，并为 Mac 做了字体适配。
+ [PanBook](https://github.com/annProg/PanBook)：[annProg](https://github.com/annProg) 开发并维护的基于 Markdown 写作的工作流，收录了 ElegantBook 和 ElegantPaper 模板。

---

## Build / Render PDF (Local)

This repository contains two example sources:

- **English**: `elegantbook-en.tex`
- **Chinese**: `elegantbook-cn.tex` (recommended engine: **XeLaTeX**)

### 1) Install TeX distribution

- **Linux / WSL (recommended)**: install **TeX Live** (full or a reasonably complete scheme).
  - If you prefer minimal installs, make sure you have at least: `latexmk`, `xelatex`, `biber`, and common LaTeX packages.
- **macOS**: install **MacTeX**
- **Windows**: install **TeX Live**

### 2) Build with `latexmk` (recommended)

From the repo root:

```bash
# English PDF (XeLaTeX)
latexmk -xelatex -interaction=nonstopmode -file-line-error -synctex=1 elegantbook-en.tex

# Chinese PDF (XeLaTeX)
latexmk -xelatex -interaction=nonstopmode -file-line-error -synctex=1 elegantbook-cn.tex
```

Outputs will be `elegantbook-en.pdf` and/or `elegantbook-cn.pdf` in the same directory.

### 3) Clean build artifacts (optional)

```bash
latexmk -c
# or, remove everything latexmk generated:
latexmk -C
```

### 4) Manual build (if you don’t have `latexmk`)

Because this template uses **biblatex**, you usually need **biber**:

```bash
# Example: Chinese
xelatex -interaction=nonstopmode -file-line-error elegantbook-cn.tex
biber elegantbook-cn
xelatex -interaction=nonstopmode -file-line-error elegantbook-cn.tex
xelatex -interaction=nonstopmode -file-line-error elegantbook-cn.tex
```

(Same pattern for `elegantbook-en.tex`.)

### Troubleshooting

- **`biber: command not found` / bibliography not shown**: install `biber`, then rebuild.
- **Font-related errors in Chinese mode**: use **XeLaTeX** (as above) and ensure required system fonts are installed.
- **Missing package errors** (`.sty` not found): install the missing TeX Live packages (or install a fuller TeX Live scheme).
