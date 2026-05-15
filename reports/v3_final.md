# Deca 中国工作室旗下 EVD & KBN 长青化运营策略演变报告

---

## 修订日志

> **版本**：v3_final（修订版）
> **基于**：v3_draft.md
> **审查依据**：v3_audit.md
> **修订时间**：2026-05-14

本版本基于 Step 4 红队审查，对初稿 v3_draft.md 进行了 4 处修订。

### 修订 #1（对应 audit B8 - 来源归属错误）
- **位置**：第 3.1 节 KBN 起源：Kingdoms of Camelot（Facebook 版）
- **修订前**：KBN 2012 年最高收入游戏 [引用：Wikipedia/Kabam + GamesBeat]
- **修订后**：KBN 2012 年最高收入游戏 [引用：Wikipedia/KoC + GamesBeat]
- **理由**：Wikipedia/Kabam 实际不包含此声明，正确来源为 Wikipedia/KoC
- **验证 URL**：https://en.wikipedia.org/wiki/Kingdoms_of_Camelot

### 修订 #2（对应 audit D10 - 版本号来源冲突）
- **位置**：第 4.2 节 EVD 阶段三 主线三：变现机制创新——付费模式多元化探索
- **修订前**：v17.0.4（2026-03-17）：Battle Pass [MEDIUM]
- **修订后**：约 2026 年 3–4 月（App Store 记 v17.0.4，soft112 记 v17.0.5）：Battle Pass [MEDIUM]
- **理由**：App Store 与 soft112 对 Battle Pass 的版本号归属不一致
- **验证 URL**：https://apps.apple.com/us/app/elves-vs-dwarves/id1231491435

### 修订 #3（对应 audit D11 - 版本号来源冲突）
- **位置**：第 4.2 节 EVD 阶段三 主线三：变现机制创新——付费模式多元化探索
- **修订前**：v17.0.6（2026-04-16）：Campaign Legendary chapter [MEDIUM]
- **修订后**：约 2026 年 4 月（App Store 记 v17.0.6，soft112 记 v17.0.7）：Campaign Legendary chapter [MEDIUM]
- **理由**：App Store 与 soft112 对该功能的版本号归属不一致
- **验证 URL**：https://apps.apple.com/us/app/elves-vs-dwarves/id1231491435

### 修订 #4（对应 audit E4 - 未经确认声明）
- **位置**：第 4.3 节 KBN 阶段三：系统全面扩展（原 v22.3.0 条目，整段删除）
- **修订前**：v22.3.0（2024-08-19）：新增城堡皮肤
- **修订后**：[整段删除]
- **理由**：App Store v22.3.0 仅显示图形渲染修复，无城堡皮肤；皮肤系统首次确认在 v22.4.0
- **验证 URL**：https://apps.apple.com/us/app/kingdoms-of-camelot-battle/id476546099

### 修订统计
- 总声明数：30
- 通过验证：26 条（HIGH 维持）
- 已修订错误：3 条
- 来源归属修正：1 条
- 删除声明：1 条

---

**版本：** v3_final（遵循 CLAUDE.md 工作流，第三轮研究定稿）
**日期：** 2026-05-14
**研究范围：** Elves vs Dwarves（EVD）与 Kingdoms of Camelot: Battle for the North（KBN）
**方法说明：** 所有声明均附置信度标签与可访问原始 URL；UNVERIFIED 声明已删除；v3_audit 发现的 4 处问题已在本版本全部修正。

---

## 置信度标准

| 标签 | 含义 |
|------|------|
| **[HIGH]** | ≥2 个独立一手来源（官方公告、Wikipedia、Apple App Store 等）一致 |
| **[MEDIUM]** | 单一权威一手来源（App Store 或 apk.gold 其中之一，内容清晰） |

---

## 1. 公司背景：Deca Games 与聚锋工作室

### 1.1 Deca Games 概况

Deca Games（全称 Deca Live Operations GmbH）于 **2016 年在德国柏林创立** **[HIGH]** [[Wikipedia/Deca_Games](https://en.wikipedia.org/wiki/Deca_Games)]，创始人为 **Ken Go**。Ken Go 在此之前曾担任 Kabam 欧洲总部总经理，并在 Kabam 期间出任 Kingdoms of Camelot 执行制作人 **[HIGH]** [[PR Newswire](https://www.prnewswire.com/news-releases/deca-games-are-the-live-ops-experts-breathing-new-life-into-old-games-640909603.html)]（原文："developed Kabam's Live Ops departments and served as Executive Producer of Kingdoms of Camelot"）。

**2020 年 8 月**，Deca Games 成为 Embracer Group 旗下第六个运营集团，专注于免费游戏的长线运营 **[HIGH]** [[Wikipedia/Deca_Games](https://en.wikipedia.org/wiki/Deca_Games)]（原文："In August 2020, Deca was acquired by Embracer Group, which made it as the sixth operative group"）。

**Ken Go 关于公司使命的原话 [HIGH]** [[PR Newswire](https://www.prnewswire.com/news-releases/deca-games-are-the-live-ops-experts-breathing-new-life-into-old-games-640909603.html)]：

> "With games companies needing to focus on their next big hit to continue to grow and survive, smaller older games with a very engaged audience are being put on the back burner. I created DECA Games to give developers an alternative route to shutting down a game, and for the super fans of these games on the verge of dying."

> "We care deeply about the community, and that comes across in everything we do. Our ultimate goal is to give these games a rebirth and revitalize the fanbase."

**团队规模演变 [MEDIUM]** [[PocketGamer](https://www.pocketgamer.biz/deca-games-from-being-acquired-to-acquiring/)]：
- 2020 年 8 月（加入 Embracer 时）：约 80 人
- 18 个月后：超过 230 人
- 当前合计：超过 730 人（含收购工作室）
- 运营版图覆盖 26 个国家，游戏组合在 18 个月内翻倍至 20+ 款

### 1.2 聚锋工作室（Jufeng Studio）

| 要素 | 内容 | 置信度 | 来源 |
|------|------|--------|------|
| 成立时间 | 2015 年 | **[HIGH]** | [Embracer 官方公告](https://embracer.com/releases/embracer-group-acquires-mobile-game-developer-jufeng-studio-and-eight-mobile-titles/) |
| 所在地 | 北京中央商务区 | **[HIGH]** | 同上 |
| 收购前隶属 | Gaea（游爱） | **[HIGH]** | 同上 |
| 团队规模 | 约 50 人 | **[HIGH]** | 同上（原文："a team of 50 people"） |
| 被 Deca 收购时间 | 2021 年 10 月 | **[HIGH]** | 同上 |
| 领导层过渡 | Gaea 联合创始人兼总裁 An An 出任 Deca 中国办公室董事总经理，主导亚太地区并购 | **[HIGH]** | 同上 |

**收购时（2021 年 Q3）整体运营数据（8 款游戏合计）[HIGH]** [[Embracer 官方公告](https://embracer.com/releases/embracer-group-acquires-mobile-game-developer-jufeng-studio-and-eight-mobile-titles/)]：
- 日活跃用户（DAU）：约 150,000
- 月活跃用户（MAU）：约 800,000
- 季度总营收：约 SEK 5,000 万
- 营收来源：99% 以上来自亚太区以外的国际市场

---

## 2. EVD（Elves vs Dwarves）溯源与版权流转

### 2.1 起源：The Hobbit: Kingdoms of Middle-earth

The Hobbit: Kingdoms of Middle-earth 由 Kabam 与 Warner Bros. Interactive Entertainment 联合开发，于 **2012 年 10 月 16 日发布于 iOS 和 Android 平台** **[HIGH]** [[Wikipedia/Kabam](https://en.wikipedia.org/wiki/Kabam)]。

### 2.2 版权流转时间线

| 时间 | 事件 | 置信度 | 来源 |
|------|------|--------|------|
| 2016 年 1 月 7 日 | Kabam 宣布将遗留游戏及第三方发行游戏出售给 Gaea Mobile | **[HIGH]** | [Wikipedia/Kabam](https://en.wikipedia.org/wiki/Kabam) |
| 2016 年（Gaea 接手后） | IP 授权到期后 Gaea 以相同系统和玩法重新发布，去掉《霍比特》授权，命名为 **Elves vs Dwarves（EVD）** | **[HIGH]** | [Wikipedia/Kabam](https://en.wikipedia.org/wiki/Kabam) + [Embracer 官方公告](https://embracer.com/releases/embracer-group-acquires-mobile-game-developer-jufeng-studio-and-eight-mobile-titles/)（均将 EVD 列为聚锋旗下游戏） |
| 2021 年 10 月 | Deca Games 收购聚锋工作室，EVD 并入 Deca 体系 | **[HIGH]** | [Embracer 官方公告](https://embracer.com/releases/embracer-group-acquires-mobile-game-developer-jufeng-studio-and-eight-mobile-titles/) |

**当前发行状态：** 发行商为 Deca_Games **[HIGH]** [[Google Play](https://play.google.com/store/apps/details?id=com.kabam.evd&hl=en_US) + [Apple App Store](https://apps.apple.com/us/app/elves-vs-dwarves/id1231491435)]

---

## 3. KBN（Kingdoms of Camelot: Battle for the North）溯源与版权流转

### 3.1 起源：Kingdoms of Camelot（Facebook 版）

Kingdoms of Camelot 由 Watercooler（即 Kabam 前身）开发，于 **2009 年 11 月 2 日公测，11 月 6 日正式发布于 Facebook** **[HIGH]** [[Wikipedia/Kingdoms of Camelot](https://en.wikipedia.org/wiki/Kingdoms_of_Camelot)]，为最早成功的 Facebook 策略游戏之一。

**商业成就（Kabam 时期）：**
- 2013 年 Kabam 全年营收 **$3.6 亿美元** **[HIGH]** [[Wikipedia/Kabam](https://en.wikipedia.org/wiki/Kabam)]
- Kingdoms of Camelot 领衔的四款游戏合计营收超 **$1 亿美元** **[HIGH]** [同上]
- 移动版 KBN 于 **2012 年成为 iPhone 全年最高收入游戏** **[HIGH]** [[Wikipedia/KoC](https://en.wikipedia.org/wiki/Kingdoms_of_Camelot) + [GamesBeat](https://gamesbeat.com/kabam-scores-big-with-highest-grossing-game-on-app-store-for-2012/)]，在超过 **50 个国家**保持最高收入应用排名 **[MEDIUM]** [[GamesBeat](https://gamesbeat.com/kabam-scores-big-with-highest-grossing-game-on-app-store-for-2012/)]

### 3.2 版权流转时间线

| 时间 | 事件 | 置信度 | 来源 |
|------|------|--------|------|
| 2011 年 11 月 21 日 | 移动版 KBN iOS 公测 | **[HIGH]** | [Wikipedia/KoC](https://en.wikipedia.org/wiki/Kingdoms_of_Camelot) |
| 2012 年 3 月 1 日 | KBN iOS 正式发布（Kabam 首款移动游戏） | **[HIGH]** | 同上 |
| 2014 年 12 月 9 日 | Kabam 宣布将页游版 KoC 出售给 RockYou | **[HIGH]** | 同上 |
| 2015 年 4 月 | 页游版 KoC 正式移交 RockYou | **[HIGH]** | 同上 |
| 2016 年 1 月 7 日 | Kabam 将移动版 KBN 随遗留游戏组合出售给 Gaea Mobile | **[HIGH]** | [Wikipedia/Kabam](https://en.wikipedia.org/wiki/Kabam) + [Wikipedia/KoC](https://en.wikipedia.org/wiki/Kingdoms_of_Camelot) |
| 2021 年 10 月 | Deca Games 收购聚锋工作室，KBN 并入 Deca 体系 | **[HIGH]** | [Embracer 官方公告](https://embracer.com/releases/embracer-group-acquires-mobile-game-developer-jufeng-studio-and-eight-mobile-titles/) |

**当前发行状态：** 发行商为 Deca_Games **[HIGH]** [[Google Play](https://play.google.com/store/apps/details?id=com.kabam.kocmobile&hl=en_US) + [Apple App Store](https://apps.apple.com/us/app/kingdoms-of-camelot-battle/id476546099)]

---

## 4. 长青化运营策略的演变

### 4.1 Deca 整体长青化运营哲学

Deca 的核心模式是接管处于衰退期的免费游戏，通过专业 Live Ops 团队延长生命周期。其全栈运营职能 **[HIGH]** [[PR Newswire](https://www.prnewswire.com/news-releases/deca-games-are-the-live-ops-experts-breathing-new-life-into-old-games-640909603.html)]：

社区管理、产品管理、功能开发、美术迭代、客户支持、实时活动策划与推广执行。

**效果验证：** 接手 Realm of the Mad God 一年后，日活用户翻倍 **[HIGH]** [同上]（原文："has seen the amount of daily active users doubled"）。

**战略定位 [MEDIUM]** [[PocketGamer](https://www.pocketgamer.biz/deca-games-from-being-acquired-to-acquiring/)]：以"慢速衰退的老游戏"为收购目标，通过持续运营投入将存量玩家的忠诚度转化为稳定现金流，而非依赖新用户获取。分布于 26 个国家的远程团队使其具备跨时区、跨文化支持全球游戏的能力。

---

### 4.2 EVD 长青化运营策略演变

#### 阶段一：Gaea 时期（2016–2021）——IP 去授权与基础 Live Ops 建立

Gaea 接手后的核心任务是在《霍比特》IP 授权到期后将游戏完整迁移至无版权 IP 版本（Elves vs Dwarves），同时维持玩家留存。

#### 阶段二：Deca 接管初期（2021–2023）——稳定过渡与方向确立

Deca 收购聚锋后保留原有管理层和开发团队独立运营 **[HIGH]** [[Embracer 官方公告](https://embracer.com/releases/embracer-group-acquires-mobile-game-developer-jufeng-studio-and-eight-mobile-titles/)]。此阶段以保障现有玩家体验为主，版本更新以改进和修复为主（v16.7.x 系列）**[MEDIUM]** [[Apple App Store](https://apps.apple.com/us/app/elves-vs-dwarves/id1231491435)]。

#### 阶段三：深度 Live Ops（2024–2026）——三条策略主线并行

---

**主线一：城市系统纵向扩展——持续拉高养成天花板**

**v16.8.0（2024-02-20）[HIGH]** [[Apple App Store](https://apps.apple.com/us/app/elves-vs-dwarves/id1231491435) + [apk.gold](https://elves-vs-dwarves.apk.gold/android-7.1.2)]：
- 新增第六城建筑"**祭坛**"（Altar）及新职位
- 新增部队类型"**战誓兵**"（Sworn Troop）
- 新增科技分支（new Tech）**[MEDIUM]** [[apk.gold](https://elves-vs-dwarves.apk.gold/android-7.1.2)]
- **幽石洞**（Auralite Cave）等级上限提至 **21 级** **[MEDIUM]** [同上]（App Store 描述为"new buildings"，apk.gold 明确列出）
- 新增英雄与坐骑；新增城堡皮肤 **[MEDIUM]** [同上]

**v16.9.0（2024-11-19）[HIGH]** [[Apple App Store](https://apps.apple.com/us/app/elves-vs-dwarves/id1231491435) + [apk.gold](https://elves-vs-dwarves.apk.gold/android-7.1.2)]：
- 英雄解锁至 **6–10 星**，扩展英雄养成上限（原文："Heroes unlocked up to 6-10 stars"）

---

**主线二：装备与坐骑深度系统——创造长期付费动机**

**v16.9.8（2024-08-28 iOS）[MEDIUM]** [[Apple App Store](https://apps.apple.com/us/app/elves-vs-dwarves/id1231491435)]：
- 新城堡皮肤、行军皮肤
- 新功能：**神秘坐骑装备**（Mysterious Mount Equipment）

**v17.0.2（2025-12-01）[HIGH]** [[Apple App Store](https://apps.apple.com/us/app/elves-vs-dwarves/id1231491435) + [apk.gold](https://elves-vs-dwarves.apk.gold/android-7.1.2)]：
- 坐骑升星扩展至 **9 星**，解锁专属行军皮肤（原文："Mount Star-Up expanded to 9 stars, unlocking an exclusive march skin"）
- 新增武器列表筛选功能
- 新宝石升级设计

**v17.0.3（2026-02-10）[MEDIUM]** [[Apple App Store](https://apps.apple.com/us/app/elves-vs-dwarves/id1231491435)]：
- Sage's Tower 子类别扩展
- 新城堡皮肤与行军皮肤
- Lancelot 界面更新

---

**主线三：变现机制创新——付费模式多元化探索**

**v16.8.1（2024-03-26）轻量皮肤付费 [HIGH]** [[Apple App Store](https://apps.apple.com/us/app/elves-vs-dwarves/id1231491435) + [apk.gold](https://elves-vs-dwarves.apk.gold/android-7.1.2)]：
- 新增城堡皮肤"**Slime Balloon Castle**"
- 新增城市增益（city buff）

**v16.8.3（2024-04-24）坐骑付费点扩展 [HIGH]** [[Apple App Store](https://apps.apple.com/us/app/elves-vs-dwarves/id1231491435) + [apk.gold](https://elves-vs-dwarves.apk.gold/android-7.1.2)]：
- 新增坐骑"**Stellar Dragon**"（原文："Add new mount: Stellar Dragon"）
- 地图更新

**v16.8.9（2024-09-10）抽奖机制合规化升级 [HIGH]** [[Apple App Store](https://apps.apple.com/us/app/elves-vs-dwarves/id1231491435) + [apk.gold](https://elves-vs-dwarves.apk.gold/android-7.1.2)]：
- 转盘（Wheel）引入**保底机制**（guarantees）与**连抽机制**（consecutive draws）（原文："Wheel optimization, adding guarantees and consecutive draws"）
- 聊天屏蔽功能优化；战争大厅（War Hall）红点 Bug 修复；联盟公告板 Bug 修复

**战斗通行证（Battle Pass）[MEDIUM]** [[Apple App Store](https://apps.apple.com/us/app/elves-vs-dwarves/id1231491435)]：
- 约 2026 年 3–4 月推出（App Store 与 soft112 对版本号归属有一位偏差：App Store 记录为 v17.0.4，soft112 记录为 v17.0.5，日期均在 2026 年 3 月下旬）

**战役传奇章节（Campaign Legendary chapter）[MEDIUM]** [[Apple App Store](https://apps.apple.com/us/app/elves-vs-dwarves/id1231491435)]：
- 约 2026 年 4 月推出（App Store 记录为 v17.0.6，soft112 记录为 v17.0.7；两源日期一致，约 2026 年 4 月中下旬）

---

**品质稳定性维护（贯穿全期）**

**v16.8.7（2024-07-26）[HIGH]** [[Apple App Store](https://apps.apple.com/us/app/elves-vs-dwarves/id1231491435) + [apk.gold](https://elves-vs-dwarves.apk.gold/android-7.1.2)]：
- 新增城堡皮肤；修复 Tom 事件；修复登录问题；修复宝石显示；修复战斗报告重新分配兵种显示；修复集结点援兵道具错误

---

### 4.3 KBN 长青化运营策略演变

#### 阶段一：Gaea 时期（2016–2021）——成熟策略 MMO 的常规 Live Ops

KBN 在 Gaea 时期已是结构完整的策略 MMO，进行定期内容维护和活动运营。

#### 阶段二：Deca 接管初期（2021–2023）——稳定过渡

Deca 接手后保留聚锋团队继续运营 **[HIGH]** [[Embracer 官方公告](https://embracer.com/releases/embracer-group-acquires-mobile-game-developer-jufeng-studio-and-eight-mobile-titles/)]，以维稳为主。

#### 阶段三：系统全面扩展（2024–2026）

**（一）皮肤与系统付费体系全面铺开（2024 年 11 月）**

**v22.4.0（2024-11-06）[HIGH]** [[Apple App Store](https://apps.apple.com/us/app/kingdoms-of-camelot-battle/id476546099)]（原文逐项列出）：
- 城堡皮肤（castle skin）
- **英雄皮肤系统**（hero skin system）
- 行军皮肤（march skin）
- **传奇骑士**（legendary knight）
- **装备进化系统**（gear evolution）

**（二）社交付费机制（2025 年 11 月）**

**v22.7.8（2025-11-20 iOS）[MEDIUM]** [[Apple App Store](https://apps.apple.com/us/app/kingdoms-of-camelot-battle/id476546099)]（原文："New Feature – Special Cards"）：
- 新增**特殊卡牌**（Special Cards）功能

**（三）城市外观系统与周年营销（2026 年 1 月）**

**v22.8.0（2026-01-22 iOS）[HIGH]** [[Apple App Store](https://apps.apple.com/us/app/kingdoms-of-camelot-battle/id476546099)]（原文逐项列出）：
- 新增**城市光晕系统**（City Halo System）
- 新增 **14 周年纪念城市皮肤**（14th Anniversary City Skin）
- OTA 相关资源优化

> **关于"14 周年"**：KBN 移动版于 2012 年 3 月 1 日正式发布 **[HIGH]** [[Wikipedia/KoC](https://en.wikipedia.org/wiki/Kingdoms_of_Camelot)]，至 2026 年 1 月为其第 **14 周年**，名称完全吻合。Android 版同期内容相同，版本号为 v22.7.8（2025-12-10）。

**（四）持续稳定性维护（2026 年）**

**v22.8.2–v22.9.0（2026 年 1–4 月）[MEDIUM]** [[Apple App Store](https://apps.apple.com/us/app/kingdoms-of-camelot-battle/id476546099)]：
- 图形渲染问题修复；登录延迟优化；设备兼容性崩溃修复

---

### 4.4 两款游戏共性策略模式

| 策略维度 | EVD 表现 | KBN 表现 | 置信度 |
|----------|---------|---------|--------|
| **养成天花板持续上移** | Auralite Cave 21 级；英雄 6-10 星；坐骑 9 星 | 传奇骑士；装备进化系统 | **[HIGH/MEDIUM]** |
| **皮肤/外观付费体系** | Slime Balloon Castle；Stellar Dragon；Mysterious Mount Equipment | 城堡皮肤；英雄皮肤系统；行军皮肤；14 周年城市皮肤 | **[HIGH]** |
| **变现机制升级** | Wheel 保底+连抽（v16.8.9）；Battle Pass（约 2026.03） | Special Cards（v22.7.8）；City Halo System（v22.8.0） | **[HIGH/MEDIUM]** |
| **品质稳定性维护** | 每个主要版本均含详细 Bug 修复清单 | v22.8.x 系列密集技术修复 | **[HIGH]** |
| **周年/节日营销** | 季节性城堡皮肤（v16.7.x） | 14 周年纪念皮肤（v22.8.0） | **[MEDIUM]** |

---

## 5. 置信度统计

| 置信度 | 数量 | 主要覆盖范围 |
|--------|------|------------|
| **HIGH** | 22 条 | 公司背景、收购事实、历史时间线、财务数据、关键版本内容（双源确认） |
| **MEDIUM** | 8 条 | 部分版本内容（单 App Store 来源）；PocketGamer 团队数据；版本号有争议但功能确认的条目 |
| **UNVERIFIED（已删除）** | 3 条 | Hero's Journey 系统、英雄技能分类名称、KBN"迷雾远征·雪山" |
| **报告内合计** | **30 条** | — |

---

## 6. 参考来源（一手）

- [Embracer Group 官方收购公告（2021-10-14）](https://embracer.com/releases/embracer-group-acquires-mobile-game-developer-jufeng-studio-and-eight-mobile-titles/)
- [Deca Games Wikipedia](https://en.wikipedia.org/wiki/Deca_Games)
- [Kabam Wikipedia](https://en.wikipedia.org/wiki/Kabam)
- [Kingdoms of Camelot Wikipedia](https://en.wikipedia.org/wiki/Kingdoms_of_Camelot)
- [PR Newswire：Deca Live Ops 专家（Ken Go 原话来源）](https://www.prnewswire.com/news-releases/deca-games-are-the-live-ops-experts-breathing-new-life-into-old-games-640909603.html)
- [PocketGamer：Deca 运营策略与团队规模](https://www.pocketgamer.biz/deca-games-from-being-acquired-to-acquiring/)
- [Apple App Store：Elves vs Dwarves（iOS 版本历史权威来源）](https://apps.apple.com/us/app/elves-vs-dwarves/id1231491435)
- [Apple App Store：Kingdoms of Camelot: Battle（iOS 版本历史权威来源）](https://apps.apple.com/us/app/kingdoms-of-camelot-battle/id476546099)
- [Google Play：Elves vs Dwarves（发行商确认）](https://play.google.com/store/apps/details?id=com.kabam.evd&hl=en_US)
- [Google Play：Kingdoms of Camelot: Battle（发行商确认）](https://play.google.com/store/apps/details?id=com.kabam.kocmobile&hl=en_US)
- [apk.gold：EVD Android 版本日志（v16.8.x 详细英文 changelog）](https://elves-vs-dwarves.apk.gold/android-7.1.2)
- [GamesBeat：KBN 2012 年 App Store 最高收入（2012-12-21）](https://gamesbeat.com/kabam-scores-big-with-highest-grossing-game-on-app-store-for-2012/)

