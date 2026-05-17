# Deca 中国工作室 AI 组面试 - 赛道一项目

本项目是 Deca 中国工作室 AI 组的面试题答卷,展示了一套从"研究"到"配图"到"自动推送"的完整 AI 内容生产流水线。

## 项目能力(Skill 索引)

本项目通过 3 个独立 skill 提供 4 个完整能力。Claude Code 应根据用户指令自动触发对应 skill。

### Skill 1: company-research

**位置**: `.claude/skills/company-research/SKILL.md`

**能力**: 在零先验信息条件下(未知缩写、不完整公司名),研究垂类公司旗下产品的特定主题,产出带可信度分级的结构化报告。

**触发场景**:
- "研究 XX 公司旗下 YY 产品的某主题"
- "未知缩写 ABC 对应什么"
- "做一份带可信度分级的研究报告"

**产物**: draft / audit / final 三件套报告。

### Skill 2: bilibili-publish

**位置**: `.claude/skills/bilibili-publish/SKILL.md`

**能力**: 自动发布图文文章到 B 站专栏(含 1920×1080 规格的配图自动生成)。

**触发场景**:
- "发到 B 站"
- "B 站专栏发布"
- "把这篇文章自动投稿 B 站"

**产物**: 已发布的 B 站专栏。

### Skill 3: xiaohongshu-publish

**位置**: `.claude/skills/xiaohongshu-publish/SKILL.md`

**能力**: 自动发布图文笔记到小红书(含 1242×1660 封面 + 1242×1242 内容图规格的配图自动生成)。

**触发场景**:
- "发小红书"
- "小红书笔记发布"
- "把图文内容发到小红书"

**产物**: 已发布的小红书笔记。

## 典型工作流

3 个 skill 可以**独立使用**,也可以**串联**形成完整内容生产流水线:
   company-research → 产出可信报告
   ↓
   bilibili-publish → 把报告改写为 B 站专栏并发布(含自动配图)
   ↓
   xiaohongshu-publish → 把报告改写为小红书笔记并发布(含自动配图)

## 项目目录结构
   Deca-Proj1/
   ├── .claude/skills/         ← 3 个独立 skill
   │   ├── company-research/SKILL.md
   │   ├── bilibili-publish/SKILL.md
   │   └── xiaohongshu-publish/SKILL.md
   ├── reports/                ← 研究报告输出
   │   ├── v1_naive.md         ← V1 基线(零工作流)
   │   ├── v1_audit.md         ← V1 红队审查
   │   ├── v2_with_workflow.md ← V2 工作流驱动
   │   ├── v2_audit.md
   │   ├── v3_draft.md         ← V3 初稿(保留作证据)
   │   ├── v3_audit.md         ← V3 红队审查
   │   ├── v3_final.md         ← V3 修订版(可发布)
   │   └── publishable/        ← 平台适配版本
   │       ├── bilibili_article.md
   │       ├── xiaohongshu_post.md
   │       └── images/         ← 10 张配图
   ├── notes/
   │   ├── iteration_log.md            ← V1→V3 完整迭代日志
   │   └── v3_engineering_report.md    ← 工程总结报告
   └── CLAUDE.md(本文件)