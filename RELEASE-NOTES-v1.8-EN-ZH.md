# eScriptorium Studio v1.8

## English

### Added

- Embedded eScriptorium browser mirror using WebView2.
- Single-EXE embedded WebView2 managed assemblies and native loader.
- Recognition model API listing and persistent model selection.
- Direct `.mlmodel` upload to eScriptorium.
- Automatic document ID detection from the mirror URL.
- Transcription layer selection.
- Segmentation and HTR task submission.
- External Edge fallback.

### Non-commercial scope

The interface/workflow is informed by Archive Studio's CC BY-NC 4.0 project.
No Archive Studio source code is copied. Umi-OCR is not bundled in v1.8.

### Verified

- The embedded mirror displayed the local eScriptorium homepage.
- The API authenticated with local administrator credentials and loaded five
  Recognition models.
- HTR model and transcription controls rendered correctly.
- Application self-test exit code: `0`.

## 中文

### 新增

- 使用 WebView2 的 eScriptorium 内嵌镜像。
- WebView2 托管程序集与 native loader 均嵌入单 EXE。
- 从 API 读取 Recognition 模型并保存选择。
- 直接上传 `.mlmodel` 到 eScriptorium。
- 从镜像 URL 自动识别文档 ID。
- 转录层选择。
- 提交文本行检测和 HTR 任务。
- WebView2 不可用时回退到外置 Edge。

### 非商业范围

界面和工作流参考 Archive Studio（CC BY-NC 4.0）；未复制其源代码。
v1.8 尚未内置 Umi-OCR。

### 验证

- 嵌入镜像成功显示本地 eScriptorium 首页。
- API 使用本机管理员凭据成功加载 5 个 Recognition 模型。
- HTR 模型及转录层控件显示正常。
- 应用自检退出码为 `0`。
