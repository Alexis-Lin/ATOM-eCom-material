# ATOM 对外物料库 · ATOM Materials

BodyPark **ATOM 口袋 AI 私教机**的对外物料仓库：产品宣传素材、电商/官网销售详情页素材、包装印刷物。
每个物料项目自包含（`src` 源码 / `exports` 成品 / `docs` 决策与文案 / `README` 项目说明），可独立再生成。

> 命名与口径以《ATOM 产品定价与套装组合说明》为准，全局对照表见 [`docs/decisions.md`](docs/decisions.md)。

## 目录结构

```
detail-page/                 销售详情页素材（电商 / 官网）
  comparison-charts/         ├─ 套装对比图 + 会员对比图（中/英两套，详情页嵌入）
marketing/                   对外宣传素材（预留：KV、社媒、发布会物料…）
packaging/                   包装与随盒印刷物
  quick-guide/               ├─ 开箱快速指南（16 面小手册，54 × 85.6 mm）
docs/                        全局文档
  decisions.md               ├─ 命名 / 定价 / 会员政策 / 售前口径（所有物料共用）
```

## 物料索引

| 物料 | 位置 | 状态 | 成品 |
|---|---|---|---|
| 套装对比图（中/英） | `detail-page/comparison-charts/` | ✅ 已交付 | `exports/cn|global/1-kit-*.png` |
| 会员对比图 · 简洁/详细（中/英） | `detail-page/comparison-charts/` | ✅ 已交付 | `exports/cn|global/2-*, 3-*.png` |
| 开箱快速指南（中/英） | `packaging/quick-guide/` | ✅ 印刷初稿归档 | `final/`（印刷以此为准）；`exports/` 为排版稿参照 |
| 产品详情页优化提案 | `detail-page/product-page/` | 📝 提案中 | `docs/optimization-2026-08.md` |

## 约定

- **目录三层制**：`用途分类 / 物料项目 / src·exports·docs`。新物料照此建目录，并在上表登记。
- **成品可再生成**：所有图表/版式为纯 HTML/CSS 源码，导出流程见各项目 `docs/regenerate.md` 或 README。
- **语言版命名**：中文 `cn`、海外英文 `global`（详情页沿用历史命名）或 `en`（印刷物）。
