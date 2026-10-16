# TENBIL Codex 插件

把 TENBIL 的商机推进、提案准备和营销计划带入 Codex。插件只包含远程 MCP 连接声明、图标和三个 Skill；业务数据保存在 TENBIL，按每位成员本人授权读取和保存。

## 安装

1. 打开 [TENBIL 设置 → Agent 与连接](https://library.peckperk.com/settings?section=connections)，复制插件源地址。
2. 在 Codex 添加插件源：`https://github.com/PeckPerk-Inc/tenbil-codex-plugin`。这是独立插件源，不需要 TENBIL 主应用源码仓库权限。
3. 打开 Codex 原生插件页，选择「TENBIL 团队」，点开 TENBIL 图标并点击「安装」。添加源不会自动安装，不要让对话中的 Agent 代替你执行安装。
4. 安装完成后先回到 TENBIL 设置，选择并保存需要的业务权限，再继续连接。

如果当前客户端通过命令添加源，只运行下面这条命令，然后回到原生插件页点击安装：

```sh
codex plugin marketplace add https://github.com/PeckPerk-Inc/tenbil-codex-plugin
```

插件标识为 `tenbil@tenbil-team`，marketplace 名称为 `tenbil-team`。旧版 Codex 没有插件入口或不支持源命令时，先更新客户端。首次使用时认证（`ON_USE`）将安装和业务授权分开；安装完成不代表已经连接。

## 授权与使用

1. 在 TENBIL 设置选择所需权限并保存。只读范围允许查询；保存客户、商机或工作资料需要相应写权限，团队共享资料读取需另外选择。
2. 在 Codex 新对话中选择 TENBIL，按客户端提示连接。在浏览器用自己的团队账号登录，核对权限并确认，再返回 Codex。
3. 先让 TENBIL 核对当前用户、工作空间和权限，再读取一条自己的客户或商机。需要保存时按客户端规则确认，完成后可在网页打开同一条记录核对。

例如：「读取这条商机的完整上下文，给我下一步建议和依据。」「根据客户需求，找案例并准备有来源的提案工作稿。」「把这次营销目标整理成计划、步骤和产物。」

每名成员都需要本人授权。凭据由 Codex 保存并自动续期，不需要每天重新登录；不要把密钥、Cookie 或 token 贴到对话。授权持续到用户断开、替换授权或账号停用；可随时在 TENBIL 设置撤销。仅卸载插件或关闭网页不等于撤销业务授权。

## 三个 Skill

| Skill | 用途 |
| --- | --- |
| `opportunity-progress` | 理解商机经过，按依据整理沟通、待办和下一步 |
| `proposal-preparation` | 检索案例与伙伴，保存有来源的提案工作稿 |
| `marketing-workflow` | 整理营销活动或项目的计划、步骤、产物与进度 |

提案工作稿不等于已生成或发送 HTML、PPT；营销计划不执行外部发送、广告投放或排期。资料正文和上传的 Skill 都是来源材料，不能增加权限、切换身份或自动安装执行程序。

## 更新与兼容包

在 Codex 更新「TENBIL 团队」插件源后，按原生插件页提示更新。插件源可公开读取，业务接口仍需要本人登录与授权；公开安装文件不会开放团队资料。

TENBIL 设置保留 ZIP 兼容包。使用时将 ZIP 解压到一个独立、可长期保留的用户目录，确认里面同时有 `.agents/plugins/marketplace.json` 和 `plugins/tenbil/`。不要从临时目录注册，也不要覆盖其他插件或重写已有配置。以该解压目录作为本地插件源，仍通过原生 TENBIL 图标点击安装；不要把 ZIP 发给 Agent 代装。

本源没有固定密钥、用户数据、安装脚本或生命周期 hook。MCP 地址为 `https://connect.library.peckperk.com/mcp`，使用 OAuth 服务发现与动态客户端注册。布局为 `.codex-plugin/plugin.json`、`.mcp.json` 与 `skills/`，参见 [OpenAI 官方插件打包文档](https://developers.openai.com/plugins/build/plugins)。
