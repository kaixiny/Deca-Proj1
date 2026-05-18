# EVD & KBN 长青化运营策略演变报告 — 红队审查

**审查对象**：`deca_evd_kbn_evergreen_draft.md`
**审查时间**：2026-05-17
**审查方法**：对 draft 中所有 HIGH/MEDIUM 置信度声明逐一 fetch 原始页面核实

---

## 审查结论汇总

| 编号 | 声明 | 验证结果 | 来源 |
|------|------|----------|------|
| A1 | KBN iOS 公测日期 2011-11-21，正式上线 2012-03-01 | ✅ 通过 | [Wikipedia: Kingdoms of Camelot](https://en.wikipedia.org/wiki/Kingdoms_of_Camelot) |
| A2 | KBN 2012 年成为 iOS 年度最高销售榜首 | ✅ 通过 | [Wikipedia: Kingdoms of Camelot](https://en.wikipedia.org/wiki/Kingdoms_of_Camelot) |
| A3 | Kabam 于 2016-01-07 将 KBN 等游戏售予盖娅互娱 | ✅ 通过 | [Wikipedia: Kingdoms of Camelot](https://en.wikipedia.org/wiki/Kingdoms_of_Camelot) |
| A4 | Embracer 于 2020-08-13 以 €25M + 最高 €60M 对赌收购 Deca | ✅ 通过 | [Embracer 官方新闻稿](https://embracer.com/releases/embracer-group-acquires-deca-games/) |
| A5 | Deca 预测利润率 >35%，净销售 >€20M（Apr 2020-Mar 2021）| ✅ 通过 | [Embracer 官方新闻稿](https://embracer.com/releases/embracer-group-acquires-deca-games/) |
| A6 | Deca 2022 财年收入 €156.05M，814 名员工 | ✅ 通过 | [Wikipedia: Deca Games](https://en.wikipedia.org/wiki/Deca_Games) |
| A7 | Jufeng Studio 2021 年 10 月被 Deca 收购 | ✅ 通过 | [Wikipedia: Deca Games](https://en.wikipedia.org/wiki/Deca_Games) |
| A8 | 飓风工作室：50 人团队，北京 CBD | ✅ 通过 | [Embracer Jufeng 新闻稿](https://embracer.com/releases/embracer-group-acquires-mobile-game-developer-jufeng-studio-and-eight-mobile-titles/) |
| A9 | 八款游戏：~150,000 DAU / ~800,000 MAU / ~SEK 5,000 万季度毛收入（2021-Q3）| ✅ 通过 | [Embracer Jufeng 新闻稿](https://embracer.com/releases/embracer-group-acquires-mobile-game-developer-jufeng-studio-and-eight-mobile-titles/) |
| A10 | 99%+ 收入来自亚太以外 | ✅ 通过 | [Embracer Jufeng 新闻稿](https://embracer.com/releases/embracer-group-acquires-mobile-game-developer-jufeng-studio-and-eight-mobile-titles/) |
| A11 | EVD App Store 评分 2.2/5（465 评） | ✅ 通过 | [Apple App Store - EVD](https://apps.apple.com/us/app/elves-vs-dwarves/id1231491435) |
| A12 | KBN App Store 评分 3.1/5（413 评） | ✅ 通过 | [Apple App Store - KBN](https://apps.apple.com/us/app/kingdoms-of-camelot-battle/id476546099) |
| A13 | EVD v17.0.4（2026-03-17）上线 Battle Pass | ✅ 通过 | [Apple App Store - EVD](https://apps.apple.com/us/app/elves-vs-dwarves/id1231491435) |
| A14 | EVD v16.9.0（2024-11-19）转盘优化加入保底与连抽 | ✅ 通过 | [Apple App Store - EVD](https://apps.apple.com/us/app/elves-vs-dwarves/id1231491435) |
| A15 | EVD v16.9.1（2024-12-13）英雄解锁至 6-10 星 | ✅ 通过 | [Apple App Store - EVD](https://apps.apple.com/us/app/elves-vs-dwarves/id1231491435) |
| A16 | **⚠️ EVD v16.9.3 日期标注错误**：draft 写 "2025-02"，实际为 2025-05-08 | ❌ 错误 | [Apple App Store - EVD](https://apps.apple.com/us/app/elves-vs-dwarves/id1231491435) |
| A17 | EVD v16.9.3 功能：聊天翻译 + 英雄 6 级装备 | ✅ 通过 | [Apple App Store - EVD](https://apps.apple.com/us/app/elves-vs-dwarves/id1231491435) |
| A18 | KBN v22.4.0（2024-11-06）传奇骑士系统上线 | ✅ 通过 | [Apple App Store - KBN](https://apps.apple.com/us/app/kingdoms-of-camelot-battle/id476546099) |
| A19 | KBN v22.8.0（2026-01-22）城市光环系统 + 周年皮肤 | ✅ 通过 | [Apple App Store - KBN](https://apps.apple.com/us/app/kingdoms-of-camelot-battle/id476546099) |
| A20 | Embracer 重组 2023 年 6 月宣布；4,532 人离职；44 工作室关闭 | ✅ 通过 | [Wikipedia: Embracer Group](https://en.wikipedia.org/wiki/Embracer_Group) |
| A21 | Savvy Games Group 约 20 亿美元投资意外终止 | ✅ 通过 | [Wikipedia: Embracer Group](https://en.wikipedia.org/wiki/Embracer_Group) |
| A22 | Hobbit 游戏 2017-06-30 关闭，原因为 IP 授权到期 | MEDIUM（多搜索结果一致，但主页面 403/SSL 错误，未能直接 fetch 原始页面）| Search results + community sources |

---

## 发现的问题

### 错误 #1（对应 A16）— 严重：日期错误
**位置**：四、EVD 长青化策略演变 → 阶段二更新表格，第 4 行
**错误内容**：`| 2025-02 | v16.9.3 | 添加聊天翻译功能；英雄 6 级装备…`
**实际情况**：v16.9.3 发布日期为 **2025-05-08**（Apple App Store 两次独立 fetch 均显示 "05/08/2025"）。"2025-02" 是相邻版本 v16.9.2（纯 bug 修复）的月份被错误附加给了 v16.9.3。
**修订操作**：将 "2025-02" 改为 "2025-05"

### 降级标注 #1（对应 A22）— 轻微：霍比特人关闭日期置信度调整
**位置**：二、所有权链 2.2 EVD 节点 "2017-06-30 霍比特人 IP 授权到期"
**问题**：多个搜索结果一致支持"2017年6月30日"这一日期，但所有直接 fetch 主页面均返回 403 或 SSL 错误，无法独立 fetch 一手来源页面。
**修订操作**：将该声明的置信度从暗示的 HIGH 降至 **MEDIUM**，并更新置信度统计表。

---

## 审查通过声明

共抽查 22 条，其中：
- ✅ 通过验证：20 条
- ❌ 错误（需修订）：1 条
- ⚠️ 降级（由 HIGH → MEDIUM）：1 条

---

## 红队审查局限性（已知）

1. **同工具同偏差**：初稿与审查均使用 WebFetch，系统性 AI 摘要偏差无法通过内部审查消除。
2. **App Store 版本描述不稳定**：两次 fetch 同一 App Store 页面，部分中间版本（v16.9.8、v17.0.2）描述有差异，疑为 WebFetch AI 模型对截断内容的不同解读。核心声明（Battle Pass、wheel guarantees、hero stars）两次一致，可信度高；边缘版本描述存在轻微不确定性。
3. **Deca 支持页面 403**：support.decagames.com 全系拦截，无法直接验证更新日志原文。
4. **EVD 去 IP 化事件**：Hobbit→EVD 转型是报告的关键叙事节点，但 Tolkien Gateway / LOTR Fandom 等主要来源均返回 403，该声明依赖搜索摘要，存在 1-2 条细节可能不准确的风险。
