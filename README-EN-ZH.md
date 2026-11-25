# eScriptorium Studio · EN / 中文

`eScriptorium-Studio-Setup-EN-ZH-v1.6.exe` is a portable Windows installer and
coordinate-aware manuscript workbench for eScriptorium.

`eScriptorium-Studio-Setup-EN-ZH-v1.6.exe` 是一个便携式 Windows 安装器与
坐标感知手稿工作台，用于部署和使用 eScriptorium。

## Version 1.6

- Language-aware cleansing now treats OCR `l`, `f`, `s` and long s `ſ` as
  potentially ambiguous rather than a global substitution.
- The AI page prompt uses detected language, function words, morphology and
  neighboring lines to resolve suspicious tokens.
- High-confidence local corrections are applied after the AI response, while
  ambiguous forms remain unchanged for editorial review.
- Up to two page nodes are processed concurrently.
- For DeepSeek endpoints, thinking mode is disabled and JSON response format is
  requested when supported, reducing latency.
- Page translation and contextual cleanse punctuation are normalized.

## 1.6 版本

- 语境清洗把 OCR 的 `l`、`f`、`s` 和长 s `ſ` 视为潜在混淆项，而不是全局替换。
- AI 页面提示词会结合检测语言、功能词、词法和相邻行判断可疑词。
- AI 返回后再应用高置信度本地修正；模糊词保持原样供人工审阅。
- 最多同时处理两个页面节点。
- DeepSeek 接口关闭思考模式，并在支持时请求 JSON 输出格式，以减少延迟。
- 整页译文和语境清洗文本会规范化标点间距。

### Version 1.5 history

- Page-node translation replaces the previous whole-document chunk merge.
- Each manuscript page is sent as one contextual AI request.
- A single page request returns:
  - contextual cleansing for the whole page;
  - one coherent page translation;
  - cleaned and translated text for every input line ID.
- Page numbers are marked in both the contextual cleanse and translation output.
- ALTO pages and separately imported page files are numbered as distinct nodes.
- Page-node results are written to JSON and TEI with explicit page numbers.
- This is faster than running line-by-line and document translation separately,
  while preserving every line ID and coordinate box.

### 1.5 版本记录

- 按页节点翻译取代上一版的全文分块合并模式。
- 每一页手稿作为一个语境节点，只发送一次 AI 请求。
- 单页请求同时返回：
  - 整页语境清洗文本；
  - 一份连贯的整页译文；
  - 每个输入行号对应的清洗文本和译文。
- 语境清洗和译文输出都会标记 PAGE 页码。
- ALTO 多页文件和分别导入的页面文件都会分配独立页码节点。
- JSON 和 TEI 导出包含带明确页码的页面节点结果。
- 相比分别运行逐行翻译和全文翻译更快，同时保留全部行号与坐标框。

### Version 1.4 history

- The default translation target is now **English / 英语**.
- Existing installations using the previous Chinese default are migrated once;
  users can still select Chinese manually.
- Added a **Context translation / 全文语境翻译** tab.
- Adjacent line IDs are translated as connected passages, then overlapping
  passages are merged into one coherent full-document translation.
- Whole-document translation is included in aligned JSON and TEI exports.
- The table remains line-aligned with original coordinate boxes; contextual
  translation does not replace or merge coordinate rows.

### 1.4 版本记录

- 默认翻译目标语言改为 **英语 / English**。
- 使用旧中文默认值的现有安装会迁移一次；用户仍可在设置中手动选择中文。
- 新增 **全文语境翻译 / Context translation** 标签页。
- 相邻行号会作为连续段落翻译，重叠段落随后合并为一份连贯的全文译文。
- 全文译文会写入逐行对齐 JSON 和 TEI 导出。
- 表格仍保持逐行对齐和原坐标框；全文语境翻译不会替换或合并坐标行。

### Version 1.3 history

- When Windows .NET HTTPS fails with `AIC004`, the app automatically retries the
  same request through a local Python/OpenSSL HTTPS client.
- If the fallback is unavailable or fails, the UI reports `AIC017` with
  bilingual reasons.
- The fallback reads the API key from standard input only. It is not written to
  command-line arguments, logs or the fallback script.
- AI errors continue to use `AIC001`–`AIC017` with English and Chinese
  explanations.

### 1.3 版本记录

- Windows .NET HTTPS 出现 `AIC004` 时，软件自动使用本机 Python/OpenSSL
  客户端重发同一请求。
- 如果回退不可用或执行失败，界面会以中英双语说明 `AIC017`。
- 回退通道仅通过标准输入读取 API Key，不写入命令行参数、日志或回退脚本。
- AI 错误继续使用 `AIC001`–`AIC017` 报错码，并显示中英文原因。

### Version 1.2 history

- AI failures now use stable `AIC001`–`AIC016` error codes.
- Every AI error dialog includes an English explanation, a Chinese explanation
  and a technical detail section.
- Authentication, endpoint, model, quota, timeout, TLS, connection and response
  format failures are classified separately.
- The built-in workflow guide includes the complete bilingual error-code table.

### 1.2 版本记录

- AI 故障现在使用固定的 `AIC001`–`AIC016` 报错码。
- 每个 AI 错误弹窗同时显示英文原因、中文原因和技术详情。
- 鉴权、接口、模型、额度、超时、TLS、连接及响应格式错误分别分类。
- 软件内工作流说明增加了完整的中英双语报错码表。

### Version 1.1 history

- Fixed the `index` / “索引超出范围” error shown after an AI request failed.
- Failed AI operations no longer trigger the success-only page refresh.
- The line table is selected only after data binding has completed.
- Added in-app guidance for selecting segmentation and HTR models.
- Added guidance that the eScriptorium login and AI provider API key are
  separate credentials.

### 1.1 版本记录

- 修复 AI 请求失败后出现的 `index` /“索引超出范围”错误。
- AI 失败后不再执行只应在成功时进行的页面刷新。
- 仅在表格数据绑定完成后选择第一行。
- 在软件内增加区域检测模型和 HTR 模型选择说明。
- 明确 eScriptorium 登录账号与 AI 服务商 API Key 是两套独立凭据。

## What it installs

- Windows Subsystem for Linux 2 (WSL 2), when missing
- Docker Desktop with its WSL 2 backend
- A pinned local eScriptorium Compose stack on `http://localhost:8080/`
- A generated administrator password, protected on disk with Windows DPAPI
- A bilingual workspace for ALTO XML / PAGE XML import, line-aligned AI
  cleaning and translation, text analysis, and TEI/JSON/CSV export

## 安装内容

- 缺失时安装 Windows Subsystem for Linux 2（WSL 2）
- 启用 WSL 2 后端的 Docker Desktop
- 在 `http://localhost:8080/` 部署本地 eScriptorium Compose 服务
- 自动生成管理员密码，并使用 Windows DPAPI 在本机保护
- 中英双语工作台：导入 ALTO XML / PAGE XML，逐行 AI 清洗与对照翻译，
  文本分析，以及 TEI/JSON/CSV 导出

## Requirements

- 64-bit Windows 10/11 with WSL 2 support
- At least 8 GB RAM and 12 GB free disk space
- Hardware virtualization enabled in BIOS/UEFI
- Internet access on first install (container images may total several GB)
- Administrator approval for the machine-wide Docker and WSL installation

Docker Desktop has its own subscription terms. The app asks you to review those
terms before it can download and install Docker. Docker is free for qualifying
personal, education, small-business, and open-source use.

## 系统要求

- 支持 WSL 2 的 64 位 Windows 10/11
- 至少 8 GB 内存和 12 GB 可用磁盘空间
- BIOS/UEFI 中已启用硬件虚拟化
- 首次安装需要联网，容器镜像可能需要下载数 GB
- 机器级安装 Docker 和 WSL 需要管理员授权

Docker Desktop 有独立的订阅条款。程序在下载和安装 Docker 前会要求您阅读并确认条款。
符合条件的个人、教育、小型企业和开源用途可以免费使用 Docker。

## First run

1. Start `eScriptorium-Studio-Setup-EN-ZH-v1.6.exe`.
2. Choose **Install & run / 安装与运行**.
3. Review and check the Docker terms box.
4. Choose **Install & start / 安装并启动** and approve the Windows UAC prompt.
5. If Windows installs WSL and asks for a restart, restart Windows and run the
   installer again. The app resumes from the current machine state.
6. Wait for Docker image download and the `localhost:8080/health` check.
7. The browser opens eScriptorium. Use the administrator credentials shown in
   **Settings / 设置**.
8. Create a document, upload manuscript images or a PDF, run layout/HTR, then
   export ALTO XML or PAGE XML.
9. Import that export in **Manuscript studio / 手稿工作台**.

## 首次使用

1. 启动 `eScriptorium-Studio-Setup-EN-ZH-v1.6.exe`。
2. 进入“安装与运行”。
3. 阅读并勾选 Docker 条款。
4. 点击“安装并启动”，在 Windows UAC 提示中批准。
5. 如果 Windows 安装 WSL 后要求重启，请重启后再次运行安装器；程序会从当前
   机器状态继续，不会重复已完成步骤。
6. 等待 Docker 镜像下载完成及 `localhost:8080/health` 检查通过。
7. 浏览器会打开 eScriptorium。管理员账号和密码可在“设置”中查看。
8. 新建文档并上传手稿图像或 PDF，执行区域检测与 HTR，然后导出 ALTO XML 或
   PAGE XML。
9. 在“手稿工作台”导入该导出文件。

## AI cleaning and aligned translation

The workspace calls a user-supplied OpenAI-compatible `chat/completions`
endpoint. Enter the endpoint, API key, model, source language, and target
language in **Settings / 设置**. You can use a local endpoint such as Ollama or
an institutional gateway.

The endpoint should be the complete Chat Completions URL, for example
`https://api.openai.com/v1/chat/completions` or
`https://api.deepseek.com/chat/completions`. The model name must belong to the
same provider that issued the API key.

The AI prompt is line-oriented: each input line ID and its coordinate box must
remain paired with one cleaned source line and one translation. The prompt keeps
early modern spelling and marks unreadable text as `[illegible]`; it does not
silently modernize names, abbreviations, or u/v and i/j forms.

### AI error codes

| Code | Meaning |
|---|---|
| `AIC001` | Missing endpoint, model or API key / 缺少接口、模型或 API Key |
| `AIC002` | Invalid endpoint URL / 接口 URL 格式无效 |
| `AIC003` | DNS, network, VPN, proxy or firewall connection failure / 网络连接失败 |
| `AIC004` | Windows TLS/Schannel credential unavailable / Windows TLS 凭证不可用 |
| `AIC005` | Request timeout / 请求超时 |
| `AIC006` | HTTP 401: invalid or mismatched API key / API Key 无效或不匹配 |
| `AIC007` | HTTP 403: model, project or region permission denied / 权限不足 |
| `AIC008` | HTTP 404: endpoint path or model not found / 接口或模型不存在 |
| `AIC009` | HTTP 429: rate limit, quota or balance problem / 限流、额度或余额问题 |
| `AIC010` | Other unexpected HTTP error / 其他 HTTP 错误 |
| `AIC011` | Invalid JSON in the AI response / AI 响应 JSON 无效 |
| `AIC012` | Missing `choices/message/content` / Chat Completions 响应结构缺失 |
| `AIC013` | Returned line IDs do not match imported lines / 返回行号不匹配 |
| `AIC014` | No non-empty transcription text / 没有可处理的非空文字 |
| `AIC015` | HTTP 5xx provider server error / 服务商服务器错误 |
| `AIC016` | HTTPS certificate validation failed / HTTPS 证书验证失败 |
| `AIC017` | Windows TLS failed and Python/OpenSSL fallback failed / Windows TLS 失败且 Python/OpenSSL 回退失败 |

### Automatic AIC004 transport fallback

If the normal .NET client reports `AIC004`, the app searches for a local
`python.exe` with the `requests` package and sends the request through
Python/OpenSSL. This is a transport fallback; it does not bypass TLS
certificate verification.

The current machine already has Anaconda Python with `requests`, so this path is
available. If Python is not installed, the app reports `AIC017` and the normal
AI error-code explanation.

### AIC004 自动回退

正常 .NET 客户端出现 `AIC004` 时，软件会查找带 `requests` 包的本机
`python.exe`，并通过 Python/OpenSSL 重发请求。该机制只替换传输层，不会跳过 TLS
证书验证。

当前电脑已安装 Anaconda Python 和 `requests`，因此可使用该回退通道。如果没有
Python，软件会显示 `AIC017` 及对应中英文原因。

Without an API key, the app still supports local Unicode/whitespace cleaning,
word frequency, type/token ratio, likely-language hints, and all exports. Local
cleaning is not a substitute for scholarly proofreading.

## AI 清洗与对照翻译

工作台调用用户自行提供的 OpenAI 兼容 `chat/completions` 接口。在“设置”中填写
接口地址、API Key、模型、源语言和目标语言。可使用 Ollama 等本机接口，也可使用
学校或研究机构的兼容网关。

接口应填写完整的 Chat Completions 地址，例如
`https://api.openai.com/v1/chat/completions` 或
`https://api.deepseek.com/chat/completions`。模型名必须属于签发该 API Key 的同一
服务商。

## Three independent processing choices

1. eScriptorium **segmentation model**: detects regions and line areas.
2. eScriptorium **HTR/recognition model**: turns each line image into text.
3. AI **translation model and API key**: cleans and translates recognized text.

The first two models are selected inside eScriptorium and depend on script,
language and period. For early modern German handwriting, confirm that the HTR
model supports Kurrent/Fraktur. AI translation does not replace HTR.

The generated eScriptorium administrator password is only for signing in to
`http://localhost:8080/`. It is not an AI API key. The provider API key in
**AI TRANSLATION** is separate and should never be entered into the
eScriptorium login form.

## 三套独立的处理配置

1. eScriptorium **区域检测/分割模型**：检测版面和文本行区域。
2. eScriptorium **HTR/文字识别模型**：把每一行图像转换成文字。
3. AI **翻译模型和 API Key**：对识别后的文本进行清洗和翻译。

前两个模型必须在 eScriptorium 内自行选择，并适合手稿的字体、语言和年代。
早期现代德语手稿应确认 HTR 模型支持 Kurrent/Fraktur。AI 翻译不能代替 HTR。

自动生成的 eScriptorium 管理员密码仅用于登录 `http://localhost:8080/`，
不是 AI API Key。“AI TRANSLATION”中的服务商 API Key 与它相互独立，
也不应填入 eScriptorium 登录框。

提示词按行组织，要求同一输入行号、原坐标框、清洗文本和译文保持一一对应。
默认保留早期现代拼写；无法辨认的文字标记为 `[illegible]`，不会擅自现代化人名、
缩写或 u/v、i/j 异体。

不填写 API Key 时，仍可使用本地 Unicode/空白清洗、词频、词型/词元比、语言提示和
全部导出功能。本地清洗不能替代学者逐行复核。

## Privacy

Manuscript images and coordinates remain in the local eScriptorium Docker stack
and this desktop app. When you press an AI action, only the source/cleaned line
text and translation fields in that batch are sent to your configured endpoint.
For restricted collections, configure a local model endpoint or leave AI
unconfigured.

## 隐私

手稿图像和坐标保存在本机 eScriptorium Docker 服务及桌面程序中。只有点击 AI 操作时，
该批次中的原文/清洗文本和翻译字段才会发送到您配置的接口。受限藏品建议使用本机
模型接口，或不配置 AI。

## Sample

See `samples/early-modern-english.alto.xml`. It contains long-s, early modern
spelling, and four line coordinate boxes. Import it from the studio to test the
workflow before using a real HTR export.

## 样例

请见 `samples/early-modern-english.alto.xml`。其中包含长 s、早期现代英语拼写和四个
逐行坐标框。可在工作台导入该文件，在真实 HTR 导出前验证完整流程。

## Data, backup, and removal

- Settings and deployment metadata: `%LOCALAPPDATA%\eScriptoriumStudio\`
- eScriptorium database, media, and search data: Docker named volumes for the
  `escriptorium-studio` Compose project
- Exports: chosen by you; the default folder is
  `%LOCALAPPDATA%\eScriptoriumStudio\exports\`
- Do not remove Docker volumes unless you intend to delete the manuscript data.
- No uninstall command is run automatically. Data removal is deliberately a
  separate, explicit destructive action.

## 数据、备份和卸载

- 配置与部署元数据：`%LOCALAPPDATA%\eScriptoriumStudio\`
- eScriptorium 数据库、媒体与搜索数据：`escriptorium-studio` Compose 项目的
  Docker 命名卷
- 导出位置：由您选择；默认目录为
  `%LOCALAPPDATA%\eScriptoriumStudio\exports\`
- 如不需要保留手稿数据，不要删除 Docker 卷。
- 程序不会自动执行卸载。删除数据属于独立的显式破坏性操作。

## Troubleshooting

- **Port 8080 occupied:** stop the other service, then choose Recheck.
- **Docker engine not running:** open Docker Desktop, finish its first-run
  prompts, then choose Start / repair.
- **Restart required after WSL:** restart Windows and run Install & start again.
- **AI HTTP 401/403:** verify the API key and endpoint.
- **AI response has no aligned JSON:** choose a model with reliable JSON output.
- **Need logs:** open `%LOCALAPPDATA%\eScriptoriumStudio\studio.log`.

## 故障排查

- **8080 端口被占用：** 关闭占用端口的服务，再点击“重新检查”。
- **Docker 引擎未运行：** 打开 Docker Desktop，完成首次启动提示，再点击
  “启动 / 修复”。
- **WSL 安装后要求重启：** 重启 Windows，再次点击“安装并启动”。
- **AI 返回 401/403：** 检查 API Key 和接口地址。
- **AI 未返回对齐 JSON：** 换用 JSON 输出稳定的模型。
- **查看日志：** 打开 `%LOCALAPPDATA%\eScriptoriumStudio\studio.log`。

## Technical notes

- The app is a dependency-free .NET Framework 4.8 WinForms executable.
- The Compose project binds eScriptorium to `127.0.0.1:8080` and Flower to
  `127.0.0.1:5555`; database and Redis ports are not published.
- The eScriptorium image currently uses the official `latest` application tag.
  Rechecking / repair starts the same local volumes and preserves data.
- For production or multi-user deployment, review the official eScriptorium
  deployment guidance and harden credentials, TLS, backups, and authentication.

## 技术说明

- 程序是无外部运行时依赖的 .NET Framework 4.8 WinForms 可执行文件。
- Compose 仅将 eScriptorium 绑定到 `127.0.0.1:8080`，Flower 绑定到
  `127.0.0.1:5555`；数据库与 Redis 端口不对外发布。
- eScriptorium 当前使用官方 `latest` 应用标签。重新检查或修复会启动同一组本地卷，
  并保留数据。
- 用于生产或多用户环境时，请进一步阅读 eScriptorium 官方部署指南，并加固凭据、
  TLS、备份与身份认证。
