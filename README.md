# 挖我 neo-wawo-skill

**记者式采访 + 初稿写手**，治「有经历、想表达，却不知道写什么、怎么写」。

不需要提前准备任何东西。一个问题开局，你随口说，它顺着你的话追问，聊着聊着选题自然浮出来，然后深采写成第一人称初稿。

## 能输出什么

wawo 不只帮你写故事。通过采访挖掘，它能帮你产出四类内容的初稿：

| 类型 | 说明 | 例子 |
|---|---|---|
| **故事** | 有场景、有转折的个人经历叙事 | 「我试了五个方向，全亏了」 |
| **观点** | 基于亲身经历的立场和看法 | 「为什么我认为 XX 是扯淡的」 |
| **方法论** | 从踩坑经历中提炼的框架 | 「合伙前问自己的三个问题」 |
| **进行时** | 还没想通的问题，正在纠结的事 | 「我知道该怎么做，但就是做不到」 |

四种类型地位平等，走同一套采访→深挖→出稿流程。产出的都是初稿，都需要你调整。

## 怎么用

喊 `/wawo`（或 `/挖我`、「采访我」「帮我把这个经历写出来」「我想写点东西」）。

**首次使用（Phase 1 → 2）：**
1. **深度了解** → 每轮 30 题，共 10 轮，先把你这个人搞懂（可跨多次会话，进度自动续接）
2. **内容种子提取** → Phase 1 结束后自动从经历中提取四类内容种子

**了解完成后（Phase 3-9）：**

3. **破冰** → 一个小问题开局（「最近什么事还在你脑子里转？」）
4. **滚雪球** → 每个问题从你上一句话里长出来，自由探索
5. **选题浮现** → 聊到某个点，它指出「这就是一条好内容」，你觉得对就往下
6. **深采** → 围绕选题聚焦追问，拿到全部真实细节
7. **出初稿** → 它用你说的素材写第一人称初稿
8. **改稿** → 你提意见，它改，来回几轮直到你满意
9. **沉淀** → 存档 + 新经历写成卡片

随时可以说「跳过」跳出 Phase 1，或带着明确话题来直接进入采访。

## 搭配 neo-write（可选）

wawo 的初稿可以交给 [neo-write-skill](https://github.com/ImNeo-hub/neo-write-skill) 用声音档案精修成成品，但这不是必须的。wawo 单独使用完全可以独立完成从采访到初稿的全流程。

- **wawo**：从零开始采访到初稿。核心价值是把你脑子里雾状的经历变成文字。
- **neo-write**（可选）：拿已有文稿用你的声音精修成成品。

## 冷启动

第一次用不需要准备任何东西。wawo 自动进入 Phase 1（深度了解），通过 10 轮结构化问答建立对你的理解。进度跨会话自动续接——中途退出下次继续，不用从头来。

可选：如果手上有旧的经历素材（笔记、AI 对话导出等），跑 `/wawo-learn` 可以预先蒸馏成卡片（见 `learn.md`），但这不是必须步骤。

## 安装

1. 克隆到本地：
   ```bash
   git clone https://github.com/ImNeo-hub/neo-wawo-skill.git
   ```
2. 软链到 skills 目录（Claude Code 和 Codex 都支持）：
   ```bash
   ln -s /path/to/neo-wawo-skill ~/.claude/skills/neo-wawo-skill
   ln -s /path/to/neo-wawo-skill ~/.codex/skills/neo-wawo-skill
   ```
3. 创建私有目录（存放你的个人内容，不会进仓库）：
   ```bash
   mkdir -p ~/Documents/neo-wawo-skill-private/{drafts,written,wawo-private-experience-cards}
   ```
4. 复制模板并填入你的配置：
   ```bash
   cp neo-wawo-skill/memory/private-config.template.md ~/Documents/neo-wawo-skill-private/private-config.md
   cp neo-wawo-skill/memory/topics.template.md ~/Documents/neo-wawo-skill-private/topics.md
   cp neo-wawo-skill/memory/wawo-state.template.md ~/Documents/neo-wawo-skill-private/wawo-state.md
   ```
5. 创建软链（把私有目录链入 memory/）：
   ```bash
   cd neo-wawo-skill/memory
   ln -s ~/Documents/neo-wawo-skill-private/wawo-private-experience-cards cards
   ln -s ~/Documents/neo-wawo-skill-private/topics.md topics.md
   ln -s ~/Documents/neo-wawo-skill-private/drafts drafts
   ln -s ~/Documents/neo-wawo-skill-private/written written
   ln -s ~/Documents/neo-wawo-skill-private/private-config.md private-config.md
   ln -s ~/Documents/neo-wawo-skill-private/wawo-state.md wawo-state.md
   ```
6. 在 Claude Code 里喊 `/wawo`，开始。

## 文件

| 文件 | 作用 |
|---|---|
| `SKILL.md` | 流程主控（LLM 入口） |
| `interview.md` | 采访引擎：破冰→滚雪球→选题浮现→深采 |
| `coach.md` | 写稿/改稿手册 |
| `questions.md` | 备用弹药（聊不起来时翻） |
| `knowledge-base.md` | 沉淀层：选题库 + 成品归档 |
| `learn.md` | 蒸馏手册（/wawo-learn，可选） |
| `memory/*.template.md` | 私有配置/选题库/状态追踪的模板 |

## 隐私

真实个人内容（经历卡片、选题库、成品、状态文件）全部物理存放在仓库**外**的私有目录，通过软链接入 `memory/`，被 `.gitignore` 屏蔽。仓库里只有引擎和模板，永不包含任何个人数据。

## License

[MIT](LICENSE)
