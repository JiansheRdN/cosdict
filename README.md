# cosdict

A concise in-game glossary / dictionary for the five constructed languages in the game **Chants of Sennaar** (《巴别塔圣歌》), typeset in XeLaTeX.

一本《巴别塔圣歌》游戏中五种虚构语言的简明字典，使用 XeLaTeX 排版。

---

## Download the compiled dictionary / 下载编译成品

Please refer to each [Release](../../releases) to download the attached compiled .pdf document. The source tree is provided for those who would like to compile the glossary themselves only. 

`.pdf` 编译成品文件附在各版 [Release](../../releases) 下供下载。如欲本地编译请看本仓库的 source tree。

---

## Repository layout / 仓库结构

```
cosdict/
├── common/              Shared assets for every edition / 各语言版本共用资源
│   ├── cosdict.sty      The layout package / 版式宏包
│   ├── fonts/
│   │   └── COSGlyphs.otf The game-glyph font / 游戏字符字体
│   └── img/             All figures and radical images / 全部插图与部首或义符图片
└── zh/                  Chinese edition / 中文版
    └── main.tex
```

Each translation lives in its own top-level folder (`zh/`, and future `en/`, …) and shares everything in `common/`. All paths inside the source are written relative to `common/`.

每个译本放在各自的顶层文件夹里（`zh/`，将来的 `en/` …），并共用 `common/` 中的内容。源码中的路径都相对于 `common/`。

---

## Building from source / 从源码编译

XeLaTeX is required for compilation. (as the document uses `fontspec`/`ctex`). Run it **twice** to resolve the table of contents, the character index page/line references, and the running heads. 

请使用 XeLaTeX（文档使用 `fontspec`/`ctex`）编译。需编译两次以生成目录、检字表的“页-行”引用和页眉。

```bash
cd zh
xelatex main.tex
xelatex main.tex
```

(A full TeX Live or MiKTeX installation provides the required packages (`ctex`, `fontspec`, `zref`, `titlesec`, `tcolorbox`, `multicol`, `pifont`, …).)

（本文档所需宏包（`ctex`、`fontspec`、`zref`、`titlesec`、`tcolorbox`、`multicol`、`pifont`、……）为 TeX Live 或 MiKTeX 预装宏包。）

### Fonts / 字体

Due to mispresence of the formal consense or `LICENSE`ing from the author of `COSGlyphs.otf`, this required font is not uploaded in the source tree, so you must put this file under `common/fonts/` before compilation. Its repository link: <https://github.com/Wolceorght/COSGlyphs>. The document also uses these system fonts, which are not redistributed here: 

由于本文档所需的 `COSGlyphs.otf` 字体缺乏 `LICENSE`，该字体需要用户自行安装，并放在 `common/fonts/` 目录下。（其仓库地址：<https://github.com/Wolceorght/COSGlyphs>）本文档还用到以下不包含本仓库中的系统字体，编译前请自行安装（随 Windows / Microsoft Office 预装）：

| Role / 用途 | Font / 字体 |
|---|---|
| Latin body & titles / 西文正文与标题 | Times New Roman |
| CJK body / 中文正文 | SimSun 宋体 |
| Emphasis / 强调 | SimHei 黑体 |
| Titles / 标题 | STZhongsong 华文中宋 |
| Example glosses / 例句译文 | KaiTi 楷体 |
| Line numbers / 行号 | Arial |
| Index symbols (⌵ ⫯ △) / 检字表符号 | Segoe UI Symbol |

---

## Font attribution & Licence / 字体署名与许可

- The game-glyph font **COSGlyphs** is the work of **Wolceorght** and comes from its own project: <https://github.com/Wolceorght/COSGlyphs>. It is redistributed here for convenience with attribution; please refer to the upstream project for its terms of use and consider supporting the original author.

  游戏字符字体 **COSGlyphs** 由 **Wolceorght** 制作，来自其项目 <https://github.com/Wolceorght/COSGlyphs>。此处为方便读者附带提供并署名，其使用条款请以上游项目为准，并请支持原作者。

- **Text and compiled dictionary content** (definitions, grammar notes, index, typesetting) are released under **CC BY-NC-SA 4.0**.

  字典的**文字内容**（释义、语法说明、检字表、版式）采用 **CC BY-NC-SA 4.0** 协议发布。
- The **names, glyphs, and in-game screenshots** of *Chants of Sennaar* belong to their respective rights holders (**Rundisc** / **Focus Entertainment**). This is an unofficial, fan-made work with no affiliation to them.

  《巴别塔圣歌》的**名称、游戏字形及游戏截图**的权利归原权利人（**Rundisc** / **Focus Entertainment**）所有。本书为玩家自制的非官方资料，与其无任何关联。
- **COSGlyphs** font is governed by its upstream project, not by this licence.

  借用的的 **COSGlyphs** 字体以其上游项目为准，不受本许可约束。

---

## Credits / 编写

- Written and compiled by **JiansheRdN（建设北路）**, 2026, Malta.

  由 **建设北路（JiansheRdN）** 编写，2026 年，马耳他。

- `.sty` package by Claude AI.

  `.sty` 宏包由 Claude AI 编写。

- Corrections and suggestions are welcome via Issues.

  欢迎通过 Issue 提出勘误与建议。
