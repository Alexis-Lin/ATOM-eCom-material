# 产品详情页优化提案 · 主图与右栏（2026-08）

> 对象：bodypark.fit/products/bodypark-atom 详情页（Stand Alone 落地态截图）。
> 触发：运营草稿两处改动（主图信息化、套装选择器重排）。本文档 = 草稿评审 + 完整优化清单。

## 一、对草稿两处改动的评审

### 1. 主图信息化（logo + 套装名 + 会员 chip + reddot）—— 方向 ✓，两个修正

- ✅ **主图随所选套装联动**是最重要的一步：当前选择器切换后主图不变，用户看不到"这个套装到手是什么"。
  建议每个套装一张**组合物料图**（Training Kit = 主机+三脚架；Performance Kit = 全家福），左上角标套装名。
- ⚠️ **「+ Free Lifetime PLUS membership」chip 建议撤掉或改内容**：海外政策是**每个套装都送 Lifetime Plus**，
  这条不构成套装间的差异信息，且与右栏绿色 banner 完全重复。chip 位置应留给**随套装变化的差异点**
  （如 Performance Kit: `+12 mo PRO`，与套装对比图口径一致），才对得起主图黄金位。
- ✅ reddot 徽章前置是好的信任背书；注意按红点官方规范使用（标注获奖年份/类别，用官方素材，如
  `Red Dot Winner 2025`），不要裸放 logo。

### 2. 套装选择器重排（Performance Kit 置顶 + Most Popular）—— 方向 ✓，三个补强

- ✅ 高价锚定 + Most Popular 引导是标准做法。
- ➕ **卡片只有名字不够**：三个选项必须点开才知道区别。每张卡加一行：**内含物摘要 + 价格 + 会员赠送差异**
  （如 `ATOM + Gym Tripod + Pocket Bag · $299 · +3 mo PRO`）。数据口径直接用 docs/decisions.md 第 4 节。
- ➕ **Most Popular 做成徽章**（黑底/绿底小 chip），不要括号文本。
- ➕ **默认选中逻辑要定规则**：截图 URL 参数是 Stand Alone 但草稿高亮 Performance Kit——
  建议：直接流量默认 Most Popular；广告/比价落地保持与来源一致（URL 参数优先）。

## 二、主图与图集的其它优化点

1. **首图 3 秒法则**：当前首图只有渲染图，没回答"这是什么"。信息优先级建议：产品 + 一句定位
   （AI Fitness Companion）+ reddot；套装名在切换后出现。不要把 4 个元素全堆上去。
2. **图集叙事线**（缩略图顺序即讲故事顺序）：
   ① 我是谁（主图）→ ② 我能干什么（计数/纠错实拍，配屏显 x9/12 的绿环微注释）→
   ③ 怎么用（摆放/投屏场景）→ ④ 套装内含（flat-lay 拆箱图）→ ⑤ App 三屏 → ⑥ 技术/尺寸图。
3. **带文字的图**（"Not a Tracker. A Real AI Coach."）：缩略态文字不可读没关系，但大图态字号要过手机端可读线。
4. **What's in the box 图集化**：折叠面板点开率低，图集里放一张随套装联动的拆箱平铺图。

## 三、右栏文案优化点

### Key Features 重写（现 4 条的问题：口号化、行话、语义重复）

| 现文 | 问题 | 建议 |
|---|---|---|
| Every rep counts. Stay in the zone. | 口号，无信息量；与第 2 条重复 | **Counts every rep, corrects your form — live** |
| AI coach with real-time feedback | 与 1、3 重复 | （并入上一条） |
| Agentic AI trainer, smart adaptive planning | **Agentic 是行业黑话**，消费者不懂 | **Builds your weekly plan, adapts as you improve** |
| Portable MagMount design. Train anywhere, share with ease. | "share with ease" 语义不明 | **Pocket-sized — MagMount snaps on anywhere** |
| （缺） | 大屏是强卖点未出现 | **Cast workouts to your TV** |

原则：动词开头、每条 ≤8 词、一条一个利益点、不用内部术语。

### 促销 banner 层级

- 两条绿 banner 同色同权重叠放 → banner blindness。**First 1,000 Orders**（稀缺）保留 banner 位，
  可加剩余数量/倒计时；**Lifetime PLUS** 并入价格区或套装卡片行（它是"人人有"的政策，不是促销）。

### 结构补缺（转化三件套）

1. **价格**：截图可视区内没有价格——价格 + 划线价 + 套装差价必须跟选择器联动出现在首屏。
2. **评价**：星级 + 评论数（哪怕先少量）放 H1 下。
3. **保障行**：退货政策 / 质保 / 发货时效一行小字放加购按钮附近。
4. **一句话定位副标题**：H1 「BodyPark ATOM」下加 tagline（如 *Your AI coach that sees, counts, and corrects*），
   当前从 H1 直接跳 Key Features，缺"是什么"。
5. **套装对比入口**：选择器下方加 "Compare kits →"，直接复用本仓库
   `detail-page/comparison-charts/exports/global/1-kit-global.png`（现成物料）。

## 四、口径一致性（对照 docs/decisions.md）

- 套装名 Stand Alone / Training Kit / Performance Kit ✓ 一致。
- 会员名写法：图/文案中 `PLUS` 全大写与物料口径 `Plus` 不一致，建议统一（badge 视觉可全大写，正文用 Plus）。
- 主图若加 Pro 赠送差异，用套装对比图口径：`+1 / +3 / +12 mo`（盒内自带 1 个月的表达规则见 decisions.md 4）。

## 五、优先级建议

| P | 项 | 理由 |
|---|---|---|
| P0 | 价格/评价/保障补缺；Key Features 重写 | 转化基本盘 |
| P0 | 套装卡片加内含+价格+差异行 | 决策信息前置，减少跳出 |
| P1 | 主图随套装联动 + 差异 chip | 草稿方向，修正 chip 内容 |
| P1 | banner 层级拆分；Most Popular 徽章化 | 视觉权重 |
| P2 | 图集叙事线重排；拆箱图；Compare kits 入口 | 体验增强 |
