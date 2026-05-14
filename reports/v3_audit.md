# v3_draft 报告红队审查记录

**审查日期：** 2026-05-14
**被审查文件：** reports/v3_draft.md
**审查方法：** 对报告中所有 HIGH 置信度声明，独立使用 WebFetch 直接访问原始页面复验；对可疑 MEDIUM 声明进行交叉核查
**验证工具：** WebFetch 直接访问 Wikipedia（Deca_Games、Kabam、KoC）、Apple App Store（EVD & KBN）、apk.gold（EVD Android changelog）、soft112（EVD iOS changelog）

---

## 声明验证表

### A. 公司与收购事实

| # | 声明 | 验证结果 | 验证来源（本轮直接访问） | 结论 |
|---|------|---------|---------------------|------|
| A1 | Deca Games 于 2016 年在柏林创立 | ✅ 确认 | Wikipedia/Deca_Games（原文："Founded 2016; Headquarters: Berlin, Germany"） | HIGH 维持 |
| A2 | 创始人 Ken Go，前 Kabam 欧洲总部总经理 | ✅ 确认 | 同上（原文："Ken Go, formerly general manager for Kabam's European headquarters"） | HIGH 维持 |
| A3 | Ken Go 曾任 KoC 执行制作人 | ✅ 确认 | PR Newswire 直接 fetch（原文："served as Executive Producer of Kingdoms of Camelot"） | HIGH 维持 |
| A4 | 2020 年 8 月成为 Embracer 第六个运营集团 | ✅ 确认 | Wikipedia/Deca_Games（原文精确："made it as the sixth operative group"） | HIGH 维持 |
| A5 | 聚锋 2015 年成立、北京、约 50 人、前隶属 Gaea | ✅ 确认 | Embracer 官方公告（直接 fetch） | HIGH 维持 |
| A6 | 收购时间 2021 年 10 月 | ✅ 确认 | Wikipedia/Deca_Games + Embracer 官方公告 | HIGH 维持 |
| A7 | An An（Gaea 总裁）出任 Deca 中国办公室 MD | ✅ 确认 | Embracer 官方公告（直接 fetch） | HIGH 维持 |
| A8 | Q3 2021：约 150K DAU、800K MAU、SEK 5000 万 | ✅ 确认 | Embracer 官方公告（直接 fetch） | HIGH 维持 |
| A9 | 99%+ 营收来自亚太区以外 | ✅ 确认 | Embracer 官方公告（直接 fetch） | HIGH 维持 |

### B. 历史时间线

| # | 声明 | 验证结果 | 验证来源（本轮直接访问） | 结论 |
|---|------|---------|---------------------|------|
| B1 | The Hobbit KoME 发布日期 2012-10-16 | ✅ 确认 | Wikipedia/Kabam（原文："2012/10/16"） | HIGH 维持 |
| B2 | Kabam 2013 年营收 $3.6 亿 | ✅ 确认 | Wikipedia/Kabam（原文："$360 million in revenues for 2013"） | HIGH 维持 |
| B3 | KoC 领衔四款游戏合计超 $1 亿 | ✅ 确认 | Wikipedia/Kabam（原文："four of its games – led by Kingdoms of Camelot – grossed more than $100 million"） | HIGH 维持 |
| B4 | Kabam 出售给 Gaea Mobile：2016-01-07 | ✅ 确认 | Wikipedia/Kabam（原文确认） + Wikipedia/KoC（原文："January 7, 2016, Kabam sold…to GAEA Mobile"） | HIGH 维持 |
| B5 | KoC Facebook beta 2009-11-02，正式 2009-11-06 | ✅ 确认 | Wikipedia/KoC（原文：beta Nov 2, release "four days later" Nov 6） | HIGH 维持 |
| B6 | KBN mobile beta 2011-11-21，iOS 正式 2012-03-01 | ✅ 确认 | Wikipedia/KoC（原文精确匹配） | HIGH 维持 |
| B7 | RockYou：2014-12-09 宣布，2015-04 完成 | ✅ 确认 | Wikipedia/KoC（原文："December 9, 2014"；"beginning of April 2015"） | HIGH 维持 |
| B8 | **KBN 是 2012 年 iPhone 最高收入游戏（引用 Wikipedia/Kabam + GamesBeat）** | ⚠️ **来源归属错误**：Wikipedia/Kabam 原文中**不包含**此声明；正确来源应为 **Wikipedia/KoC**（原文："became the top-grossing iPhone app of 2012"）+ GamesBeat | Wikipedia/Kabam 本轮直接 fetch 未找到该声明 | **需修正引用来源**（事实正确，来源有误）|
| B9 | KBN 在超过 50 个国家保持最高收入 | ✅ 确认 | GamesBeat（直接 fetch，原文："highest-grossing apps on iOS in more than 50 countries"） | MEDIUM 维持 |

### C. Deca 策略声明

| # | 声明 | 验证结果 | 验证来源（本轮直接访问） | 结论 |
|---|------|---------|---------------------|------|
| C1 | Ken Go 两段引文（逐字核对） | ✅ 确认 | PR Newswire（直接 fetch，原文完全一致） | HIGH 维持 |
| C2 | 接手 Realm of the Mad God 一年后 DAU 翻倍 | ✅ 确认 | PR Newswire（原文："has seen the amount of daily active users doubled"） | HIGH 维持 |
| C3 | Deca 全栈运营职能列表 | ✅ 确认 | PR Newswire（原文列出 7 个词组，合并"live events and promotion planning"为一项后计为六项，报告计数正确） | HIGH 维持 |

### D. EVD 版本内容（重点核查项）

| # | 声明 | 验证结果 | 验证来源（本轮直接访问） | 结论 |
|---|------|---------|---------------------|------|
| D1 | v16.8.0（2024-02-20）：Altar、Sworn Troop、新职位 | ✅ 确认 | App Store（原文："Add new building 'Altar'…Add Sworn Troop"）+ apk.gold | HIGH 维持 |
| D2 | v16.8.0：幽石洞（Auralite Cave）升至 21 级 | ✅ 确认 | apk.gold（原文："Upgrade Auralite Cave level limit to 21"） | MEDIUM 维持（单一来源；App Store v16.8.0 描述未明确列出此项） |
| D3 | v16.8.0：新 Tech、新英雄与坐骑、新城堡皮肤 | ✅ 确认 | apk.gold（逐项原文确认） | MEDIUM（apk.gold 单源；App Store 描述为"new buildings"未细列） |
| D4 | v16.8.1（2024-03-26）：Slime Balloon Castle + city buff | ✅ 确认 | App Store（原文："Add new castle skin 'Slime Balloon Castle' Add city buff"）+ apk.gold | HIGH 维持 |
| D5 | v16.8.3（2024-04-24）：Stellar Dragon + 地图变更 | ✅ 确认 | App Store（原文："Add new mount: Stellar Dragon Change map Fix some bugs"）+ apk.gold | HIGH 维持 |
| D6 | v16.8.7（2024-07-26）：新城堡皮肤 + Tom 事件修复等 | ✅ 确认 | apk.gold（原文逐项列出六项修复）+ App Store 一致 | HIGH 维持 |
| D7 | v16.8.9（2024-09-10）：Wheel 保底+连抽 + Chat/War Hall 修复 | ✅ 确认 | App Store（原文："Wheel optimization, adding guarantees and consecutive draws"）+ apk.gold | HIGH 维持 |
| D8 | v16.9.0（2024-11-19）：英雄解锁至 6–10 星 | ✅ 确认 | App Store（原文："Heroes unlocked up to 6-10 stars"）+ apk.gold | HIGH 维持 |
| D9 | v17.0.2（2025-12-01）：坐骑升星至 9 星 | ✅ 确认 | App Store（原文："Mount Star-Up expanded to 9 stars, unlocking an exclusive march skin"） | HIGH 维持 |
| D10 | **v17.0.4（2026-03-17）：Battle Pass** | ❌ **来源冲突** | App Store 本轮 fetch：v17.0.4 未见 Battle Pass；**soft112**（直接 fetch）：v17.0.5（Mar 27）含 Battle Pass；v17.0.4 含 Sage's Tower + Castle/March Skins | **需降级为 MEDIUM，版本号标注冲突** |
| D11 | **v17.0.6（2026-04-16）：Campaign Legendary chapter** | ❌ **来源冲突** | App Store 本轮 fetch：v17.0.6 仅"Fixed: Some known issues"；**soft112**：v17.0.7（Apr 23）含 Campaign Legendary；v17.0.6 仅修复 | **需降级为 MEDIUM，版本号标注冲突** |

### E. KBN 版本内容（重点核查项）

| # | 声明 | 验证结果 | 验证来源（本轮直接访问） | 结论 |
|---|------|---------|---------------------|------|
| E1 | v22.4.0（2024-11-06）：城堡皮肤、英雄皮肤系统、行军皮肤、传奇骑士、装备进化 | ✅ 确认 | App Store（原文逐项列出，完全一致） | HIGH 维持 |
| E2 | v22.7.8（2025-11-20）：Special Cards 功能 | ✅ 确认 | App Store（原文："New Feature – Special Cards"） | MEDIUM 维持 |
| E3 | v22.8.0（2026-01-22）：City Halo System + 14 周年皮肤 + OTA 优化 | ✅ 确认 | App Store（原文："New Feature – City Halo System ▶ New Skin – 14th Anniversary City Skin…OTA-related resources"） | HIGH 维持 |
| E4 | **v22.3.0（2024-08-19）：新增城堡皮肤（castle skin）** | ❌ **未确认** | App Store 本轮 fetch：v22.3.0 仅显示图形渲染修复，**无城堡皮肤内容**；WebSearch 亦无法从独立来源确认 | **应删除此声明；城堡皮肤首次确认出现在 v22.4.0** |
| E5 | "14 周年"：KBN mobile 2012-03-01 → 2026 = 14 周年 | ✅ 确认 | Wikipedia/KoC（KBN iOS 2012-03-01）+ App Store（"14th Anniversary City Skin"）计算一致 | HIGH 维持 |

---

## 总体统计

| 类别 | 数量 |
|------|------|
| 验证通过（✅） | 26 条 |
| 已确认错误（❌） | 3 条 |
| 来源归属错误（⚠️） | 1 条 |
| **合计审查** | **30 条** |

---

## 已确认问题详情

### 问题 1：Battle Pass 版本号来源冲突（D10）

| 项目 | 内容 |
|------|------|
| **v3_draft 写法** | v17.0.4（2026-03-17）：新增 Battle Pass |
| **App Store 本轮 fetch** | v17.0.4 未见 Battle Pass；本轮 App Store 只列出 v17.0.6 及 v17.0.7 的部分内容，对 v17.0.4 无明确描述 |
| **soft112（直接 fetch）** | v17.0.5（Mar 27）含 Battle Pass；v17.0.4（Mar 17）含 Sage's Tower + Castle/March Skins |
| **根本原因** | App Store 与 soft112 对同一功能的版本号归属存在一位偏差，且两次 App Store fetch 结果不一致（WebFetch 输出受页面截断影响）|
| **处理方式** | 标注为版本号不确定，功能本身存在；v3_final 中注明"约 2026 年 3–4 月（v17.0.4 或 v17.0.5）"，置信度降为 MEDIUM |

### 问题 2：Campaign Legendary Chapter 版本号来源冲突（D11）

| 项目 | 内容 |
|------|------|
| **v3_draft 写法** | v17.0.6（2026-04-16）：新增 Campaign Legendary chapter |
| **App Store 本轮 fetch** | v17.0.6"Fixed: Some known issues"，无 Campaign Legendary |
| **soft112（直接 fetch）** | v17.0.7（Apr 23）含 Campaign Legendary chapter |
| **处理方式** | 标注为版本号不确定；v3_final 中写"约 2026 年 4 月（v17.0.6 或 v17.0.7）"，置信度降为 MEDIUM |

### 问题 3：KBN v22.3.0 城堡皮肤未经独立确认（E4）

| 项目 | 内容 |
|------|------|
| **v3_draft 写法** | v22.3.0（2024-08-19）：新增城堡皮肤（castle skin） |
| **App Store 本轮 fetch** | v22.3.0 条目显示图形渲染修复，无城堡皮肤 |
| **处理方式** | **删除此声明**；皮肤系统首次确认出现在 v22.4.0（2024-11-06） |

### 问题 4：来源归属错误（B8）

| 项目 | 内容 |
|------|------|
| **v3_draft 写法** | 引用"Wikipedia/Kabam + GamesBeat"证明 KBN 是 2012 年 iPhone 最高收入游戏 |
| **实际情况** | Wikipedia/Kabam 本轮 fetch 未找到此声明；正确来源是 **Wikipedia/KoC**（原文："became the top-grossing iPhone app of 2012"）+ GamesBeat |
| **处理方式** | 修正引用来源：改为 Wikipedia/KoC + GamesBeat；事实内容不变，仍为 HIGH |

---

## 方法论说明

本轮审查发现的问题与 v2 报告相比：

| 对比维度 | v2 报告 | v3_draft |
|---------|---------|---------|
| 核心事实错误（时间差 2 年以上） | 1 处（KBN City Halo System）| 0 处 |
| 版本号冲突（功能存在，版本不确定） | 2 处 | 2 处（Battle Pass、Campaign Legendary） |
| 来源归属错误 | 1 处 | 1 处（Wikipedia/Kabam vs KoC） |
| 应删除声明 | 1 处（v22.3.0）| 1 处（v22.3.0） |
| UNVERIFIED 声明残留 | 0 条 | 0 条 |

v3_draft 在核心历史事实和主要版本内容上显著提升了可靠性。剩余问题集中在 EVD v17.0.x 系列的版本号精确归属（功能本身存在无争议），以及一处来源引用错误。
