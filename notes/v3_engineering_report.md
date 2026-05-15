# Deca 研究任务工程总结

**日期：** 2026-05-15
**覆盖版本：** V1（裸跑基线）→ V2（工作流驱动）→ V3（审查+自动修订）
**产物文件：** reports/v1_naive.md · v1_audit.md · v2_with_workflow.md · v2_audit.md · v3_draft.md · v3_audit.md · v3_final.md

---

## 1. 迭代轨迹

### 1.1 三版量化对比

| 指标 | V1 | V2 | V3_draft | V3_final |
|------|----|----|----------|----------|
| **总声明数** | 46 | 32 | 31 | 30 |
| **HIGH 数 / 占比** | 31 / 67% | 18 / 56% | 22 / 71% | 22 / 73% |
| **MEDIUM 数 / 占比** | 5 / 11% | 14 / 44% | 9 / 29% | 8 / 27% |
| **LOW 数** | 2 | 0 | 0 | 0 |
| **UNVERIFIED（已删除）** | 8 / 17% | 5 | 3 | 3 |
| **审查发现错误数** | 2 确认 + 多 UNVERIFIED | 2 确认 + 1 降级 | 4 项 | — |
| **工作流闭环程度** | 无（事后手动审查） | 有审查，无自动修订 | 审查 + 自动修订 | 修订日志置顶 |

> 注：V2 HIGH 占比（56%）低于 V1（67%），因为 V2 工作流要求更严格的来源分级，将多条仅有单一来源的声明归入 MEDIUM，而不是 HIGH；这是质量提升，不是退步。

### 1.2 错误性质演变

| 版本 | 错误性质 | 代表案例 |
|------|---------|---------|
| V1 | 模型幻觉 + AI 摘要传播链 | Hero's Journey Boss 系统细节（"玩家使用魔法号角"）完全来自 WebSearch AI 摘要，无任何一手页面支持；Slime Balloon Castle 被错误归属到 v16.8.1 而非 v16.8.3 |
| V2 | 工具数据不一致（同一 URL 多次 fetch 返回不同内容窗口） | Battle Pass 版本号：首次 fetch 读到 v17.0.5，二次 fetch 读到 v17.0.4；KBN iOS City Halo System 首次 fetch 归入 v22.8.0，修复后为 v22.7.8 |
| V3 | 跨平台版本号偏移 + 引用归属精度 | App Store 记 Battle Pass 在 v17.0.4，soft112 记为 v17.0.5；Wikipedia/Kabam 被错误引用为 KBN 2012 最高收入游戏的来源（实际文本在 Wikipedia/KoC） |

### 1.3 闭环程度说明

- **V1**：红队审查在工作流之外手动执行，correction 停留在 audit 文档中，未回写进 v1_naive.md。这意味着任何人读 v1_naive.md 都会读到已知错误。
- **V2**：CLAUDE.md 工作流内置红队审查（Step 4a），但无 Step 4b 自动修订机制。v2_audit.md 发现的 2 处错误在 v2_with_workflow.md 中依然存在。
- **V3**：Step 4b 强制产出 v3_final.md，draft 保留为审查证据，final 顶部附修订日志。任何读者打开文件第一屏看到的就是"本版本改了什么、为什么改"。

---

## 2. 关键工程决策

### 2.1 为什么从单步指令拆为 4 步工作流

**V1 指令**（见 notes/指令集.md）：
> "搜集 Deca 中国工作室旗下代理的 EVD、KBN 两个游戏的长青化运营策略演变的信息，产出一份报告"

这是一个无 checkpoint 的单步执行。模型在无人确认的情况下连续完成搜索 → 整合 → 成文三个子任务，没有机会暴露中间状态。结果是 8 条 UNVERIFIED 声明（Hero's Journey、英雄技能分类名称、迷雾远征·雪山等）混入最终报告，其中 Hero's Journey 的"magic horns"细节完全是 AI 摘要的发明。

**V2 改变**：拆为 Step 1（公司识别）→ Step 2（信息搜集）→ Step 3（初稿）→ Step 4（审查修订），每步结束后强制汇报并等待用户"继续"。这个 friction 让两个问题提前暴露：
1. Step 2 搜集阶段会明确标注 UNVERIFIED，而不是等到成文后才发现
2. Step 3 输出前已知道哪些声明没有一手来源，决定删还是保

**实际效果**：V2 报告的 UNVERIFIED 从 V1 的 8 条降至 0 条（5 条删除，报告中不再出现）。

### 2.2 为什么强制 fetch 原始页面而非 AI 摘要

WebSearch 返回的 AI 摘要存在两个结构性问题：

1. **时间漂移**：V1 的 KBN City Halo System 时间被 AI 摘要写成"2023 年 12 月"，而直接 fetch App Store 页面显示是 2025 年 11 月（v22.7.8）——时间差超过 2 年。原因是 AI 摘要可能引用了过期的搜索索引快照。

2. **幻觉注入**：V1 的"英雄技能系统（步兵/弓兵/骑兵防御技）"和"Hero's Journey Boss 召唤系统"均来自 WebSearch AI 摘要，在任何 App Store 版本历史、官方公告或 apk.gold changelog 中均找不到对应文本。V1 audit D21-D22 均标注为 UNVERIFIED。

CLAUDE.md 中的强制规则是：
> WebSearch 给出声明但无具体页面 URL → 二次搜索找原始页面 → 找不到则降级为 UNVERIFIED

这个规则让 V2 的公司背景类声明（15 条 HIGH，全部有官方公告或 Wikipedia 原文支持）保持 100% 准确率通过 V2_audit 验证。

**代价**：WebFetch 的工具精度问题（见第 5 节）导致了 V2 的两处新型错误，但这是工具精度上限问题，而非工作流设计问题。

### 2.3 为什么分离 draft / audit / final 三件套

**V2 的问题**：v2_with_workflow.md 是唯一的报告文件；v2_audit.md 发现了 2 处错误，但这 2 处错误在 v2_with_workflow.md 中永久保留，没有"修订后的权威版本"存在。

任何后续读者需要同时持有两份文件（report + audit）才能得到准确信息。这是一个信息可访问性问题。

**V3 三件套设计逻辑**：

| 文件 | 角色 | 为什么不能合并 |
|------|------|--------------|
| `v3_draft.md` | 时间戳快照 + 审查证据 | 必须保持不变，否则 audit 的"修订前"失去对照 |
| `v3_audit.md` | 错误发现记录 | 作为判定依据；禁止凭空修改的保障机制 |
| `v3_final.md` | 权威可分发版本 | 修订日志置顶，读者不需要读 audit 也能知道"本版本已知的修改" |

这个设计的附加价值：防止"凭空修改"。CLAUDE.md 的强制要求是：
> 修订必须基于 audit 报告的明确判定，禁止凭空修改。如果 audit 中没有标记为错误的声明，最终版也不能改它。

### 2.4 为什么用 CLAUDE.md 而非 SKILL.md 进行迭代

`skills/company-game-research/SKILL.md` 当前只有一行前端注释（stub），内容为空。这是有意为之的决策，原因如下：

**CLAUDE.md 的特性**：
- 作为项目级持久化指令，每次对话自动加载
- 内容可以在两轮研究之间修改，修改立即生效
- 工作流本身是"正在迭代的产物"

**迭代过程中需要修改工作流的场景**：
- V1→V2：增加 4 步分解、强制置信度标签、UNVERIFIED 删除机制
- V2→V3：增加 Step 4b 自动修订、分离 draft/audit/final、修订日志置顶强制规则

如果把 V1 的工作流直接固化进 SKILL.md，V2 就需要修改 SKILL.md 本身——而 SKILL.md 被设计为跨项目复用的稳定工具，不适合边迭代边修改。

**时序原则**：
1. 用 CLAUDE.md 在项目内迭代，直到工作流稳定（现为 V3 状态）
2. 稳定后将工作流提炼进 SKILL.md，作为下一个项目的起点（见第 6 节）

---

## 3. 错误演化分析

### 3.1 V1 错误：模型幻觉（工作流问题）

V1 的 8 条 UNVERIFIED 声明中，有 3 条属于主动幻觉，而非"找不到来源"：

1. **Hero's Journey Boss 召唤系统**（v1_audit D22）：v1 报告写"玩家获得魔法号角，召唤 Boss，联盟协作击杀"。在 App Store、apk.gold、任何官方公告中均无此描述。来源追踪至 WebSearch AI 摘要，是 AI 对 EVD 玩法的想象性补充。

2. **英雄技能分类"步兵/弓兵/骑兵防御技"**（v1_audit D21）：具体技能名称来自 AI 摘要，无 App Store 版本 changelog 可核查。

3. **KBN 迷雾远征·雪山**（v1_audit E4）：专项搜索未返回任何结果，完全无法独立验证。

**根因**：单步指令 + AI 摘要作为来源 = 模型在需要填充细节时直接生成合理听起来的内容，而不是承认"找不到"。

### 3.2 V2 错误：数据源不一致（工具问题）

V2 的 2 处错误性质完全不同：功能本身是真实存在的，只是版本号或日期有偏差。

1. **Battle Pass 版本号**（v2_audit D5）：v2 报告写 v17.0.5，实际为 v17.0.4。两次对同一 App Store URL（`apps.apple.com/us/app/elves-vs-dwarves/id1231491435`）的 fetch 返回了不同的版本列表"窗口"——第一次 fetch 在 v17.0.4 和 v17.0.5 之间产生了归属混淆。

2. **KBN City Halo System iOS 版本**（v2_audit E3）：v2 报告写 v22.8.0（2026-01-22），实际为 v22.7.8（2025-11-20）。首次 fetch 返回的内容与二次 fetch + soft112 交叉验证的结果不一致，后者被判定为正确。

**根因**：App Store 版本历史页面是动态渲染内容，WebFetch 每次获取的"可见窗口"不保证完整，且不同时刻的请求可能触发不同的内容缓存状态。这是工具层面的不可靠性，通过更好的提示词无法解决。

### 3.3 V3 错误：版本号偏移 + 引用归属（工具精度上限）

V3 审查发现的 4 个问题代表了当前工具能力的精度上限：

1. **B8：引用归属精度**（v3_audit）：声明"KBN 2012 年最高收入游戏"引用了 Wikipedia/Kabam + GamesBeat 两个来源，但直接 fetch Wikipedia/Kabam 页面，此声明文本实际不在该页，而在 Wikipedia/KoC（`https://en.wikipedia.org/wiki/Kingdoms_of_Camelot`）。两个 URL 相差一个词，但引用归属是错的。

2. **D10/D11：跨平台版本号偏移**：App Store（iOS）记录 Battle Pass 在 v17.0.4，soft112 记录为 v17.0.5；Campaign Legendary 同样存在 v17.0.6 vs v17.0.7 的一位差异。这是 iOS/Android 版本历史的平台差异——同一功能在不同平台的版本号可以合法地差一位，目前没有工具能权威地确定"哪个是正确的"，只能如实标注冲突。

3. **E4：v22.3.0 城堡皮肤**：App Store v22.3.0 条目仅显示图形渲染修复，无城堡皮肤。v3_final 将此条整段删除；城堡皮肤首次确认出现在 v22.4.0（2024-11-06），见 `https://apps.apple.com/us/app/kingdoms-of-camelot-battle/id476546099`。

### 3.4 结论：Agent 能力 vs 工具能力的边界

```
V1→V2 的质量跃升（-8 条 UNVERIFIED，-幻觉）：
  可通过工作流设计解决 ✅ → 强制 fetch、步骤分解、UNVERIFIED 删除

V2→V3 的质量改进（-2 确认错误）：
  可通过工具精度 + 多源交叉解决 ✅ → 用 App Store 替换 soft112 作为主源

V3 残余问题（版本号一位差、引用归属细节）：
  属于工具精度上限 ⚠️ → 两个权威来源相互矛盾时，Agent 只能记录冲突，无法裁定
```

当错误变成"两个权威来源给出不同答案"时，解决方案不是更好的提示词，而是更好的工具（结构化 API 接入、官方 changelog 数据库）。

---

## 4. 红队审查的可信度分析

### 4.1 为什么 Step 4 比 Step 2 更准

Step 2（信息搜集）和 Step 4（红队审查）都在访问相同的网页，但产出质量不同，原因在于认知模式不同：

| 维度 | Step 2（搜集模式） | Step 4（审查模式） |
|------|-------------------|-------------------|
| 驱动问题 | "这个游戏有什么值得写的？" | "这条声明是否在原始页面上？" |
| 目标 | 最大化信息量 | 发现矛盾 |
| 精力分配 | 广泛扫描多个 URL | 精准 fetch 特定 URL 的特定内容 |
| 对负面结果的态度 | 找不到就跳过 | 找不到 = 需要降级或删除 |
| 确认偏误暴露度 | 高（容易接受 AI 摘要）| 低（比对 draft 中的具体声明）|

V3 audit 发现了 draft 中的 4 个问题，而 Step 2 没有发现——正是因为 Step 4 有明确的"对立假设"：这条声明可能是错的，我要验证它。

### 4.2 审查可信度的 4 个失效场景

**场景 1：URL 腐烂（URL Rot）**
审查发现某 URL 返回 404 或内容已更新，无法验证原始研究时的页面状态。App Store 的版本历史是活文档，随新版本发布滚动更新。v2_audit 发现 v22.7.8 的内容，但 v3 的同一页面又显示不同内容——同一 URL 在不同时间 fetch 可能得到不同版本历史长度。

**场景 2：页面截断（Content Truncation）**
WebFetch 抓取 App Store 版本历史时，会触发动态渲染，只返回"可见屏幕"内的条目。如果目标版本在历史列表的深处，会被截断，研究者和审查者都看不到——两次误差相同，审查无法发现。这是 V2 Battle Pass 版本错误的根本原因：v17.0.4 正好落在截断边界附近，不同次 fetch 的边界位置不一致。

**场景 3：同一工具同一偏差（Tool Systematic Bias）**
如果研究者和审查者都用 WebFetch 访问同一个有 bug 的 URL，且该 URL 稳定地返回错误内容，审查将通过错误内容。在本项目中，v1_audit 使用 WebSearch 审查 v1_naive，而 v1_naive 也由 WebSearch 产生——审查工具和生产工具相同，系统性偏差无法被发现（例如"迷雾远征·雪山"在两次搜索中都没有结果，但这说明它是幻觉，而不是说它是正确的）。

**场景 4：同域不同页（Same Domain, Different Path）**
B8 错误：研究者引用了 Wikipedia/Kabam（`en.wikipedia.org/wiki/Kabam`），审查者也 fetch 了这个 URL 并没有发现矛盾——因为这个 URL 存在且有相关内容，只是目标声明的文本在另一个 URL（Wikipedia/KoC：`en.wikipedia.org/wiki/Kingdoms_of_Camelot`）。审查者需要对比报告中引用的 URL 与实际文本的精确匹配，而不只是"URL 存在且相关"。

### 4.3 改进方向

**独立会话**：在独立会话（无 draft 上下文）中执行审查，避免确认偏误。当前的 Step 4 在同一对话中进行，审查者的"期望"受 draft 影响，更容易在模糊内容上接受而非拒绝。一个没有读过 draft 的独立 Agent 发现 B8 归属错误的概率更高。

**多源交叉**：对每条 HIGH 声明强制要求 ≥2 个不同域名的来源（而不是同一站点的两个页面）。V3 的版本号冲突（D10/D11）正是因为 App Store 和 soft112 两个不同域名的信息不一致才被发现。

---

## 5. 已识别但未解决的问题

### 5.1 WebFetch 的页面截断 + 内容漂移

**现象**：对同一个 URL（`apps.apple.com/us/app/elves-vs-dwarves/id1231491435`）在 V2 研究、V2 审查、V3 研究三次 fetch 中，返回的版本历史长度不同：
- 有时返回到 v17.0.6（Campaign Legendary），有时只到 v17.0.4（Battle Pass）
- soft112 对同一版本历史的记录有时与 App Store 差一位版本号

**影响**：这导致了 V2 的 Battle Pass 版本错误（D5），以及 V3 的 D10/D11 无法最终裁定。

**当前处理方式**：对存在冲突的版本号，改用"约 X 月（App Store 记 vA，soft112 记 vB）"的模糊化表述，并降至 MEDIUM 置信度。

**未解决**：没有办法从工作流层面确保每次 fetch 都能获取完整的版本历史。

### 5.2 单一来源的版本号无法 100% 确认

部分 V3 MEDIUM 声明依赖单一 App Store 来源，缺乏 Android 端交叉验证：

- `v17.0.2（2025-12-01）：坐骑升星至 9 星` — 仅 App Store iOS
- `v22.7.8（2025-11-20）：Special Cards` — App Store iOS（soft112 记为 v22.7.6）

App Store 是 iOS 版的权威来源，但同一功能的 Android 版本号可能不同。当前报告的 MEDIUM 标签准确反映了这个局限。

### 5.3 未来改进方向

**短期（可在现有工具链内实现）**：
- 对每条 MEDIUM 声明的版本号，同时查询 App Store（iOS）和 apk.gold/soft112（Android），记录两平台版本号
- 对 Step 4 新增"独立会话"要求：规则写入 CLAUDE.md，强制使用 `/clear` 或新对话后执行审查

**中期（需要工具升级）**：
- 接入 iTunes Search API（`https://itunes.apple.com/lookup?id=1231491435&country=us`）获取 App Store 结构化数据，避免依赖页面渲染
- 接入 AppFollow 或 AppMagic 等版本历史监控工具，消除截断问题

**长期（架构改变）**：
- 将版本历史数据本地化（定期拉取并存入 JSON），研究和审查都对照本地快照，而不是每次实时 fetch；消除"URL 腐烂"和"内容漂移"两个失效场景

---

## 6. 工作流的可复用性

### 6.1 CLAUDE.md 在本项目内的有效性

在本项目（`C:\Users\Kaixin\Desktop\Deca-Proj1`）中，CLAUDE.md 工作流从 V2 开始运行了两个完整研究周期，有效地：
- 将 UNVERIFIED 从 17%（V1）降至 0%（V2、V3 报告内均无）
- 将 HIGH 声明的审查通过率从 V1 的不可知提升至 V2 的 90%（27/30 通过）和 V3 的 95%+（26/27 高置信声明通过）
- 建立了可追溯的修订链（draft → audit → final）

**当前局限**：CLAUDE.md 针对整个项目目录有效，但本项目目前只做了 Deca 这一个垂类研究。如果项目内需要同时跑两个完全不同的研究任务，CLAUDE.md 的工作流会同时约束两者，缺乏选择性。

### 6.2 向 SKILL.md 迁移的时机与内容

`skills/company-game-research/SKILL.md` 当前为 stub，触发词定义在注释中：
```
description: 在缺少背景信息（如缩写、未知公司名）的情况下，研究垂类公司旗下游戏的特定主题并产出可信度分级的结构化报告。
```

**迁移时机**：V3 工作流已进入稳定状态，下一轮研究预计只会在内容层面而非工作流层面有改动。此时可以提炼。

**应迁入 SKILL.md 的内容**（工作流核心部分，已在 V3 CLAUDE.md 中稳定）：
- Step 1 的缩写反向匹配规则（首字母、拼音、副标题、内部代号等）
- Step 2 的强制溯源机制（AI 摘要降级为 UNVERIFIED）
- Step 4 的 draft / audit / final 三件套输出结构
- 置信度分级标准（HIGH / MEDIUM / LOW / UNVERIFIED 定义）

**不应迁入 SKILL.md 的内容**（项目特定配置）：
- 具体的保存路径（`reports/v3_draft.md` 等）——迁入后应参数化
- 游戏研究特有的来源优先级（App Store > apk.gold）——其他行业需调整

### 6.3 适用场景

| 场景 | SKILL.md 可直接复用的部分 | 需要调整的部分 |
|------|--------------------------|--------------|
| 垂类公司主题研究（游戏/App/SaaS） | 4 步工作流、draft/audit/final 结构、置信度分级 | 来源优先级列表（不同行业的权威来源不同） |
| 未知缩写匹配（任意行业） | Step 1 反向匹配规则（6 类规则）、双源验证要求 | 无（规则通用） |
| 可信度分级报告产出（任意研究任务） | 声明格式（`声明内容 [HIGH] [来源](URL)`）、统计表、UNVERIFIED 删除规则 | 置信度阈值定义（需根据行业调整"权威来源"的定义） |
| App 版本历史追踪（移动端产品分析） | Step 2 的 App Store fetch 优先规则、版本号冲突的模糊化处理方式 | 添加 Android 交叉验证步骤 |

### 6.4 当前版本 CLAUDE.md 的一个已知缺陷

Step 4 审查在**同一会话**中执行，审查者（模型当前状态）读过 draft，存在确认偏误。B8 引用归属错误被 V3 审查发现，是因为审查者特别检查了引用 URL 的文本匹配——但如果审查者已对 draft 内容"预期正确"，可能会在"URL 存在且相关"时就停止，而不深入比对文本。

**建议写入 SKILL.md 的改进规则**：
> Step 4 审查必须在独立会话（`/clear` 后或新对话）中执行，禁止在产出 v3_draft.md 的同一会话中进行审查。

---

*本报告基于以下产物文件的实际数据，所有量化指标均来自对应文件的统计节或 audit 记录，非推断。*

| 文件 | 路径 |
|------|------|
| V1 报告 | reports/v1_naive.md |
| V1 审查 | reports/v1_audit.md |
| V2 报告 | reports/v2_with_workflow.md |
| V2 审查 | reports/v2_audit.md |
| V3 初稿 | reports/v3_draft.md |
| V3 审查 | reports/v3_audit.md |
| V3 修订版 | reports/v3_final.md |
| 迭代日志 | notes/iteration_log.md |
| 工作流 | CLAUDE.md |
