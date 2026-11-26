# eScriptorium Studio v1.9

## English

### Added

- One-click **Export Word** action for a native Microsoft Word `.docx` file.
- Three retained texts for every manuscript line: original, cleansed and
  translated.
- Dedicated **Printed-text OCR** workspace for printed books, Fraktur,
  typescript and modern print.
- Umi-OCR HTTP integration with language discovery, page selection, preview and
  four-corner coordinate conversion.
- Optional Tesseract CLI backend with line reconstruction from TSV coordinates.
- One-click Umi-OCR and Tesseract download/installation with official SHA-256
  verification and an OpenSSL/curl download fallback.
- Native PDF processing through Umi-OCR document OCR, including extraction mode
  and page-range controls.
- Windows tablet/device preflight warnings for ARM, less than 8 GB RAM and less
  than 20 GB free disk space.
- Page-grouped Word tables with page-level contextual cleanse, page translation
  and a basic text-analysis appendix.
- Expanded in-app bilingual workflow guide for Word/CSV/TEI annotation,
  follow-up corpus analysis, and OCR/HTR processing.
- A generated Word sample under `samples/`.

### Verification

- Application self-test passed.
- Fixed a Word Open XML schema-order defect that caused Microsoft Word to report
  unreadable content.
- The generated `.docx` was reopened as an OOXML package and checked for the
  three text columns and page-context content.
- The corrected sample passes Microsoft's Open XML validator with zero schema
  errors and opens in desktop Microsoft Word.

## 中文

### 新增

- 新增一键 **导出 Word**，直接生成 Microsoft Word 原生 `.docx`。
- 每一行同时保留原文、清洗文和译文三段文字。
- 新增专门处理印刷书籍、Fraktur、打字稿和现代印刷文本的 **印刷文本 OCR**。
- 接入 Umi-OCR HTTP，可读取语言、选择页面、预览并把四角坐标转换为手稿坐标框。
- 提供可选 Tesseract CLI，并从 TSV 坐标重建文本行。
- 新增 Umi-OCR 与 Tesseract 一键下载安装，校验官方 SHA-256，并提供
  Python/OpenSSL 与 curl 下载回退。
- 通过 Umi-OCR 文档接口原生处理 PDF，可选择提取模式和页码范围。
- 安装页新增 Windows 平板/设备预检：ARM、内存低于 8 GB 或磁盘低于 20 GB
  时显示明确警告。
- Word 按手稿页组织表格，并附页面语境清洗、整页译文和基础文本分析。
- 软件内扩展中英文工作流说明，覆盖 Word/CSV/TEI 标注、后续语料分析和 OCR/HTR 操作。
- `samples/` 中增加可直接查看的 Word 示例。

### 验证

- 应用自检通过。
- 修复了导致 Microsoft Word 提示“内容不可读”的 Word Open XML 架构顺序错误。
- 生成的 `.docx` 已作为 OOXML 包重新读取，并确认三栏文字和页面语境内容存在。
- 修复后的示例通过 Microsoft Open XML 验证器（0 个架构错误），并已在
  桌面版 Microsoft Word 中实际打开。

### Notes / 说明

This non-commercial research build is not code-signed. Docker Desktop/WSL 2 and
the Microsoft Edge WebView2 Runtime are required.

本非商业研究版本未进行代码签名；需要 Docker Desktop/WSL 2 和 Microsoft Edge
WebView2 Runtime。
