# paper-writer-v2-full

IEEE/SCI 论文分章节指导与写作生成技能。用于撰写或指导 Abstract、Introduction、Problem Formulation、Method、Experiment、Ablation、Discussion-Limitations、Conclusion、Rebuttal 等章节。技能面向 IEEE Trans 投稿要求，强调严谨学术表达、叙事闭环、工程价值、可复现性和期刊范式。

## 写作优化要点

- 所有文献综述统一整合在 Introduction 内部，不再单独设置 Related Work；
- Experimental Setup 从现实挑战开篇，并与 Introduction 形成叙事闭环；
- Abstract 按“具体痛点 → 现有方法失效场景 → 本文工作 → 贡献与意义”组织，不要堆叠数据结果，最多保留一个关键量化结果；
- Introduction 给出 3-4 条可验证贡献，并在末尾简要说明全文结构；
- 新增 Problem Formulation，形式化输入、输出、优化目标、约束和符号体系；
- Method 必须先给总体架构图，再展开模块；公式前后必须给出动机和自然语言解释；
- Experiments 强调公平可复现，结果不只列表格，还要解释有效场景、有限提升和失败样例；
- 消融每一组都要对应一个设计假设，Discussion 必须坦诚报告固有局限；
- 整体采用被动、客观学术表达，不使用营销化形容词；图表必须被正文引用且图注表注自解释。

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

如果需要“按照本工程已经完成的实验结果撰写论文”，必须先以当前工程中的实验结果、表格、日志或报告为准，再生成相应章节；缺失结果不得编造。

技能会按顺序输出以下三部分：

1. `Section-Structure`
2. `Writing-Sample`
3. `Pitfall-Notice`

技能只使用用户提供的信息，不会虚构创新点、实验数据、Baseline 或符号定义。
