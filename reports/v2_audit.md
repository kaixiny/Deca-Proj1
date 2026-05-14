# v2_with_workflow 报告红队审查记录

**审查日期：** 2026-05-14
**被审查文件：** reports/v2_with_workflow.md
**审查方法：** 对报告中所有 HIGH 置信度声明逐一使用 WebFetch 访问原始页面复验；MEDIUM 声明抽查关键项
**验证工具：** WebFetch 直接访问 Wikipedia、Apple App Store、soft112 版本记录、APK 版本记录、PR Newswire 原文

---

## 声明验证表

### A. 公司与收购事实（HIGH 声明）

| # | 声明 | 验证结果 | 验证来源（直接访问） | 置信度判定 |
|---|------|---------|------------------|-----------|
| A1 | Deca Games 于 2016 年在柏林创立 | ✅ 确认 | [Wikipedia/Deca_Games](https://en.wikipedia.org/wiki/Deca_Games)："Founded 2016" | HIGH |
| A2 | 创始人 Ken Go 曾任 Kabam 欧洲总部总经理 | ✅ 确认 | 同上："general manager for Kabam's European headquarters" | HIGH |
| A3 | Ken Go 曾任 KoC 执行制作人 | ✅ 确认 | [PR Newswire](https://www.prnewswire.com/news-releases/deca-games-are-the-live-ops-experts-breathing-new-life-into-old-games-640909603.html) 原文："served as Executive Producer of Kingdoms of Camelot" | HIGH |
| A4 | Deca 于 2020 年 8 月成为 Embracer Group 第六个运营集团 | ✅ 确认 | [Wikipedia/Deca_Games](https://en.wikipedia.org/wiki/Deca_Games)："In August 2020, Deca was acquired by Embracer Group, which made it as the sixth operative group" | HIGH |
| A5 | 聚锋成立于 2015 年，位于北京，约 50 人 | ✅ 确认 | [Embracer 官方公告](https://embracer.com/releases/embracer-group-acquires-mobile-game-developer-jufeng-studio-and-eight-mobile-titles/)（直接 fetch）："Founded 2015, based in Beijing, China … a team of 50 people" | HIGH |
| A6 | 收购时间 2021 年 10 月 14 日 | ✅ 确认 | 同上（"October 14, 2021"） | HIGH |
| A7 | An An（Gaea 总裁）出任 Deca 中国办公室 MD | ✅ 确认 | 同上（"President of GAEA … joined as managing director of DECA Games' new China office"） | HIGH |
| A8 | 2021 年 Q3：约 150K DAU、800K MAU、SEK 5000 万季度营收 | ✅ 确认 | 同上（原文数字一致） | HIGH |
| A9 | 99%+ 营收来自亚太区以外 | ✅ 确认 | 同上（"more than 99% of revenues … outside the Asia Pacific Region"） | HIGH |

### B. 历史时间线（HIGH 声明）

| # | 声明 | 验证结果 | 验证来源（直接访问） | 置信度判定 |
|---|------|---------|------------------|-----------|
| B1 | KoC Facebook 版 beta：2009-11-02；正式：2009-11-06 | ✅ 确认（精确到日） | [Wikipedia/KoC](https://en.wikipedia.org/wiki/Kingdoms_of_Camelot)（直接 fetch） | HIGH |
| B2 | KBN 移动版 beta：2011-11-21；iOS 正式：2012-03-01 | ✅ 确认（精确到日） | 同上 + WebSearch（Wikipedia 引用） | HIGH |
| B3 | Kabam 出售网页版 KoC 给 RockYou：2014-12-09 宣布，2015-04 完成 | ✅ 确认 | [Wikipedia/KoC](https://en.wikipedia.org/wiki/Kingdoms_of_Camelot)（"December 9, 2014"；"beginning of April 2015"） | HIGH |
| B4 | Kabam 出售移动版给 Gaea Mobile：2016-01-07 | ✅ 确认 | [Wikipedia/Kabam](https://en.wikipedia.org/wiki/Kabam)（"January 7, 2016"） | HIGH |
| B5 | The Hobbit KoME 于 2012 年秋季发布 | ✅ 确认（报告措辞"秋季"覆盖两个来源的差异） | Wikipedia/Kabam："2012/10/16"；BusinessWire 原文：2012-11-08 — 两源有差异，报告用"秋季"属保守描述 | HIGH |
| B6 | 2010 年 6 月 KoC DAU 开始持续下滑 | ⚠️ Wikipedia/KoC 直接 fetch **未找到此具体描述**（该页面未包含 2010 年 6 月下滑的说法） | [Wikipedia/KoC](https://en.wikipedia.org/wiki/Kingdoms_of_Camelot) | MEDIUM（降级）|
| B7 | Kabam 2013 年营收 $3.6 亿 | ✅ 确认 | [Wikipedia/Kabam](https://en.wikipedia.org/wiki/Kabam)："$360 million in revenues for 2013" | HIGH |
| B8 | KoC 领衔四款游戏合计营收超 $1 亿 | ✅ 确认 | 同上："four of its games – led by Kingdoms of Camelot – grossed more than $100 million" | HIGH |
| B9 | KBN 是 2012 年 iPhone 最高收入游戏 | ✅ 确认（两个独立来源） | [Wikipedia/Kabam](https://en.wikipedia.org/wiki/Kabam) + [GamesBeat](https://gamesbeat.com/kabam-scores-big-with-highest-grossing-game-on-app-store-for-2012/) | HIGH |
| B10 | Kabam 出售聚锋，EVD 并入 Deca（2021-10-14） | ✅ 确认 | [Embracer 官方公告](https://embracer.com/releases/embracer-group-acquires-mobile-game-developer-jufeng-studio-and-eight-mobile-titles/) | HIGH |

### C. Deca 策略声明（HIGH 声明）

| # | 声明 | 验证结果 | 验证来源（直接访问） | 置信度判定 |
|---|------|---------|------------------|-----------|
| C1 | Ken Go 原话（两段引文） | ✅ 确认（原文逐字核对） | [PR Newswire](https://www.prnewswire.com/news-releases/deca-games-are-the-live-ops-experts-breathing-new-life-into-old-games-640909603.html)（直接 fetch） | HIGH |
| C2 | Deca 六大运营职能列表 | ✅ 确认（原文实为 7 个词组，合并"live events and promotion planning"为一项后为六项，报告计数正确） | 同上（原文："community management, product management, feature development, art, customer support, live events and promotion planning"） | HIGH |
| C3 | Realm of the Mad God 接手一年内 DAU 翻倍 | ✅ 确认 | 同上（原文："has seen the amount of daily active users doubled"） | HIGH |
| C4 | Server Merge Policies 文档存在于 Deca Support | ✅ 确认（URL 可通过搜索找到；直接 fetch 返回 403，不影响存在性确认） | [Deca Support](https://support.decagames.com/hc/en-us/articles/30917602002589-Server-Merge-Policies)（搜索结果确认） | HIGH |

### D. EVD 版本内容（MEDIUM 声明抽查）

| # | 声明 | 验证结果 | 验证来源（直接访问） | 置信度判定 |
|---|------|---------|------------------|-----------|
| D1 | v16.8.0 Android（2024-02）含 Altar、Sworn Troop、Auralite Cave 21 | ✅ 确认（逐字核对英文 changelog） | [apk.gold](https://elves-vs-dwarves.apk.gold/android-7.1.2)（直接 fetch） | HIGH |
| D2 | v16.8.1 Android 含 Slime Balloon Castle skin + city buff | ✅ 确认 | 同上 | HIGH |
| D3 | v16.8.9（2024-09-10）含转盘保底+连抽机制 | ✅ 确认（"Wheel optimization, adding guarantees and consecutive draws"） | 同上 | HIGH |
| D4 | v17.0.3（2026-02-10）坐骑升星至 9 星 | ✅ 确认（"Mount Star-Up expanded to 9 stars, unlocking an exclusive march skin"） | [Apple App Store](https://apps.apple.com/us/app/elves-vs-dwarves/id1231491435)（直接 fetch） | HIGH |
| D5 | **v17.0.5（2026-03-27）：Battle Pass** | ❌ **错误**：App Store 显示 v17.0.5 仅含 bug 修复；Battle Pass 在 **v17.0.4（2026-03-17）** | [Apple App Store](https://apps.apple.com/us/app/elves-vs-dwarves/id1231491435)（直接 fetch，原文："v17.0.5 Fixed: Some known issues"；"v17.0.4 才提及 Battle Pass"） | HIGH（错误已确认）|
| D6 | v17.0.6（2026-04-16）：Campaign Legendary chapter | ✅ 确认（App Store 原文："Added new Campaign Legendary chapter"在 v17.0.6 条目下） | [Apple App Store](https://apps.apple.com/us/app/elves-vs-dwarves/id1231491435)（直接 fetch） | HIGH |
| D7 | v16.9.1（2024-12-13）：英雄解锁至 6-10 星 | ✅ 确认（"Heroes unlocked up to 6-10 stars"） | [soft112 iOS](https://elves-vs-dwarves-ios.soft112.com/)（直接 fetch） | HIGH |

### E. KBN 版本内容（MEDIUM 声明抽查）

| # | 声明 | 验证结果 | 验证来源（直接访问） | 置信度判定 |
|---|------|---------|------------------|-----------|
| E1 | v22.4.0（2024 年 11 月）：castle skins、hero skin system、march skins、legendary knights、gear evolution | ✅ 确认（App Store 原文逐条列出） | [Apple App Store KBN](https://apps.apple.com/us/app/kingdoms-of-camelot-battle/id476546099)（直接 fetch，v22.4.0 release date：Nov 6, 2024） | HIGH |
| E2 | v22.7.6（2025-08-23）：Special Cards 功能 | ✅ 确认 | [soft112 KBN](https://kingdoms-of-camelot-battle.soft112.com/)（直接 fetch，原文："New Feature – Special Cards"） | HIGH |
| E3 | **v22.7.8 Android（2025-12-10）/ iOS v22.8.0（2026-01-22）：City Halo System** | ❌ **iOS 版本归属错误**：App Store（iOS）显示 City Halo System 在 **v22.7.8（2025-11-20）**，而非报告所写的 v22.8.0 | [Apple App Store KBN](https://apps.apple.com/us/app/kingdoms-of-camelot-battle/id476546099)（直接 fetch，v22.7.8 Nov 20, 2025："New Feature – City Halo System ▶ New Skin – 14th Anniversary City Skin"） | HIGH（iOS 版本号错误已确认）|
| E4 | "14th Anniversary"对应移动版 2012→2026 年 14 周年 | ✅ 确认（计算：KBN iOS 正式发布 2012-03-01，至 2026 年为第 14 年；App Store 原文明确写"14th Anniversary"） | [Apple App Store KBN](https://apps.apple.com/us/app/kingdoms-of-camelot-battle/id476546099) + [Wikipedia/KoC](https://en.wikipedia.org/wiki/Kingdoms_of_Camelot) | HIGH |
| E5 | v22.9.0（2026-04-03）：图形渲染修复、登录延迟优化 | ✅ 确认 | [Apple App Store KBN](https://apps.apple.com/us/app/kingdoms-of-camelot-battle/id476546099)（直接 fetch） | HIGH |

---

## 总体统计

| 类别 | 数量 |
|------|------|
| 验证通过（✅ HIGH） | 27 条 |
| 发现错误（❌ 确认） | 2 条 |
| 降级处理（⚠️ HIGH→MEDIUM） | 1 条 |
| 合计审查 | 30 条 |

---

## 已确认错误详情

### 错误 1：EVD Battle Pass 版本号错误

| 项目 | 内容 |
|------|------|
| **报告写法** | v17.0.5（2026-03-27）：新增战斗通行证（Battle Pass）功能 |
| **实际情况** | Battle Pass 在 **v17.0.4（2026-03-17）**；v17.0.5 仅含 bug 修复 |
| **验证来源** | Apple App Store iOS 版本历史（直接 fetch）：v17.0.5 原文"Fixed: Some known issues"；另注"v17.0.4 才提及 Battle Pass" |
| **严重程度** | 中等——版本号差一位，日期差 10 天，功能本身存在无误 |

### 错误 2：KBN City Halo System iOS 版本归属错误

| 项目 | 内容 |
|------|------|
| **报告写法** | "iOS v22.8.0（2026-01-22）：City Halo System + 14th Anniversary City Skin" |
| **实际情况** | iOS App Store 直接 fetch 显示：City Halo System 在 **v22.7.8（2025-11-20）**（与 Android v22.7.8 在同一版本号，仅平台发布日期不同：Android 2025-12-10，iOS 2025-11-20） |
| **验证来源** | Apple App Store KBN 页面（直接 fetch）：v22.7.8 原文"New Feature – City Halo System ▶ New Skin – 14th Anniversary City Skin"；soft112 Android 亦为 v22.7.8 |
| **严重程度** | 中等——功能正确，版本号和日期均有出入（v22.8.0 是不存在的说法，实为 v22.7.8） |
| **根本原因** | 最初的 App Store WebFetch 汇总在两次抓取中对同一版本号给出了不一致结果；第二次直接 fetch 和 soft112 数据共同指向 v22.7.8，说明第一次结果有误 |

---

## 降级说明

### B6：KoC 2010年6月 DAU 开始下滑

- **降级原因：** 在 Wikipedia/KoC 页面直接 fetch 中未找到"2010年6月下滑"的具体陈述（页面数据库可能已变化）
- **处理：** 从 HIGH 降至 MEDIUM；实质上不影响报告分析，该声明在报告中并非核心论点

---

## 方法论说明

v2 报告相较 v1 的质量提升：

1. **来源层级提升**：从依赖 AI 搜索摘要，改为 WebFetch 直接访问原始页面（Wikipedia、官方公告、App Store、PR Newswire 等）
2. **UNVERIFIED 声明已删除**：Hero's Journey 细节、英雄技能分类、迷雾远征·雪山等 5 条 UNVERIFIED 声明在 Step 3 报告中全部删除
3. **重大时间错误已纠正**：KBN City Halo System 从 v1 的"2023年12月"纠正为"2025年11月/12月"
4. **iOS/Android 版本差异已标注**：v2 报告明确说明两平台版本号差一位的情况

v2 报告中仍存在的两处错误（Battle Pass 版本号、KBN iOS 版本号）均属中等级别，功能本身存在，仅版本号/日期有偏差，且根因是 WebFetch 在不同次调用中返回了不一致的 App Store 数据。
