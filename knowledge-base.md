# 沉淀层：选题库 + 成品 + 喂养 neo-write

每次采访结束后的收尾动作。用户每写一篇，这里就长一点。

## 三个私有文件/目录
- `memory/cards/` —— **经历卡片库**：采访中挖到的真实经历，按 `learn.md` 格式沉淀。每次采访都是卡片库的天然来源——不需要专门跑 `/wawo-learn`，采完顺手存就行。
- `memory/topics.md` —— **选题库**：已浮现的选题 + 状态（待写 / 已写）。
- `memory/written/` —— **成品归档**，按月一个文件。

## 采访后沉淀（Phase 8）

### 经历卡片
采访中挖到的新经历 → 按 `learn.md` 的卡片格式写进 `memory/cards/01-厚卡.md`。每次采访自然产出 1-3 张新厚卡。这是卡片库最好的生长方式——一手叙述，天然是厚卡。

### 选题记录
追加进 `memory/topics.md`：
```
- [已写] 一句话选题 — YYYY-MM-DD
```
或者采访中浮现了但这次没写的：
```
- [待写] 一句话选题 — 来自 YYYY-MM-DD 采访
```

### 成品归档
存进 `memory/written/YYYY-MM.md`：
```
## YYYY-MM-DD · [选题]
是否已喂 neo-write：否

[定稿全文]
```

## 交接 neo-write（可选闭环）
如果用户安装了 neo-write，用户自己写的（经 wawo 采访 + 初稿 + 用户改过的）真东西，是喂养 neo-write 声音档案**最好的语料**。定稿后提示用户：
> 这篇可以喂给 neo-write 当语料 → 跑 `/nws-learn` 校准你的声音。

喂过之后在 written 里把「是否已喂 neo-write」改成「是」。没有 neo-write 的用户跳过这一步即可。

## 增长信号
- 某个方向已写 **5+ 篇** → 提议连成系列或攒长文
- 选题库里「待写」积累多了 → 下次 /wawo 开局时可以提一嘴

## 隐私
`cards/`、`topics.md`、`written/`、`drafts/`、`private-config.md` 真身都在仓库**外**（私有目录），memory/ 里只是软链且被 `.gitignore` 屏蔽。开源只走引擎，私人内容物理隔离、永不上传。
