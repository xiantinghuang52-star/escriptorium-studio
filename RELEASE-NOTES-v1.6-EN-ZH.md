# eScriptorium Studio v1.6

## English

### Language-aware OCR cleansing

- Treats l/f/s/ſ as ambiguous OCR forms, not a universal replacement rule.
- Detects the page language and supplies language-specific guidance to the AI.
- Uses function words, morphology, capitalization and neighboring lines.
- Adds a conservative local correction dictionary for high-confidence cases such
  as German fich→sich, ift→ist and English lhe→she, lhall→shall.
- Leaves ambiguous forms unchanged for human review.

### Faster page processing

- Processes up to two page nodes concurrently.
- Removes DeepSeek thinking mode for page-node requests.
- Requests JSON response format from DeepSeek.
- Normalizes punctuation spacing in page translations and contextual cleanse.

### Verified

- A one-page OCR sample containing lhe, Lhall, luch, thil and loule was corrected
  to she, Shall, such, this and soule.
- The page-node request completed in about 15 seconds in the local test.
- Application self-test exit code: `0`.

Network and provider latency vary, so 15 seconds is a measured example rather
than a guaranteed time.

## 中文

### 语言感知 OCR 清洗

- 把 l/f/s/ſ 视为 OCR 潜在混淆，不采用全局替换规则。
- 自动检测页面语言，并向 AI 提供该语言的拼写搭配指导。
- 综合功能词、词法、大小写和相邻行上下文。
- 增加保守的本地高置信度修正，例如德语 fich→sich、ift→ist，英语
  lhe→she、lhall→shall。
- 模糊形式保持原样，供人工复核。

### 更快的页面处理

- 最多同时处理两个页面节点。
- DeepSeek 页面请求关闭思考模式。
- 请求 DeepSeek 返回 JSON 格式。
- 对整页译文和语境清洗文本规范化标点间距。

### 验证

- 包含 lhe、Lhall、luch、thil、loule 的单页样例已修正为
  she、Shall、such、this、soule。
- 本地测试中页面节点请求约 15 秒完成。
- 应用自检退出码为 `0`。

网络和服务商延迟会波动，15 秒是本次实测结果，不是固定保证。
