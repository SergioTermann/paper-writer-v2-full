---
name: paper-writer-v2-full
description: >
  IEEE/SCI论文分章节指导与写作生成技能。用于当用户询问论文某一章节或子小节怎么写，或需要撰写 Abstract、Introduction、Method、Experiment、Ablation、Discussion-Limitations、Conclusion、Rebuttal 时。
  不再设置独立 Related Work：所有前人研究与参考文献综述直接整合在 Introduction 内部；Experimental Setup 以现实挑战开篇，先回应论文问题，再展开数据、指标、基线和训练配置。
  当用户要求按照本工程已经完成的实验结果撰写论文时，必须先读取当前工程中的实验结果、表格、日志或报告，并以这些实际结果为准；不得虚构或补全缺失数据。
  输出固定三部分：Section-Structure、Writing-Sample、Pitfall-Notice。
  不编造用户未提供的创新点、实验数据、符号，只依据 user_core_content；严格区分背景、动机、方法、结果；Method 不写实验结果，Experiment 不复述算法原理；不输出 AI 开场白，直接输出结构化内容。
---

# Paper Writer v2 Full

Use `paper_writer_v2_full.yaml` as the authoritative configuration. The required inputs are `section_name` and `user_core_content`; optional inputs are `target_journal` and `language`.

## Workflow

1. Read `paper_writer_v2_full.yaml` and locate the example matching `section_name`.
2. If the requested output contains experiments, ablations, metrics, or results, inspect the current project for completed experiment artifacts such as CSV, JSON, logs, tables, reports, or result directories before drafting.
3. Apply the corresponding `Section-Structure` to organize the response.
4. Produce the three fixed sections in order:
   - `Section-Structure`: paragraph count, purpose, and content of each paragraph.
   - `Writing-Sample`: IEEE-style academic English, preferring passive voice.
   - `Pitfall-Notice`: high-frequency mistakes and prohibited writing patterns for that section.
5. Write the response directly. Do not add an AI preamble.

## Hard Constraints

- Use only the facts supplied in `user_core_content`; never invent innovations, experimental data, baselines, or notation.
- When the user asks to write from this project's completed experiments, use the actual result values found in the project. If those artifacts are absent or incomplete, state the missing artifact and do not invent results.
- Do not create a standalone `Related Work` section. Consolidate all related-work and literature discussion inside `Introduction` using its fixed five-paragraph structure.
- Start `Experimental Setup` with the real-world challenges from the task, then cover dataset, metrics, baselines, and training configuration in order.
- Keep paragraph functions separate: background, motivation, method, and results must not be mixed.
- In `Method`, do not write experimental results.
- In `Experiment`, do not restate the algorithm at length.
- Do not include results in `Introduction`, and do not duplicate algorithm derivation in `Ablation Study`.

## Section Selection

Use the `section_name` enum from `paper_writer_v2_full.yaml`. If the requested section is not listed, ask the user to choose from the supported sections.
