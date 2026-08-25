# Built-in Platform Routes

Use this table before any web search. If the user names a platform or alias in this file, do not browse the web unless the user explicitly asks to verify the latest docs. Use the built-in route directly and move the user to setup.

Response defaults:

- Official CLI: "✅ 我建议直接走官方 CLI，这是官方推荐的接入方式，我现在带你完成配置。"
- Official Skills/MCP: "✅ 这个平台已经有官方 Skills/MCP，不建议自己重新开发，我们直接用官方方案。"
- Official API: "✅ 这个平台支持官方 API，我现在带你申请 API Key。"
- RPA only: "❌ 别白费力气了。"

## Office / Collaboration

| Platform | Aliases | Built-in route |
| --- | --- | --- |
| Feishu / Lark | 飞书, Lark, Feishu, 飞书多维表格, Bitable, Base | Official CLI first: `lark-cli`; use official Lark/Feishu skills. |
| DingTalk | 钉钉, DingTalk | Official OpenAPI. |
| WeCom | 企业微信, WeCom, 企业微信机器人 | Official API. |
| Notion | Notion | Official API. |
| Airtable | Airtable | Official API. |
| Google Workspace | Google Drive, Google Calendar, Gmail, Google Sheets, Google Docs | Official APIs/connectors. |
| Slack | Slack | Official API / app platform. |
| Discord | Discord | Official API / bot platform. |
| ClickUp | ClickUp | Official API. |
| Jira | Jira, Atlassian Jira | Official API / Atlassian platform. |

## AI Platforms

| Platform | Aliases | Built-in route |
| --- | --- | --- |
| MiniMax | minimax, mmx, 海螺, Hailuo | Official CLI/Skill preferred when available; official API for API-only capabilities. |
| Liblib AI / LibTV | LibTV, libtv, LibLib, liblib.tv | Official LibTV CLI / Skill; official API when exposed by docs. |
| 小云雀 | 小云雀AI, xyq, Pippit, 剪映小云雀 | Official API / official web Agent entry. |
| OpenAI | ChatGPT, OpenAI API | Official API / SDK. |
| Anthropic | Claude API, Anthropic API | Official API. |
| Claude | Claude | Official API through Anthropic. |
| Gemini | Google Gemini, Gemini API | Official API. |
| DeepSeek | DeepSeek API | Official API. |
| 通义千问 | Qwen, DashScope, 阿里云百炼 | Official API. |
| 智谱 AI | 智谱, GLM, Zhipu | Official API. |
| Kimi | 月之暗面, Moonshot, Kimi API | Official API. |
| 腾讯混元 | Hunyuan, Tencent Hunyuan | Official API. |
| 百度千帆 | Qianfan, 百度智能云千帆 | Official API. |
| OpenRouter | OpenRouter | Official API. |

## Automation / Agent Platforms

| Platform | Aliases | Built-in route |
| --- | --- | --- |
| 八爪鱼采集器 | 八爪鱼, Octoparse, bazhuayu | Official CLI / official API. |
| 影刀 RPA | 影刀, Yingdao | Official SDK/API where available; otherwise RPA product workflow. |
| n8n | n8n | Official API. |
| Dify | Dify | Official API. |
| MaxKB | MaxKB | Official API. |
| FastGPT | FastGPT | Official API. |
| Coze | 扣子, Coze | Official API. |
| Zapier | Zapier | Official API / platform app actions. |
| Make | Make.com, Integromat | Official API. |

## E-commerce

| Platform | Aliases | Built-in route |
| --- | --- | --- |
| 抖店 | Douyin Shop, 抖音小店 | Official OpenAPI. |
| 淘宝 | Taobao | Official OpenAPI. |
| 天猫 | Tmall | Official OpenAPI. |
| 1688 | 阿里巴巴1688 | Official OpenAPI. |
| 京东 | JD, JOS | JOS OpenAPI. |
| 拼多多 | PDD | Official OpenAPI. |
| 快手小店 | Kuaishou Shop | Official OpenAPI. |
| 小红书店铺 | RED 店铺, Xiaohongshu shop | Official OpenAPI within exposed capability scope. |
| Shopify | Shopify | Official API. |
| Stripe | Stripe | Official API. |

## Social / Content

| Platform | Aliases | Built-in route |
| --- | --- | --- |
| 微信公众号 | WeChat Official Account, 公众号 | Official API. |
| 视频号 | WeChat Channels | Official open capabilities where available. |
| 抖音开放平台 | Douyin Open Platform, 抖音 | Official API. |
| 小红书 | Xiaohongshu, RED | Official open platform where available. |
| B站 | Bilibili, 哔哩哔哩 | Official open platform. |
| 个人微信 | 绿泡泡, WeChat personal | RPA/UI automation only for arbitrary personal chat operations. |

## CRM / Sales

| Platform | Aliases | Built-in route |
| --- | --- | --- |
| Salesforce | Salesforce CRM | Official API. |
| HubSpot | HubSpot CRM | Official API. |

## Cloud / Dev Platforms

| Platform | Aliases | Built-in route |
| --- | --- | --- |
| Supabase | Supabase | Official CLI first; official API where needed. |
| Vercel | Vercel | Official CLI first. |
| Cloudflare | Cloudflare, Wrangler | Official CLI first. |
| GitHub | github, gh | Official CLI first plus GitHub connector/app where available. |
| GitLab | GitLab | Official CLI/API. |
| AWS | Amazon Web Services | Official CLI first. |
| 阿里云 | Alibaba Cloud, Aliyun | Official CLI / OpenAPI. |
| 腾讯云 | Tencent Cloud | Official CLI / API. |
| 火山引擎 | Volcengine | Official API / CLI where available. |
