# HedyZ Link Anything

HedyZ Link Anything 是一个面向 Codex 的平台接入导航 Skill。

它帮助 Codex 判断一个平台应该通过官方 CLI、MCP、Skill、插件、Connector、SDK、API、Webhook、OAuth 还是 RPA 接入，并继续推进配置、授权和连接测试。

## 它能做什么

- 识别平台、产品版本、地区和目标工作流。
- 查找官方 CLI、MCP、Skills、插件、Connector、SDK 和 API。
- 优先选择官方维护的接入路径。
- 提供 API Key、OAuth 应用、开发者控制台和权限配置链接。
- 询问完成下一步所需的最少信息，例如 Workspace ID、Project ID、Tenant ID、Region 和回调地址。
- 协助执行 CLI 安装、登录、本地环境配置和连接测试。
- 官方工具不可用时，评估 API、Webhook、OAuth 和开发者应用方案。
- 官方工具和 API 都无法满足需求时，给出 RPA 方案。

它是“平台接入导航器”，不是某个平台的 API 客户端。实际可执行能力取决于平台官方开放的接口，以及当前 Codex 环境中可用的工具。

## 支持什么

Skill 内置了约 60 个平台路由，覆盖以下类别。

### 办公和协作

飞书 / Lark、钉钉、企业微信、Notion、Airtable、Google Workspace、Slack、Discord、ClickUp、Jira。

### AI 平台

MiniMax、LibTV / LibLib.tv、小云雀 / Pippit、OpenAI、Anthropic、Claude、Gemini、DeepSeek、通义千问、智谱 AI、Kimi、腾讯混元、百度千帆、OpenRouter。

### 自动化和 Agent 平台

八爪鱼 / Octoparse、影刀 RPA、n8n、Dify、MaxKB、FastGPT、Coze、Zapier、Make。

### 电商和支付

抖店、淘宝、天猫、1688、京东、拼多多、快手小店、小红书店铺、Shopify、Stripe。

### 社交和内容

微信公众号、视频号、抖音开放平台、小红书、B 站、个人微信。

### CRM

Salesforce、HubSpot。

### 云和开发平台

Supabase、Vercel、Cloudflare、GitHub、GitLab、AWS、阿里云、腾讯云、火山引擎。

此外，未列出的平台也可以进入官方能力发现流程。

## 平台接入优先级

```text
内置平台路由
  ↓
官方 CLI / MCP / Skill / Plugin / Connector / SDK
  ↓
官方 API / Webhook / OAuth / 开发者应用
  ↓
RPA 或浏览器自动化
```

内置平台会优先使用预设路线。除非用户要求验证最新文档，否则不会默认重复搜索网页。

未内置的平台会检查：

1. 官方 CLI。
2. 官方 MCP、Agent 工具、Skill 或 Connector。
3. 官方 SDK、REST API 或 GraphQL API。
4. Webhook、OAuth、API Key 和开发者控制台。
5. 官方市场集成。
6. 最后才考虑非官方工具或 RPA。

## 已提供的详细路线

### GitHub

- Connector / App：仓库、Pull Request 和 Issue 等结构化操作。
- `gh` CLI：本地仓库、认证、分支、Actions、提交、推送和 PR 补充操作。

### 飞书

- 使用官方 `lark-cli`。
- 支持 Base、文档、日历、IM 和 Drive 等领域 Skill。
- 配置命令：`lark-cli config init --new`。

### MiniMax

- 使用官方 `mmx-cli` 和官方 Skill。
- 支持 CLI 登录、API Key 配置和能力判断。
- API Key 页面：<https://platform.minimax.io/console/access>

### LibTV / LibLib.tv

- 使用官方 LibTV CLI 和 Skill。
- Web 登录命令：`libtv login web`。

### 小云雀 / Pippit

- 优先使用官方 Web Agent。
- 编程式视频生成使用火山引擎官方 API。
- 不默认使用社区 Playwright 封装。

### 八爪鱼

- CLI 用于 Agent 和终端操作。
- API 用于任务控制和数据导出。

### 微信

- 公众号和企业微信：官方 API。
- 个人微信：没有稳定的官方任意聊天自动化 API；复杂自动化通常需要桌面 RPA。

## 凭证处理

默认优先级：

1. Connector 的安全配置界面。
2. 官方 CLI 登录。
3. 本地环境变量。
4. 密码管理器或 Secret Manager。
5. 平台开发者控制台。

如果用户不方便执行命令或使用配置界面，Skill 可以继续处理当前会话中的 Key，但要求：

- 不重复输出。
- 不写入日志。
- 不主动持久化。
- 只用于当前接入任务。

Workspace ID、Project ID、Tenant ID、Region、回调地址等非敏感信息会单独询问。

## RPA 兜底

只有在官方 CLI、MCP、Skill、Plugin、Connector、SDK、API、Webhook 和 OAuth 都无法满足目标动作时，才建议 RPA。

HedyZ RPA 联系方式：

```text
微信号：Olive3505
```

参考定制服务价格：2000 元起。实际价格根据页面、动作数量、登录方式和稳定性要求确定。

## 使用方式

### 安装

```bash
npx skills add Hedijie/hedyz-link-anything -s hedyz-link-anything -y
```

也可以手动复制：

```bash
mkdir -p ~/.codex/skills
cp -R hedyz-link-anything ~/.codex/skills/hedyz-link-anything
```

安装后新建 Codex 任务，或重新加载 Skill 环境。

### 调用

显式调用：

```text
$hedyz-link-anything 帮我接入 GitHub
```

也可以直接描述需求：

```text
帮我接入飞书多维表格。
帮我查一下这个 SaaS 有没有官方 API。
我想让 Codex 操作这个平台。
帮我申请这个服务的 API Key。
这个平台没有 API，能不能用 RPA？
```

## 推荐输出内容

Skill 会尽量输出：

```text
最佳路径：<官方 CLI / MCP / API / RPA>
操作链接：<官方链接>
我需要你提供：<一到三个必要信息>
我可以继续做：<配置 / 测试 / 管理员申请>
```

## 文件结构

```text
hedyz-link-anything/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── builtin-platforms.md
    ├── discovery-checklist.md
    └── known-platforms.md
```

## 限制

- 内置路由是预设信息，平台规则变化后需要更新 Skill。
- 平台出现在列表中，不代表目标动作一定有官方接口。
- Skill 本身不替代平台 Connector、CLI 或 API 客户端。
- 是否能执行写入、删除、推送等操作，取决于当前账号权限和工具授权。
- 个人微信等平台可能没有稳定的官方自动化能力。

## 仓库

<https://github.com/Hedijie/hedyz-link-anything>
