# paper-writer-v2-full

IEEE/SCI 论文分章节指导与写作生成 skill。用于撰写或指导 Abstract、Introduction、Related Work、Method、Experiment、Ablation、Discussion-Limitations、Conclusion、Rebuttal。

## Install for Codex

In Codex, users can directly install this skill by pasting the repository URL:

```
给我安装 https://github.com/SergioTermann/paper-writer-v2-full 的 skill
```

Equivalent CLI command:

```bash
python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --url https://github.com/SergioTermann/paper-writer-v2-full \
  --path . \
```

If `CODEX_HOME` is set, the skill is installed under `$CODEX_HOME/skills`.

## Install for Claude Code

Clone the repository into the Claude personal skills directory:

```bash
git clone https://github.com/SergioTermann/paper-writer-v2-full.git \
  ~/.claude/skills/paper-writer-v2-full
```

If Claude Code uses a custom `CLAUDE_CONFIG_DIR`, use:

```bash
git clone https://github.com/SergioTermann/paper-writer-v2-full.git \
  "$CLAUDE_CONFIG_DIR/skills/paper-writer-v2-full"
```

## Usage

Provide `section_name` and `user_core_content`. Optional inputs are `target_journal` and `language`.

The skill outputs three sections in order:

1. `Section-Structure`
2. `Writing-Sample`
3. `Pitfall-Notice`

It only uses the information supplied by the user and does not invent innovations, experimental data, baselines, or notation.
