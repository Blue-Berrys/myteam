# AgentRecall 团队资产

此仓库由 agentrecall init 初始化。团队资产在 Git 中共同维护，一次同步更新所有已启用的工作目录。

## 资源

agentrecall.json 使用版本 4 清单：skills、workConfigs、documents、instructions、mcpServers、environment。Skills 放入 skills/；共享指令放入 rules/，同步到 AGENTS.md 或 CLAUDE.md 的团队区块；普通文档放入 docs/。MCP 与公共环境变量直接在清单中维护，密钥只使用 fromEnv 引用，不提交密钥值。

格式与完整示例：https://github.com/zszz3/AgentRecall/blob/main/docs/v2/team-assets.md

## 使用

在 AgentRecall V2 设置中连接团队，再在团队空间接入本地工作目录并选择客户端。点击「同步团队」统一更新，CLI 可运行 team sync。初始化不会自动开启团队功能、安装 Hook、启动 MCP 或上传会话。已有本地内容会受到保护；请在客户端信任工作目录并按需确认 MCP。

## 添加 Skill

创建 skills/review/SKILL.md，YAML frontmatter 包含 name: review 与非空 description，再在清单 skills 中添加 {"id":"review","path":"skills/review"}。提交并推送后，成员可同步使用。
