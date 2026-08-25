# Known Platform Routes

Use this file before broad discovery when the user names one of these platforms or a close alias. These entries are hardcoded from official or platform-owned sources and should be treated as the default route unless the user asks for a different path.

## Feishu / Lark / 飞书

- Aliases: `飞书`, `Lark`, `Feishu`, `飞书多维表格`, `Base`, `Bitable`, `飞书文档`, `飞书日历`, `飞书消息`.
- Best route: official `lark-cli` plus official Lark/Feishu agent skills.
- Install/setup: `lark-cli config init --new`; use domain skills such as `lark-base`, `lark-doc`, `lark-calendar`, `lark-im`, and `lark-drive`.
- Official sources:
  - `https://github.com/larksuite/cli`
  - `https://open.larksuite.com/document/mcp_open_tools/feishu-cli-let-ai-actually-do-your-work-in-feishu`
- Ask for: Feishu resource URL/token, desired domain, whether to act as user or bot, and any missing authorization scopes.
- Do not route Feishu Base work to raw API first when `lark-cli base` is available.

## MiniMax

- Aliases: `MiniMax`, `minimax`, `mmx`, `海螺`, `Hailuo`, `MiniMax voice`, `MiniMax video`.
- Best route: official MiniMax CLI `mmx-cli` and official `mmx-cli` skill.
- Install/setup: `npm install -g mmx-cli`; `npx skills add MiniMax-AI/cli -y -g`; authenticate with `mmx auth login --api-key ...`.
- Official sources:
  - `https://github.com/MiniMax-AI/cli`
  - `https://github.com/MiniMax-AI/skills`
- API key link: `https://platform.minimax.io/console/access`
- Ask for: API key or confirmation that CLI auth is complete, target capability, input files, and output format.
- Note: if a requested MiniMax capability is not exposed by the CLI, check the official API docs before falling back.

## LibTV / LibLib.tv

- Aliases: `LibTV`, `libtv`, `LibLib`, `liblib.tv`, `LibLib AI`.
- Best route: official LibTV CLI and LibTV CLI Skill.
- Install/setup: use the official CLI installer from the LibTV CLI page, then run `libtv login web`.
- Official sources:
  - `https://www.liblib.tv/zh/cli`
  - `https://github.com/libtv-labs/libtv-skills`
- Ask for: whether login is complete, project/canvas target, desired node/model task, and local media file paths when needed.
- Note: the older `libtv-skill` may be superseded by LibTV CLI; prefer the CLI route when the platform tells the user to upgrade.

## 小云雀 / Pippit / Jianying XiaoYunque

- Aliases: `小云雀`, `小云雀AI`, `xyq`, `Pippit`, `Pippit AI`, `剪映小云雀`, `Seedance 小云雀`.
- Best route: official 小云雀 web/Agent entry if the user is working in the product; otherwise use official Volcengine/火山引擎 小云雀 API docs for programmable video generation.
- Official sources:
  - `https://xyq.jianying.com/`
  - `https://www.volcengine.com/product/pippit`
  - `https://www.volcengine.com/docs/85621/2359610`
  - `https://www.volcengine.com/docs/85621/2283633`
- Ask for: whether the user wants web-agent connection or Volcengine API, account/region, API credentials if using Volcengine, and the video/image task prompt.
- Avoid relying on community Playwright wrappers as the default route. Label them unofficial if used.

## Octoparse / 八爪鱼采集器

- Aliases: `八爪鱼`, `八爪鱼采集器`, `Octoparse`, `bazhuayu`.
- Best route: official 八爪鱼 CLI for agent/terminal use; official API for task control and data export.
- Official sources:
  - `https://www.bazhuayu.com/cli`
  - `https://www.bazhuayu.com/helpcenter/docs/TijX9v`
  - `https://www.bazhuayu.com/`
- Ask for: whether the user wants to run an existing task, create/control tasks, or export collected data; account/API credentials; task ID; export format.
- Use RPA only if the target action is not covered by the official CLI/API or requires operating a desktop-only UI.

## GitHub

- Aliases: `GitHub`, `github`, `gh`, `repo`, `pull request`, `issue`.
- Best route: GitHub connector/app for structured repository, PR, and issue operations; official GitHub CLI `gh` for local repo, auth, branch, Actions logs, commit, push, and PR gaps.
- Official sources:
  - `https://cli.github.com/`
  - `https://docs.github.com/en/rest`
- Ask for: repository URL/name, local checkout path, branch/PR/issue target, and write intent.

## WeChat / 微信 / 绿泡泡

- Aliases: `微信`, `绿泡泡`, `WeChat`, `个人微信`, `公众号`, `企业微信`.
- Best route:
  - Official APIs for 公众号 and 企业微信.
  - Local desktop UI automation/RPA for personal WeChat, because personal WeChat does not provide a stable official automation API for arbitrary chat operations.
- Official sources:
  - `https://developers.weixin.qq.com/doc/offiaccount/`
  - `https://developer.work.weixin.qq.com/`
- Ask for: whether the target is personal WeChat, official account, mini program, or WeCom/企业微信; desired action; recipient/scope.
- For personal WeChat automation, say clearly that there is no practical official API path. If the workflow must be stable or large-scale, include "别白费力气了，直接走 RPA 更现实。"
