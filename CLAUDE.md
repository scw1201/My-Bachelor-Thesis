# BUAAthesis

北京航空航天大学毕业论文 LaTeX 模板，由北航开源俱乐部维护。

## 项目结构

```
buaathesis.cls          # 核心文档类文件
data/                   # 论文内容章节
  chapter*.tex          # 各章节正文
  abstract.tex          # 摘要
  bibs.bib              # 参考文献数据库
  reference.tex         # 参考文献配置
  appendix*.tex         # 附录
  com_info.tex          # 封面信息
  conclusion.tex        # 结论
  bachelor/             # 本科专用内容
  master/               # 硕士专用内容
figure/                 # 图片资源
sample-bachelor.tex     # 本科论文示例主文件
sample-master.tex       # 硕士论文示例主文件
sample-kaitireport.tex  # 开题报告示例主文件
gbt7714*.bst / gbt7714.sty  # GB/T 7714 参考文献样式
Makefile                # 构建脚本
msmake.bat              # Windows 构建脚本
```

## 构建命令

```bash
make bachelor      # 编译本科论文（默认）
make master        # 编译硕士论文
make kaitireport   # 编译开题报告
make clean         # 删除中间文件（保留 PDF）
make depclean      # 删除所有生成文件（含 PDF）
```

编译链：`xelatex → bibtex → xelatex → xelatex`

VS Code 用户使用 `xelatex->bibtex->xelatex*2` 方式编译。

## 依赖

- **LaTeX 发行版**：TeXLive 2019+（推荐）或 CTeX 2.9.3
- **ctex 包**：v2.0 及以上
- **字体**（非 Windows 环境需手动安装）：
  - Times New Roman
  - STXingKai、STKaiTi、SimSun、SimHei

## 文档类选项

在主 `.tex` 文件中通过 `\documentclass` 传入：

| 选项 | 说明 |
|------|------|
| `bachelor` | 本科论文 |
| `master` | 硕士论文 |
| `doctor` | 博士论文 |
| `professional` | 专业学位 |
| `color` | 电子版彩色链接 |
| `twoteacher` | 双导师 |
| `ktreport` | 开题报告 |

## 参考文献

格式遵循 GB/T 7714-2005。在 `data/reference.tex` 中切换排序方式：
- 按出现顺序（默认）：`\bibliographystyle{gbt7714-numerical}`
- 按作者姓名和年份：`\bibliographystyle{gbt7714-author-year}`
