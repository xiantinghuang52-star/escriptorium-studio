# eScriptorium Studio

English / 中文

A bilingual Windows installer and manuscript workbench for local
eScriptorium, early modern European manuscripts, HTR export alignment and
page-node AI translation.

一个用于本地 eScriptorium 的中英双语 Windows 安装器和手稿工作台，支持早期现代
欧洲语言、HTR 导出对齐和按页语境翻译。

## Latest release / 最新版本

- [GitHub Release 1.8](https://github.com/xiantinghuang52-star/escriptorium-studio/releases/tag/v1.8)
- [Windows EXE 1.8](https://github.com/xiantinghuang52-star/escriptorium-studio/releases/download/v1.8/eScriptorium-Studio-Setup-EN-ZH-v1.8.exe)
- [Complete package 1.8](https://github.com/xiantinghuang52-star/escriptorium-studio/releases/download/v1.8/eScriptorium-Studio-Bilingual-Windows-v1.8.zip)
- [Source and documentation 1.8](https://github.com/xiantinghuang52-star/escriptorium-studio/releases/download/v1.8/eScriptorium-Studio-Source-and-Docs-v1.8.zip)
- [Release notes 1.8](https://github.com/xiantinghuang52-star/escriptorium-studio/releases/download/v1.8/RELEASE-NOTES-v1.8-EN-ZH.md)
- [SHA-256](https://github.com/xiantinghuang52-star/escriptorium-studio/releases/download/v1.8/SHA256SUMS-v1.8-RELEASE.txt)

## Highlights

- Install/start Docker Desktop and eScriptorium on `http://localhost:8080/`.
- Use an embedded WebView2 mirror of the local eScriptorium page.
- Select an eScriptorium Recognition/HTR model and upload Kraken `.mlmodel` files.
- Submit text-line segmentation and HTR for the document open in the mirror.
- Import ALTO XML and PAGE XML with line numbers and coordinate boxes.
- Generate page-node contextual cleansing and aligned English translations.
- Use language-aware handling for OCR confusion among `l`, `f`, `s` and `ſ`.
- Export aligned CSV, JSON and TEI.
- Bilingual English/Chinese interface and AI error codes `AIC001`–`AIC017`.

## 主要功能

- 安装 Docker Desktop，并在 `http://localhost:8080/` 部署 eScriptorium。
- 使用 WebView2 内嵌本地 eScriptorium 页面。
- 选择 eScriptorium Recognition/HTR 模型，并上传 Kraken `.mlmodel`。
- 对镜像中当前打开的文档提交文本行检测和 HTR。
- 导入带行号和坐标框的 ALTO XML、PAGE XML。
- 按页生成语境清洗和逐行对齐的英文译文。
- 针对 `l`、`f`、`s`、`ſ` 的 OCR 混淆进行语言感知消歧。
- 导出 CSV、对齐 JSON 和 TEI。
- 中英双语界面及 `AIC001`–`AIC017` AI 报错码。

## Build

```powershell
powershell -ExecutionPolicy Bypass -File .\work\build.ps1
```

The build uses the C# compiler included with Windows .NET Framework 4.8 and
writes the executable to `outputs/`.

## Project layout

```text
work/src/       C# source
work/build.ps1  build script
work/assets/    executable icon
outputs/        latest EXE, ZIP, documents and samples
```

## Security

API keys and generated eScriptorium passwords are stored in the local Windows
user profile, not in this repository. Runtime logs, settings and temporary
diagnostic files are excluded by `.gitignore`.

API Key 和 eScriptorium 密码只保存在 Windows 用户本机配置中，不写入此仓库。
运行日志、设置和临时诊断文件均由 `.gitignore` 排除。

## Non-commercial use / 非商业用途

This personal project is intended for non-commercial research and study. Its
workflow was informed by Archive Studio (CC BY-NC 4.0); no Archive Studio source
code is included. The EXE is not code-signed.

本项目面向非商业研究和个人学习。工作流参考 Archive Studio（CC BY-NC 4.0），
未包含其源代码。EXE 尚未进行代码签名。
