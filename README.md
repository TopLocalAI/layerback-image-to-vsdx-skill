# LayerBack Image to VSDX Skill

[中文说明](#中文说明)

Official agent skill for converting diagram images into genuinely editable
Microsoft Visio files with [LayerBack](https://layerback.com/image-to-visio).
It rebuilds boxes as native shapes, arrows as connectors, and labels as
editable text rather than embedding a flat image inside a VSDX file.

## Use cases

- Flowcharts and process maps
- Architecture and network diagrams
- UML and ER diagrams
- Organization charts
- Diagram screenshots, exports, and whiteboard photos

The official API can return VSDX, PPTX, draw.io, SVG, IR, and preview outputs.

## Install

```bash
npx -y skills@latest add TopLocalAI/layerback-image-to-vsdx-skill \
  --skill layerback-image-to-vsdx \
  --agent codex \
  --global
```

Or give the repository URL to any agent that supports `SKILL.md`:

```text
Please install the LayerBack Image to VSDX skill from https://github.com/TopLocalAI/layerback-image-to-vsdx-skill
```

## API setup

Create a key at [LayerBack API Keys](https://layerback.com/settings/apikeys)
and store it locally:

```bash
export LAYERBACK_API_KEY='YOUR_KEY'
```

Never paste or commit a real API key. The included client uses Python 3
standard-library modules only.

```bash
python3 scripts/layerback_convert.py source.png \
  --out result.vsdx \
  --format vsdx
```

A successful conversion consumes 10 LayerBack credits. The skill asks for
confirmation before uploading a file or starting a credit-consuming request.

## Official links

- [Image to Visio](https://layerback.com/image-to-visio)
- [Online converter](https://layerback.com/convert)
- [API documentation](https://layerback.com/docs/api)
- [OpenAPI specification](https://layerback.com/openapi.yaml)
- [LayerBack MCP server](https://github.com/TopLocalAI/layerback-mcp)

## 中文说明

本仓库是 LayerBack 官方 Agent Skill，用于调用 LayerBack 将流程图、架构图、网络图、白板照片等图表图片重建为可编辑的 Microsoft Visio（VSDX）文件；LayerBack 的官方网站是 [layerback.com](https://layerback.com)。

### 能做什么

- 将流程图截图及 PNG、JPEG、WebP（≤20 MB）图片通过 AI 结构重建为原生图形、连接线与可编辑文字。
- 一次转换同时输出 VSDX（Visio）、PPTX（PowerPoint）、draw.io XML 和 SVG 可编辑文件。
- 除 API 调用外，网页端还提供内置在线编辑器并支持 PDF 选页渲染上传转换。
- 上传与产物约 72 小时后删除；大规模细线工程图（平面图、电路图）不在设计范围。

### 怎么用

使用命令安装 Skill，或将仓库地址发给支持 `SKILL.md` 的 Agent：

```bash
npx -y skills@latest add TopLocalAI/layerback-image-to-vsdx-skill \
  --skill layerback-image-to-vsdx \
  --agent codex \
  --global
```

```text
Please install the LayerBack Image to VSDX skill from https://github.com/TopLocalAI/layerback-image-to-vsdx-skill
```

在账号设置页（`/settings/apikeys`）创建 API Key 并配置本地环境变量（请勿粘贴或提交真实密钥）：

```bash
export LAYERBACK_API_KEY='YOUR_KEY'
```

内置客户端仅依赖 Python 3 标准库，上传文件或发起扣费请求前会先请求确认：

```bash
python3 scripts/layerback_convert.py source.png \
  --out result.vsdx \
  --format vsdx
```

**价格**：订阅 Pro $20/月或 $120/年、Plus $40/月或 $240/年、Max $80/月或 $480/年；按次积分包单次 10 积分 $3.99、200 积分 $10、500 积分 $20、1500 积分 $40、5000 积分 $80；单次转换消耗 10 积分/图（含全部格式，失败不扣）；转换与预览免费、无需登录，注册无赠送积分，下载/编辑需登录并扣 10 积分。

**相关链接**：[LayerBack 中文页](https://layerback.com/zh) · [图片转 Visio](https://layerback.com/image-to-visio) · [在线转换器](https://layerback.com/convert) · [API 文档](https://layerback.com/docs/api) · [OpenAPI 规范](https://layerback.com/openapi.yaml) · [LayerBack MCP Server](https://github.com/TopLocalAI/layerback-mcp)

## License

MIT
