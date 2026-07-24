# WorkBuddy OPC 认证备考教练（Claude Code Skill）

把腾讯云《WorkBuddy OPC 认证课程》变成你的私人考官：11 章考点笔记 + 219 道题库 + 错题本 + 进度追踪，用 Claude Code 的 Skill 机制实现随开随练。

## 这是什么

一个 Claude Code Skill，安装后输入 `/WorkBuddy-opc-exam-prep` 即可唤起备考教练，提供五种模式：

1. **章节测验** — 指定章节抽题，逐题作答、即时批改、解析定位到考点
2. **模拟考试** — 全 11 章混抽 30 题，考完统一评分，输出各章得分明细和薄弱点 Top3
3. **错题重练** — 答错的题自动进错题本，连对 2 次标记「攻克」
4. **考点速记** — 考前快速过一遍某章核心概念和易混点对照表
5. **学习报告** — 各章正确率、未攻克错题数、模考历史、下一步建议

## 内容构成

| 文件 | 说明 |
|------|------|
| `SKILL.md` | Skill 入口：考官教练角色 + 五种模式交互规则 |
| `references/` | 11 章考点笔记（含易混点速记表）+ `exam-map.md` 跨章考点地图 |
| `questions/` | 11 章题库共 219 题（单选 118 / 多选 47 / 判断 36 / 场景应用 18），每题带答案、解析、考点定位 |

课程章节：01 产品基础｜02 任务创建｜03 助理连接｜04 技能｜05 连接器｜06 灵感｜07 资料库｜08 自动化｜09 专家中心与模型配置｜10 办公场景｜11 OPC 概念与专家团

## 安装方式

### 直接让 Agent 安装

在 Claude Code、Codex 等支持 Agent Skills 的工具里，直接发送指令：

```plaintext
帮我安装这个 skill：https://github.com/muzhi-tech/WorkBuddy-opc-exam-prep
```

### 手动安装

```bash
git clone https://github.com/muzhi-tech/WorkBuddy-opc-exam-prep.git

# Codex
mkdir -p ~/.codex/skills
cp -R WorkBuddy-opc-exam-prep ~/.codex/skills/

# Claude Code
mkdir -p ~/.claude/skills
cp -R WorkBuddy-opc-exam-prep ~/.claude/skills/
```

如果你的 Agent 暂时不支持 Skill 安装，也可以把项目内的 SKILL.md 和它引用的资源放进项目，让 Agent 按照其中的流程执行。

练习产生的错题和进度会写入 `wrongbook.md` / `progress.md`（已 gitignore，不会污染仓库）。

## 制作方法（如果你想做自己的备考 Skill）

1. 课程视频 → 语音转写为 txt 逐字稿
2. **清洗**：修 ASR 错词、去口播废话、加 Markdown 结构（只清洗不提炼）
3. **提炼**：每章产出考点笔记（保留枚举类知识点，加易混点对照表）
4. **出题**：每章 14~22 题，单选/多选/判断/场景应用混合，答案+解析+考点定位
5. **写 SKILL.md**：定义教练角色、练习模式、批改与错题记录规则

本项目 11 章内容全程由 Claude Code 并行 subagent 加工完成。

## 版权说明

本仓库内容提炼自腾讯云《WorkBuddy OPC 认证课程》，仅供个人学习备考交流使用，不作商业用途。原始课程逐字稿未包含在本仓库中。课程版权归腾讯云所有，如有侵权请联系删除。

## License

MIT（SKILL.md 及配套结构文件）；课程衍生内容版权归原作者所有。
