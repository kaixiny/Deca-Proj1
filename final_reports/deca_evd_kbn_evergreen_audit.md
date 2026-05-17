# 红队审查报告：deca_evd_kbn_evergreen_draft

**审查时间**: 2026-05-17  
**审查对象**: `deca_evd_kbn_evergreen_draft.md`  
**审查方法**: 对初稿中每条 HIGH/MEDIUM 声明独立 fetch 原始页面验证

---

## 审查结果汇总

| 序号 | 声明摘要 | 状态 | 原始页面验证 | 置信度判定 |
|------|----------|------|-------------|-----------|
| A1 | 聚风2015年成立、北京CBD、50人、An An任MD、99%+ 收入来自亚太区外 | ✅ 通过 | [Embracer 官方公告](https://embracer.com/releases/embracer-group-acquires-mobile-game-developer-jufeng-studio-and-eight-mobile-titles/) | HIGH → HIGH |
| A2 | Q3 2021 DAU 15万、MAU 80万、营收约 SEK 5000万 | ✅ 通过 | 同上 | HIGH → HIGH |
| A3 | KBN 2012年3月1日上线，当年App Store最高营收iPhone游戏 | ✅ 通过 | [Wikipedia](https://en.wikipedia.org/wiki/Kingdoms_of_Camelot) | HIGH → HIGH |
| A4 | KBN 2016年1月7日 Kabam 售予 Gaea Mobile | ✅ 通过 | 同上 | HIGH → HIGH |
| A5 | KBN 9.5M玩家、68+国App Store #1 | ✅ 通过（来源修正） | [App Store 官方页面](https://apps.apple.com/us/app/kingdoms-of-camelot-battle/id476546099) | MEDIUM → MEDIUM（来源为开发商自述） |
| A6 | Kabam 2013年营收$3.6亿 | ⚠️ 来源降级 | 维基百科记载为整个 Kabam 公司营收，KBN 为主要贡献游戏之一，表述本身无误但原来源(Wikipedia)非一手来源 | MEDIUM → LOW |
| A7 | Embracer 2023年重组裁员"逾4500人" | ❌ 数字错误 | [Udonis 分析](https://www.blog.udonis.co/mobile-marketing/mobile-games/embracer-group-layoffs) | 实际累计裁减约 **7,800人**，关闭44工作室，取消80项目 |
| A8 | EVD 前身为霍比特人:中洲王国，更名后保留玩家进度 | ⚠️ 来源为玩家博客 | [komhelp.wordpress.com](https://komhelp.wordpress.com/elves-vs-dwarves/) 为非官方 | MEDIUM → LOW |
| A9 | EVD 版本历史（v16.7.4 至 v17.0.7）各项功能描述 | ✅ 通过 | [soft112](https://elves-vs-dwarves-ios.soft112.com/) + [App Store](https://apps.apple.com/us/app/elves-vs-dwarves/id1231491435) | MEDIUM → MEDIUM |
| A10 | KBN 版本历史各版本时间线 | ✅ 通过（部分补充） | [soft112](https://kingdoms-of-camelot-battle.soft112.com/) + [App Store](https://apps.apple.com/us/app/kingdoms-of-camelot-battle/id476546099) | MEDIUM → MEDIUM |
| A11 | KBN Google Play 评分 3.6/5（56,800评论）| ✅ 通过 | App Store 显示3.1/5（413条），Google Play 显示3.6/5；两平台数据不同，草稿引用的是Google Play数据，需注明平台 | MEDIUM → MEDIUM（需标注平台） |

---

## 重要发现：草稿遗漏的内容更新

**补充发现**：App Store 版本历史记录的 KBN v22.4.0（2024 年 11 月 6 日）新增了以下重要内容，草稿未覆盖：
- 动态城堡皮肤（Dynamic Castle Skins）
- **英雄皮肤系统（Hero Skin System）** ← 重要新系统
- 行军皮肤（March Skins）
- 传奇骑士（Legendary Knights）
- **装备进化系统（Gear Evolution System）** ← 重要新系统

来源：[App Store 版本历史](https://apps.apple.com/us/app/kingdoms-of-camelot-battle/id476546099)  
建议在 final 中补充到 Phase 4 部分。

---

## 详细审查记录

### 审查 #A7：Embracer 裁员数字错误

- **初稿声明**："累计裁员逾 4500 人、关闭 44 个工作室"
- **问题**：4,500 人是某一统计截点（2023年6月至2024年5月）的数字，并非最终总数
- **实际数据**（来源：[Udonis/Embracer Group Layoffs](https://www.blog.udonis.co/mobile-marketing/mobile-games/embracer-group-layoffs)）：
  - 裁员总计约 **7,800 人**（Embracer 员工从 15,700 缩减至约 7,900，减少超 50%）
  - 关闭工作室：**44 个**（此数字正确）
  - 取消项目：**80 个**（初稿未提及）
- **修订方向**：将裁员数字从 "4500" 更正为 "约 7,800"，补充取消项目数

### 审查 #A6：Kabam 2013 营收来源

- **初稿声明**："Kabam 整体游戏组合 2013 年营收达 3.6 亿美元"
- **问题**：维基百科引用的二手数据，原始来源为当时媒体报道，并非 Kabam 官方财报
- **结论**：数字本身可信但置信度应从 MEDIUM 降至 LOW

### 审查 #A8：EVD Hobbit IP 来源

- **初稿声明**：EVD 前身为 The Hobbit: Kingdoms of Middle-earth，更名后玩家进度保留
- **问题**：来源为玩家非官方博客 komhelp.wordpress.com
- **部分佐证**：App ID 仍为 com.kabam.evd，包名中的 "evd" 与 Elves vs Dwarves 匹配；原始游戏也由 Kabam 开发，IP 关系逻辑合理
- **结论**：内容合理但置信度应保持 LOW，需在 final 中注明"未找到官方声明"

---

## 已知局限（Audit 失效场景）

1. **soft112 日期准确性**：该站点为第三方聚合，部分版本日期可能与实际上线日期有1-3天误差
2. **KBN 早期版本功能**（2021–2023）：多数更新说明仅记录版本号和时间，无详细功能描述，无法一一验证
3. **聚风工作室 2023 年后的内部影响**：Embracer 重组期间聚风是否受直接影响，未找到任何一手声明

---

## 修订清单

| 编号 | 位置 | 修订类型 |
|------|------|----------|
| R1 | 第五部分 5.3 Embracer 重组段 | 裁员数字从 "4500" 改为 "约 7,800" |
| R2 | 第四部分 Phase 4 | 补充 KBN v22.4.0 英雄皮肤 + 装备进化系统 |
| R3 | 第四部分 4.2 Kabam 营收 | 置信度从 MEDIUM 降至 LOW |
| R4 | 第三部分 3.2 EVD IP 来源 | 置信度从 MEDIUM 降至 LOW，标注"来源为非官方" |
| R5 | 第四部分 4.2 KBN 峰值数据来源 | 来源改为 App Store 官方页面（而非 PocketGamer）|
