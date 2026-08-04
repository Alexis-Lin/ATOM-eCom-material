# 详情页对比图 · Comparison Charts

官网 / 电商详情页对比图物料。**两套交付**（国内中文 / 海外英文），每套三张，均为 @3x 高清、手机屏宽、白底全直角。

```
src/
  kit-compare.html          套装对比（中 + 英）
  membership-simple.html    会员 · 简洁版（详情页首屏）
  membership-matrix.html    会员 · 详细版（逐项核对）
exports/
  cn/                       国内 · 中文（1-kit / 2-membership-simple / 3-membership-detail）
  global/                   海外 · English（同构三张）
docs/
  regenerate.md             无头 Chrome 出图流程与校验基准
```

**规格**：宽 1272 / 1296 px（424 / 432pt @3x），PNG，白底、无边框、全直角，高度随内容。

**两套的区别**：套装对比国内/海外内容不同（币种 ¥/$、赠送时长）；会员对比功能矩阵全球一致，仅语言不同。

## 视觉规范

| 层级 | 字号 | 用途 |
|---|---|---|
| 标题 | 20 | 主标题 |
| 副标题 / 横幅 / 档位名 | 13.5 | 副标题、购机横幅、Basic/Plus/Pro 名 |
| 正文 | 12–13.5 | 功能条目、格值 |
| 说明 | 9.5–10 | 分组标签、注释、脚注 |

**配色**：Basic 灰 / Plus 绿 / Pro 黑金，档位名压黑底会员卡；套装图单绿渐进。
**造型**：套装图全直角；会员图小圆角 r=3（既定决策）。勾选为品牌绿 #5E8A00 粗线。
**关键信息**：会员图顶部横幅明示「购买 ATOM 主机即送 Pro + Plus 会员」。

改数据：编辑 `src/*.html` 顶部 `DATA`，按 `docs/regenerate.md` 重新导出。
命名 / 定价 / 售前口径见根目录 [`docs/decisions.md`](../../docs/decisions.md)。
