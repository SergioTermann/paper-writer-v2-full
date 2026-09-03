# paper-writer-v2-full

IEEE/SCI 论文分章节指导与写作生成技能。用于撰写或指导 Abstract、Introduction、Method、Experiment、Ablation、Discussion-Limitations、Conclusion、Rebuttal 等章节。所有文献综述统一整合在 Introduction 内部，不再单独设置 Related Work；Experimental Setup 从现实挑战开篇并与引言形成叙事闭环。

## 在 Codex 中安装

在 Codex 中可以直接粘贴仓库地址安装：

```
给我安装 https://github.com/SergioTermann/paper-writer-v2-full 的 skill
```

等价命令行：

```bash
python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --url https://github.com/SergioTermann/paper-writer-v2-full \
  --path . \
```

如果设置了 `CODEX_HOME`，技能会安装到 `$CODEX_HOME/skills`。

## 在 Claude Code 中安装

将仓库克隆到 Claude 个人技能目录：

```bash
git clone https://github.com/SergioTermann/paper-writer-v2-full.git \
  ~/.claude/skills/paper-writer-v2-full
```

如果 Claude Code 使用了自定义的 `CLAUDE_CONFIG_DIR`，请使用：

```bash
git clone https://github.com/SergioTermann/paper-writer-v2-full.git \
  "$CLAUDE_CONFIG_DIR/skills/paper-writer-v2-full"
```

## 使用方法

提供 `section_name` 和 `user_core_content`。可选输入为 `target_journal` 和 `language`。

技能会按顺序输出以下三部分：

1. `Section-Structure`
2. `Writing-Sample`
3. `Pitfall-Notice`

技能只使用用户提供的信息，不会虚构创新点、实验数据、Baseline 或符号定义。
