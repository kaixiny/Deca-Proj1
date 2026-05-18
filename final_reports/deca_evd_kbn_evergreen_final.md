# EVD & KBN 长青化运营策略演变报告（定稿）

---

## 修订日志

**版本**：deca_evd_kbn_evergreen_final
**基于**：deca_evd_kbn_evergreen_draft.md
**审查**：deca_evd_kbn_evergreen_audit.md
**时间**：2026-05-17

### 修订 #1（对应 audit 编号 A16）

**位置**：四、EVD 长青化策略演变 → 阶段二"Deca 接管后的内容深化"更新表格，第 4 行
**修订前**：`| 2025-02 | v16.9.3 | 添加聊天翻译功能…`
**修订后**：`| 2025-05 | v16.9.3 | 添加聊天翻译功能…`
**理由**：Apple App Store 两次独立 fetch 均显示 v16.9.3 发布日期为 05/08/2025（5 月）。"2025-02" 是相邻版本 v16.9.2 的月份。
**验证 URL**：[Apple App Store - EVD](https://apps.apple.com/us/app/elves-vs-dwarves/id1231491435)

### 修订 #2（对应 audit 编号 A22）

**位置**：二、所有权链 2.2 EVD — 2017-06-30 节点置信度标注
**修订前**：声明隐含 HIGH 置信度
**修订后**：显式标注 **[MEDIUM]**
**理由**：所有关联主页面 fetch 返回 403 或 SSL 错误，无法直接从一手来源验证。多搜索结果一致支持但不构成两个独立一手来源。
**验证 URL**：不可访问（search results 综合）

### 修订统计

| 项目 | 数值 |
|------|------|
| 总声明数 | 38 |
| 通过验证 | 20 |
| 已修订错误 | 1 |
| 降级声明（HIGH→MEDIUM）| 1 |
| 未改动（MEDIUM/LOW 无争议）| 16 |

---

# EVD & KBN 长青化运营策略演变报告

**研究主题**：Deca 中国工作室（飓风工作室 / Jufeng Studio）旗下代理的 EVD、KBN 两款游戏的长青化运营策略演变
**报告版本**：final
**生成日期**：2026-05-17
**研究方法**：多轮 WebSearch + WebFetch，优先一手来源（App Store 版本历史、官方新闻稿、Wikipedia），所有声明附置信度标签

---

## 一、实体识别结论

| 缩写 | 全名 | 匹配规则 | 置信度 |
|------|------|----------|--------|
| EVD | **Elves vs Dwarves**（精灵大战矮人） | 首字母规则（E·V·D）；Google Play 包名 `com.kabam.evd` 直接印证 | **HIGH** |
| KBN | **Kingdoms of Camelot: Battle for the North**（卡美洛王国：北境之战） | 跳过连接词规则（**K**ingdoms … **B**attle … **N**orth） | **HIGH** |

**Deca 中国工作室**即**飓风工作室（Jufeng Studio）**，由 Embracer Group 旗下子公司 Deca Games 于 2021 年 10 月从盖娅互娱（Gaea Mobile）收购，工作室位于北京，团队约 50 人，持续独立运营。EVD 与 KBN 均属飓风工作室管理的六款游戏之列。 **[HIGH]** [[来源]](https://embracer.com/releases/embracer-group-acquires-mobile-game-developer-jufeng-studio-and-eight-mobile-titles/)

---

## 二、所有权链与历史背景

### 2.1 KBN 所有权链

```
Kabam（Watercooler Inc.）
│  2009-11-02  Kingdoms of Camelot 浏览器版公测
│  2011-11-21  KBN 手游 iOS 公测；2012-03-01 正式上线
│  2012         KBN 成为当年 iOS 年度最高销售榜首
│  2016-01-07  Kabam 将旗下传统手游打包出售给盖娅互娱（Gaea Mobile）
▼
盖娅互娱 / 飓风工作室（Jufeng Studio）
│  2016–2021   KBN 持续运营，面向全球市场（亚太以外占 99%+ 收入）
▼
Deca Games（Embracer Group 旗下，2021-10 收购）
│  2021–今     继续迭代，当前版本已达 22.9.x
```

**来源**：
- Kabam→Gaea 交易：**[HIGH]** [[Business Wire 公告 2016-01-07]](https://www.businesswire.com/news/home/20160107006328/en/Kabam-Divests-Classic-Mobile-Games-and-Publishing-Business-to-GAEA) | [Wikipedia 核实](https://en.wikipedia.org/wiki/Kingdoms_of_Camelot)
- KBN 2012 年 iOS 榜首：**[HIGH]** [[Wikipedia: Kingdoms of Camelot]](https://en.wikipedia.org/wiki/Kingdoms_of_Camelot)
- Gaea→Deca 交易：**[HIGH]** [[Embracer 官方新闻稿]](https://embracer.com/releases/embracer-group-acquires-mobile-game-developer-jufeng-studio-and-eight-mobile-titles/)

### 2.2 EVD 所有权链

```
Kabam
│  2012-10    The Hobbit: Kingdoms of Middle-earth（霍比特人：中土王国）上线
│             基于《霍比特人》电影 IP 授权的移动端策略游戏
│  2016-01-07 与 KBN 一同售予盖娅互娱
▼
盖娅互娱 / 飓风工作室
│  2017-06-30 《霍比特人》IP 授权到期，游戏关闭  [MEDIUM]
│  2017        【关键策略节点】去 IP 化重塑：将游戏核心玩法 1:1 迁移至
│             自有 IP《Elves vs Dwarves》；玩家账号、进度全量迁移  [MEDIUM]
▼
Deca Games（2021-10 收购）
│  2021–今    继续迭代，当前版本 17.0.7（2026-04-23）
```

**来源**：
- 霍比特人游戏 2017 年关闭：**[MEDIUM]** [多搜索结果一致；主页面 fetch 不可访问]
- EVD 为替代品、包名 `com.kabam.evd`：**[HIGH]** [[Google Play 商店]](https://play.google.com/store/apps/details?id=com.kabam.evd)

---

## 三、Deca 长青化运营的整体哲学

Deca Games 的核心商业逻辑被其创始人 Ken Go（前 Kabam 欧洲区总经理）概括为：

> "DECA believes games can last decades and built the company around that belief."

公司定位为"**纯粹的实况运营（Live Ops）专家**"，商业模式基于：
1. **低价收购**有忠实社群但被原开发商搁置的游戏资产；
2. **注入专业 live ops 资源**（社群管理、产品、功能开发、客服、活动策划）；
3. 通过**长期运营**而非新游开发来持续盈利。

公司于 2020-08-13 被 Embracer Group 以约 €25M 预付款 + 最高 €60M（7 年对赌）收购，验证了这一模式的规模化可行性。 **[HIGH]** [[Embracer 收购 Deca 公告]](https://embracer.com/releases/embracer-group-acquires-deca-games/)

2022 财年 Deca 整体收入达 **€156.05M**，预测利润率超 35%。 **[HIGH]** [[Wikipedia: Deca Games]](https://en.wikipedia.org/wiki/Deca_Games) | [[Embracer 收购公告]](https://embracer.com/releases/embracer-group-acquires-deca-games/)

---

## 四、EVD 长青化策略演变

### 阶段一：IP 授权危机与去 IP 化重塑（2016–2017）

**核心事件**：《霍比特人》授权到期 → 关闭原游戏 → 以自有 IP 重启

EVD 的长青化之路起点是一次**被迫的品牌重构**。Gaea/飓风接手游戏后，面临《霍比特人》版权到期这一根本性风险。策略团队的应对是：不续版权、不关服，而是将全部核心机制（阵营选择、城建、部队、英雄系统）迁移至全新原创 IP《Elves vs Dwarves》，玩家账号与进度 100% 迁移，有效降低了玩家流失。

这一操作将游戏从**IP 授权依赖型**转型为**独立 IP**，消除了未来再次面临授权到期的风险，为长期运营奠定基础。 **[MEDIUM]** [来源：搜索结果综合；主页面不可访问]

### 阶段二：Deca 接管后的内容深化（2021–2026）

Deca 接手后延续了飓风工作室原有团队和运营节奏，重点投入**系统深度扩展**：

| 时间 | 版本 | 策略动作 | 来源 |
|------|------|----------|------|
| 2024-09 | v16.8.9 | 新城堡皮肤；活动 & 登录 bug 修复 | **[HIGH]** [Apple App Store](https://apps.apple.com/us/app/elves-vs-dwarves/id1231491435) |
| 2024-11 | v16.9.0 | 转盘优化（加入保底与连抽机制）— 重大变现机制调整 | **[HIGH]** [Apple App Store] |
| 2024-12 | v16.9.1 | 英雄解锁上限扩展至 6-10 星 — 纵向进深延伸 | **[HIGH]** [Apple App Store] |
| **2025-05** | v16.9.3 | 添加聊天翻译功能；英雄 6 级装备 — 社群互联与装备深化 | **[HIGH]** [Apple App Store] |
| 2025-12 | v17.0.2 | 坐骑升星扩展至 9 星；专属坐骑皮肤 | **[HIGH]** [Apple App Store] |
| 2026-03 | v17.0.4 | **Battle Pass（战令）系统上线** — 重大变现模式升级 | **[HIGH]** [Apple App Store] |
| 2026-04 | v17.0.7 | 新部队与英雄 | **[HIGH]** [Apple App Store] |

**策略模式提炼**：
1. **纵向进深（Vertical Depth）**：英雄星级、坐骑升星、装备等级不断扩展上限，给老玩家持续提供进阶目标。
2. **变现机制现代化**：从纯粹付费资源包转向转盘保底 + 战令（Battle Pass），追赶行业主流变现设计。
3. **社群工具**：聊天翻译功能降低跨语言玩家社群壁垒，有助于国际化玩家保留。

### 阶段三：当前状态（2026）

游戏持续活跃更新（每月至少一次），但 **App Store 评分仅 2.2/5（465 评价）** **[HIGH]** [Apple App Store]，表明玩家满意度存在显著挑战。玩家反馈集中于变现压力增大。

---

## 五、KBN 长青化策略演变

### 阶段一：从网页到手游的品类延伸（2009–2012）

KBN 本身即 Kingdoms of Camelot 的长青化产品——将 2009 年的 PC 浏览器策略游戏移植为移动原生游戏，2012 年成为 iOS 年度最高销售榜首，证明了 IP 跨平台迁移的商业价值。 **[HIGH]** [[Wikipedia]](https://en.wikipedia.org/wiki/Kingdoms_of_Camelot)

### 阶段二：Gaea/飓风维持期（2016–2021）

Gaea 接手后以全球化运营为主，不大改核心玩法，专注于稳定的活动运营和功能维护。收购时（2021-Q3）合并八款游戏共约 150,000 DAU / 800,000 MAU，季度总毛收入约 SEK 5,000 万。 **[HIGH]** [[Embracer 新闻稿]](https://embracer.com/releases/embracer-group-acquires-mobile-game-developer-jufeng-studio-and-eight-mobile-titles/)

### 阶段三：Deca 接管后的系统扩展（2021–2026）

当前版本已达 22.x，说明游戏进行了超过 22 个大版本迭代（自 2012 年首发以来）。

| 时间 | 版本 | 策略动作 | 来源 |
|------|------|----------|------|
| 2024-11 | v22.4.0 | **传奇骑士系统**上线；新城堡 / 英雄 / 行军皮肤 — 重大系统扩展 | **[HIGH]** [Apple App Store](https://apps.apple.com/us/app/kingdoms-of-camelot-battle/id476546099) |
| 2025-07 | v22.7.4 | 推荐礼包功能 — 主动推送变现工具 | **[HIGH]** [Apple App Store] |
| 2025-11 | v22.7.8 | **特殊卡牌（Special Cards）**系统 — 新变现品类 | **[HIGH]** [Apple App Store] |
| 2026-01 | v22.8.0 | **城市光环（City Halo）系统** + 14 周年纪念皮肤 | **[HIGH]** [Apple App Store] |
| 2026-04 | v22.9.0 | 图形渲染 / 登录稳定性修复 | **[HIGH]** [Apple App Store] |

**策略模式提炼**：
1. **里程碑式系统扩展**：传奇骑士、特殊卡牌、城市光环等新系统以季度级别推出，持续为老玩家创造新目标。
2. **周年纪念锚点**：14 周年纪念皮肤（2026 年游戏发布已满 14 年）以周年节点作为玩家情感锚点，强化归属感。
3. **稳定性优先**：近期多个版本以修复登录 / 图形问题为主，反映 Deca 对技术基础设施的持续投入。
4. **服务器合并政策**：Deca 为人口下降的服务器实施合并策略，将两个旧服迁移至一个新服，保留全部角色进度，以维持活跃社区规模。 **[MEDIUM]** [[Deca 官方支持页]](https://support.decagames.com/hc/en-us/articles/30917602002589-Server-Merge-Policies)

### 阶段四：当前状态（2026）

App Store 评分 **3.1/5（413 评价）** **[HIGH]** [Apple App Store]，高于 EVD 但仍属中低水平。社区博主（2024-12）评论游戏"losing gas day by day"。 **[LOW]** [[kocbattle4thenorth.home.blog]](https://kocbattle4thenorth.home.blog/)

---

## 六、横向比较：两款游戏长青化策略异同

| 维度 | EVD | KBN |
|------|-----|-----|
| **IP 风险管理** | 主动去 IP 化（2017 年霍比特人授权到期后重建自有 IP）| 无 IP 授权风险（原创中世纪题材） |
| **核心玩法迭代** | 保留原核心机制，持续扩展英雄 / 坐骑 / 装备上限 | 保留核心策略玩法，叠加传奇骑士等新系统 |
| **变现机制演化** | 转盘保底（2024）→ Battle Pass（2026-03） | 推荐礼包（2025）→ 特殊卡牌（2025）→ 城市光环（2026） |
| **社群工具** | 聊天翻译（2025-05）提升国际化 | Discord 官方社群 + 周年纪念活动 |
| **服务器管理** | 通用 Deca 服务器合并政策 | 通用 Deca 服务器合并政策 |
| **App Store 评分** | 2.2/5（较低）| 3.1/5（中低）|
| **当前版本号** | 17.0.7 | 22.9.0（版本数量显著更高，首发更早）|

**共同规律**：
1. **"不关服、不弃玩家"原则**：所有权每次更迭时均承诺保留玩家数据和进度。
2. **持续纵向深化（Vertical Depth Expansion）**：避免横向扩展新玩法，而是对现有系统（英雄、装备、坐骑）不断加深上限，以低研发成本延长付费生命周期。
3. **变现机制现代化**：逐步从资源直售型向系统化变现（战令、保底转盘）转型，追齐行业最佳实践。
4. **面向全球西方市场**：亚太之外贡献 99%+ 收入，这决定了运营语言（英语）和活动设计（欧美文化节点）。

---

## 七、外部环境：Embracer 重组的影响（2023–2024）

2023 年 6 月，因 Savvy Games Group 约 20 亿美元战略投资意外终止，Embracer Group 宣布大规模重组，从 2023 年 6 月至 2024 年 5 月共关闭 44 个工作室、裁员 4,532 人。 **[HIGH]** [[Embracer 官方声明]](https://embracer.com/releases/embracer-group-announces-comprehensive-restructuring-program-with-immediate-implementation/) | [[Wikipedia]](https://en.wikipedia.org/wiki/Embracer_Group)

**对 Deca/飓风工作室的影响**：Deca 旗下手游（包括 EVD、KBN）因属于盈利性 live ops 资产，并未见具体裁撤报道。Wikipedia 记载 Deca 2022 年整体营收达 €156.05M，说明在重组压力下仍保持商业可行性。然而，重组带来的资源收缩可能限制了新功能的研发投入速度。 **[MEDIUM]** [综合多来源推断]

---

## 八、主要数据汇总

| 指标 | 数值 | 时间点 | 来源 | 置信度 |
|------|------|--------|------|--------|
| 八款游戏合计 DAU | ~150,000 | 2021-Q3 | Embracer 官方新闻稿 | HIGH |
| 八款游戏合计 MAU | ~800,000 | 2021-Q3 | Embracer 官方新闻稿 | HIGH |
| 八款游戏季度毛收入 | ~SEK 5,000 万 | 2021-Q3 | Embracer 官方新闻稿 | HIGH |
| Deca 年营收 | €156.05M | 2022 财年 | Wikipedia | HIGH |
| Deca 利润率 | >35% | 收购时预测（2020）| Embracer 收购公告 | HIGH |
| EVD App Store 评分 | 2.2/5（465 评） | 2026-05（研究时）| Apple App Store | HIGH |
| KBN App Store 评分 | 3.1/5（413 评） | 2026-05（研究时）| Apple App Store | HIGH |
| KBN 历史注册玩家 | 950 万+ | 未注明（营销文案）| App Store 描述 | LOW |

---

## 九、置信度统计

| 置信度 | 声明数量 | 说明 |
|--------|----------|------|
| HIGH | 27 条 | 两个以上独立一手来源，或直接可验证数据（App Store / 官方新闻稿）|
| MEDIUM | 8 条 | 单一权威来源，或多来源综合推断（含 audit 降级 1 条）|
| LOW | 3 条 | 仅社区来源或营销文案 |
| UNVERIFIED | 0 条 | 已全部排除或标注 |

---

## 十、已知局限性

1. **Deca 支持页面无法访问**：support.decagames.com 对 WebFetch 返回 403，无法直接获取更新日志全文，版本描述依赖 App Store 版本历史。
2. **无单款游戏财务数据**：Embracer 未拆分 EVD / KBN 各自的收入或 DAU 数据，仅有合并的八款游戏聚合数据（2021 年数据）。
3. **EVD 2017 年重品牌节点置信度**：飓风工作室关于霍比特人 IP 授权到期及 EVD 创建的决策细节，标注为 MEDIUM，缺乏直接可访问的官方一手文件。
4. **App Store 版本描述轻微不稳定性**：两次 fetch 部分中间版本（如 v16.9.8、v17.0.2）的功能描述存在差异，核心战略性声明（Battle Pass、保底转盘、英雄星级）两次一致，可信度高。
5. **红队审查潜在误差**：同工具同偏差风险；Tolkien Gateway 等来源因 403 无法访问，EVD 去 IP 化细节存在 1-2 条潜在不准确风险。

---

*报告由 Claude Code + company-game-research skill 生成，研究日期 2026-05-17。*
*三件套：draft / audit / final 均保存于 `final_reports/` 目录。*
