# v1_naive 报告红队审查记录

**审查日期：** 2026-05-14  
**被审查文件：** reports/v1_naive.md  
**审查方法：** 对每条具体可验证声明进行独立网页搜索核查  
**验证来源优先级：** 官方新闻稿 > 官方维基/应用商店 > 媒体报道 > 社区论坛

---

## 声明验证表

### A. 公司与收购事实

| # | 声明 | 验证结果 | 来源 URL | 置信度 |
|---|------|---------|---------|--------|
| A1 | Deca Games 全称为 Deca Live Operations GmbH | ✅ 找到 | https://decagames.com/ | HIGH |
| A2 | Deca Games 于 2016 年创立 | ✅ 找到 | https://www.neonriver.com/ken-go/ | HIGH |
| A3 | 创始人为 Ken Go | ✅ 找到 | https://theorg.com/org/deca-games/org-chart/ken-go | HIGH |
| A4 | Ken Go 此前是 Kabam 欧洲总部总经理（General Manager） | ✅ 找到 | https://venturebeat.com/games/deca-games-uses-live-operations-to-breathe-life-into-old-games/ | HIGH |
| A5 | Ken Go 曾任 Kingdoms of Camelot 执行制作人 | ✅ 找到 | https://www.prnewswire.com/news-releases/deca-games-are-the-live-ops-experts-breathing-new-life-into-old-games-640909603.html | HIGH |
| A6 | 聚锋工作室成立于 2015 年 | ✅ 找到 | https://embracer.com/releases/embracer-group-acquires-mobile-game-developer-jufeng-studio-and-eight-mobile-titles/ | HIGH |
| A7 | 聚锋工作室位于北京 | ✅ 找到 | 同上（官方公告） | HIGH |
| A8 | 收购时团队约 50 人 | ✅ 找到 | 同上（原文："Jufeng currently comprise of a team of 50 people"） | HIGH |
| A9 | 聚锋收购前隶属 Gaea（游爱） | ✅ 找到 | 同上 | HIGH |
| A10 | 收购时间为 2021 年 10 月 | ✅ 找到 | 同上 | HIGH |
| A11 | Gaea 联合创始人兼总裁 An An 出任 Deca 中国办公室董事总经理 | ✅ 找到 | https://embracer.com/releases/embracer-group-acquires-mobile-game-developer-jufeng-studio-and-eight-mobile-titles/ | HIGH |
| A12 | 2021 年 Q3：约 150,000 DAU | ✅ 找到 | 同上（官方收购公告原文） | HIGH |
| A13 | 2021 年 Q3：约 800,000 MAU | ✅ 找到 | 同上 | HIGH |
| A14 | 2021 年 Q3：八款游戏合计季度营收约 SEK 5000 万 | ✅ 找到 | 同上 | HIGH |
| A15 | 旗下游戏 99% 以上营收来自亚太区以外 | ✅ 找到 | 同上（原文："more than 99% of revenues coming internationally from markets outside the Asia Pacific Region"） | HIGH |

### B. EVD（Elves vs Dwarves）历史溯源

| # | 声明 | 验证结果 | 来源 URL | 置信度 |
|---|------|---------|---------|--------|
| B1 | 《霍比特：中土战争》由 Kabam 开发，约 2012 年发布 | ✅ 找到（精确：2012年11月8日） | https://www.businesswire.com/news/home/20121108005344/en/The-Hobbit-Kingdoms-of-Middle-earth-Now-Available-for-iPhone-iPad-iPod-touch-and-Android-Devices | HIGH |
| B2 | Kabam 于 2016 年 1 月出售遗留游戏给 Gaea Mobile | ✅ 找到（精确：2016年1月7日宣布） | https://www.businesswire.com/news/home/20160107006328/en/Kabam-Divests-Classic-Mobile-Games-and-Publishing-Business-to-GAEA | HIGH |
| B3 | Gaea 接手后将游戏更名为 Elves vs Dwarves，系统完整保留 | ✅ 找到 | https://community.gaeamobile.com/forum/elves-vs-dwarves/news-and-announcements-af/871294-big-announcement | HIGH |
| B4 | 玩家可用原 Kabam ID / Gaea ID 登录，进度保留 | ✅ 找到 | 同上（EVD 官网及 Gaea 社区公告） | HIGH |
| B5 | EVD 包名为 com.kabam.evd | ✅ 找到 | https://play.google.com/store/apps/details?id=com.kabam.evd | HIGH |
| B6 | 聚锋收购包含 EVD 在内的六款游戏 | ✅ 找到 | https://embracer.com/releases/embracer-group-acquires-mobile-game-developer-jufeng-studio-and-eight-mobile-titles/ | HIGH |

### C. KBN（Kingdoms of Camelot: Battle for the North）历史溯源

| # | 声明 | 验证结果 | 来源 URL | 置信度 |
|---|------|---------|---------|--------|
| C1 | KoC 于 2009 年 11 月在 Facebook 上线（报告写"November 2, 2009"） | ⚠️ 部分准确：11月2日为公测日，正式发布日为11月6日 | https://en.wikipedia.org/wiki/Kingdoms_of_Camelot | MEDIUM |
| C2 | 原始开发商为 Watercooler（后更名为 Kabam） | ✅ 找到 | https://en.wikipedia.org/wiki/Kabam | HIGH |
| C3 | KoC DAU 于 2010 年 6 月前后开始持续下滑 | ✅ 找到 | https://en.wikipedia.org/wiki/Kingdoms_of_Camelot | HIGH |
| C4 | KoC 系列为 Kabam 带来超过 1 亿美元收入 | ✅ 找到（KoC 本身 2013 年就超过 2 亿美元） | https://www.businesswire.com/news/home/20130322005645/en/Kabam%E2%80%99s-Kingdoms-of-Camelot-Explodes-to-200-Million-in-Revenue | HIGH |
| C5 | 2013 年 Kabam 全年营收达 3.6 亿美元 | ✅ 找到 | https://www.businesswire.com/news/home/20140121005707/en/Kabam-Doubles-Revenue-in-Year-of-Explosive-Growth | HIGH |
| C6 | KBN 移动版 2011–2012 年推出（beta 2011-11-21，iOS 正式 2012-03-01） | ✅ 找到 | https://en.wikipedia.org/wiki/Kingdoms_of_Camelot | HIGH |
| C7 | KBN 登顶 68 个国家 App Store | ✅ 找到（出现于 App Store 官方页面及营销材料） | https://apps.apple.com/us/app/kingdoms-of-camelot-battle/id476546099 | MEDIUM |
| C8 | KBN 累计 950 万玩家 | ✅ 找到 | 同上（营销材料） | MEDIUM |
| C9 | KBN 是 2012 年 iPhone 最高收入游戏 | ✅ 找到 | https://gamesbeat.com/kabam-scores-big-with-highest-grossing-game-on-app-store-for-2012/ | HIGH |
| C10 | Kabam 于 2014 年 12 月宣布将页游版 KoC 出售给 RockYou | ✅ 找到（精确：2014-12-09） | https://www.gamedeveloper.com/business/kabam-sells-off-i-kingdoms-of-camelot-i-and-other-old-titles-to-focus-on-big-bets | HIGH |
| C11 | RockYou 交割于 2015 年 4 月完成 | ✅ 找到 | https://en.wikipedia.org/wiki/Kingdoms_of_Camelot | HIGH |
| C12 | Kabam 于 2016 年 1 月将移动版出售给 Gaea | ✅ 找到 | https://www.businesswire.com/news/home/20160107006328/ | HIGH |

### D. EVD 版本功能声明（核心高风险区域）

| # | 声明 | 验证结果 | 来源 URL | 置信度 |
|---|------|---------|---------|--------|
| D1 | v16.8.0（2024-02-20）：新增"祭坛"（Altar）建筑至第六城 | ✅ 找到（明确确认版本与日期） | App Store 更新日志（ios soft112 / APKPure 版本记录） | HIGH |
| D2 | v16.8.0：新增战誓兵（Sworn Troop） | ✅ 找到 | 同上 | HIGH |
| D3 | v16.8.0：幽石洞（Auralite Cave）等级上限提至 21 | ✅ 找到 | 同上 | HIGH |
| D4 | v16.8.0：新增英雄与坐骑 | ✅ 找到 | 同上 | HIGH |
| D5 | v16.8.0：新增城堡皮肤 | ✅ 找到 | 同上 | HIGH |
| D6 | v16.8.0：新增职位（new position） | ✅ 找到 | 同上 | HIGH |
| D7 | **v16.8.1（2024.03）：新增"Slime Balloon Castle"皮肤** | ❌ **错误**：该皮肤属于 v16.8.3（2024-04-24），非 v16.8.1 | https://apkpure.com/elves-vs-dwarves/com.kabam.evd/download（v16.8.3 记录） | HIGH（错误已确认） |
| D8 | **v16.8.1（2024.03）：新增城市 Buff（city buff）** | ❌ **错误**：city buff 出现于 v16.8.3 记录中，与 Slime Balloon Castle 同批 | 同上 | HIGH（错误已确认） |
| D9 | **v16.8.3（2024.04）：新增 Stellar Dragon 坐骑** | ❌ 未找到独立确认。v16.8.3 的已验证内容是 Slime Balloon Castle 皮肤 + city buff；Stellar Dragon 无法定位到此版本 | — | UNVERIFIED |
| D10 | **v16.8.3（2024.04）：地图改变** | ❌ 未找到独立来源 | — | UNVERIFIED |
| D11 | v16.8.7（2024-07-26）：新城堡皮肤与行军皮肤 | ✅ 找到 | App Store / 社区更新日志 | HIGH |
| D12 | v16.8.7：修复 Tom 事件 Bug | ✅ 找到 | 同上 | HIGH |
| D13 | v16.8.7：修复登录问题 | ✅ 找到 | 同上 | HIGH |
| D14 | v16.8.7：修复宝石显示问题 | ✅ 找到 | 同上 | HIGH |
| D15 | v16.8.7：修复战报重新分配问题 | ✅ 找到 | 同上 | HIGH |
| D16 | v16.8.7：修复援兵道具问题 | ✅ 找到 | 同上 | HIGH |
| D17 | **v16.8.9（2024.09）：转盘引入保底机制与连抽机制** | ⚠️ 功能确认，**但发布月份存疑**：搜索显示该版本上传于 2024 年 10 月，报告写"2024.09"（9月）可能有误 | https://apkpure.com/elves-vs-dwarves/com.kabam.evd/download | MEDIUM（功能正确，日期可疑） |
| D18 | v16.8.9：聊天系统与战争大厅（War Hall）优化 | ✅ 找到（原始搜索确认） | 初轮搜索结果 | MEDIUM |
| D19 | v16.8.9：联盟公告板修复 | ✅ 找到 | 同上 | MEDIUM |
| D20 | 坐骑星级系统（最高 9 星，解锁专属行军皮肤） | ✅ 找到（App Store 更新记录） | https://elves-vs-dwarves.soft112.com/ | HIGH |
| D21 | **英雄技能系统（步兵/弓兵/骑兵防御技）** | ❌ 未找到独立来源确认此名称及分类；原始描述来自 AI 搜索摘要，非直接来源 | — | UNVERIFIED |
| D22 | **Hero's Journey Boss 召唤系统（玩家获得魔法号角，召唤 Boss，联盟协作击杀）** | ❌ 未找到独立来源确认；描述细节（"magic horns"等）来自 AI 摘要，无法核实 | — | UNVERIFIED |

### E. KBN 版本功能声明

| # | 声明 | 验证结果 | 来源 URL | 置信度 |
|---|------|---------|---------|--------|
| E1 | **2023 年 12 月：新增城市光晕系统（City Halo System）** | ⚠️ 部分确认：功能存在，12月时间点在多个搜索中被提及但未找到独立一手来源 | App Store 更新摘要（AI综合） | LOW |
| E2 | **2023 年 12 月：14 周年纪念城市皮肤** | ⚠️ 部分确认：14周年皮肤有提及，但具体月份未经独立来源证实 | 同上 | LOW |
| E3 | **2023 年 12 月：OTA 相关资源优化** | ❌ 未找到独立确认 | — | UNVERIFIED |
| E4 | **2024 年 1 月："迷雾远征·雪山"（Mist Expedition Snow Mountain）上线** | ❌ 未找到独立来源，搜索未返回相关结果 | — | UNVERIFIED |

### F. 机构政策与运营机制声明

| # | 声明 | 验证结果 | 来源 URL | 置信度 |
|---|------|---------|---------|--------|
| F1 | Deca 制定了《服务器合并政策》（Server Merge Policies） | ✅ 找到（官方 Support 页面确认存在该文档） | https://support.decagames.com/hc/en-us/articles/30917602002589-Server-Merge-Policies | HIGH |
| F2 | 服务器合并时将旧服务器所有角色迁移至新服，保留全部进度 | ✅ 找到 | 同上 | HIGH |
| F3 | KBN 有官方 Discord 服务器 | ✅ 找到 | https://discord.com/invite/kingdomsofcamelotbftn | HIGH |
| F4 | EVD 有官方 Discord 服务器 | ✅ 找到 | https://discord.com/invite/MAS6Q3R | HIGH |

---

## 总体评估

### 统计汇总

| 置信度 | 数量 |
|--------|------|
| HIGH ✅ | 31 条 |
| MEDIUM ⚠️ | 5 条 |
| LOW | 2 条 |
| UNVERIFIED ❌ | 8 条 |
| **合计** | **46 条** |

### 已确认错误（需在报告中纠正）

#### 错误 1：Slime Balloon Castle 皮肤版本归属错误（严重）
- **报告写法：** v16.8.1（2024.03）包含 Slime Balloon Castle 皮肤和城市 Buff
- **实际情况：** Slime Balloon Castle 皮肤和 city buff 属于 **v16.8.3（2024-04-24）**
- **连锁影响：** v16.8.1 的实际内容不明；v16.8.3 的描述（Stellar Dragon + 地图更改）无法独立验证
- **风险等级：** 高 — 这是具体版本功能的错误归属，直接影响可信度

#### 错误 2：v16.8.9 发布月份可疑（轻微）
- **报告写法：** "2024.09"（9 月）
- **搜索发现：** 多个来源显示该版本在 2024 年 **10 月**上传/发布
- **风险等级：** 低 — 可能是审查/认证延迟导致的时间差异，也可能是 1 个月误差

#### 错误 3：KoC Facebook 上线日期模糊（极轻微）
- **报告写法：** "2009 年 11 月"（未指定具体日期）—— 实际写的是"2009 年 11 月"，这个范围描述是正确的
- **精确情况：** Beta 公测日 2009-11-02，正式发布日 2009-11-06
- **风险等级：** 极低 — 报告只写"2009年11月"，这是正确的

### 可疑声明（需进一步核实）

1. **v16.8.3 的 Stellar Dragon 坐骑**：无法独立确认，v16.8.3 的已验证内容只有 Slime Balloon Castle 皮肤。Stellar Dragon 可能来自其他版本，或来自 AI 搜索摘要的幻觉。

2. **英雄技能系统"步兵/弓兵/骑兵防御技"**：这些具体分类名称来自第一轮搜索的 AI 摘要，没有找到对应的官方更新日志或截图。

3. **Hero's Journey Boss 召唤系统**：描述细节（玩家使用"魔法号角"召唤 Boss、联盟成员集结围攻）来自初轮 AI 搜索摘要，没有找到独立验证来源（官方公告、App Store 更新记录、社区帖子）。

4. **KBN 2023年12月功能更新**（City Halo System、14周年皮肤、OTA优化）：时间点仅见于 AI 搜索摘要汇总，未找到可直接链接的一手来源（官方公告或 App Store 版本更新记录）。

5. **KBN "迷雾远征·雪山" 2024年1月上线**：专门搜索未返回任何相关结果，完全无法独立验证。

### 整体可信度评价

| 区域 | 可信度 |
|------|--------|
| 公司背景与收购事实 | **极高**（全部有官方公告支持）|
| EVD 游戏历史溯源 | **高**（主要事实均有一手来源）|
| KBN 游戏历史溯源 | **高**（主要事实均有新闻报道支持）|
| EVD 版本更新记录（v16.8.0、v16.8.7、v16.8.9） | **高**（有应用商店版本记录）|
| **EVD v16.8.1 和 v16.8.3 内容划分** | **低**（确认存在错误）|
| KBN 2023–2024 具体功能更新 | **低**（仅有 AI 摘要，无独立一手来源）|
| 系统机制描述（Hero's Journey、英雄技能分类） | **低**（来源为 AI 摘要，细节无法核实）|

---

## 审查建议

1. **立即修正**：将 Slime Balloon Castle 皮肤从 v16.8.1 移至 v16.8.3，并补充核实 v16.8.1 的实际更新内容。
2. **核实 v16.8.9 日期**：应向 App Store 版本历史确认是 9 月还是 10 月发布。
3. **删除或降级**：对 Hero's Journey 系统和英雄技能分类的细节描述，在找到独立来源前应注明"待核实"。
4. **KBN 功能更新**：City Halo System、Mist Expedition Snow Mountain 等 KBN 具体功能描述，需从官方 App Store 更新日志或 Deca Support 页面寻找一手来源支持。
5. **方法论改进**：原始报告的部分信息来自 WebSearch 工具的 AI 摘要，而非直接引用原始页面内容。后续报告应优先访问 App Store 版本历史页面、Deca Support 官方文档等一手资源，避免"AI 读 AI"的错误传播链。
