# ATOM 电商物料 · ATOM eCommerce Material

BodyPark **ATOM 口袋 AI 私教机**的官网 / 电商详情页对比图物料。**两套交付**（国内中文 / 海外英文），每套三张，均为 @3x 高清、手机屏宽、白底全直角。

> 交付对象：官网设计团队 + 电商运营团队。
> 数据与命名以《ATOM 产品定价与套装组合说明》为准；政策更新时同步本仓库。

---

## 交付素材（assets/）

```
assets/
  cn/                              国内 · 中文
    1-kit-cn.png                   套装对比
    2-membership-simple-cn.png     会员对比 · 简洁版（详情页首屏）
    3-membership-detail-cn.png     会员对比 · 详细版（逐项核对）
  global/                          海外 · English
    1-kit-global.png               Kit comparison
    2-membership-simple-global.png Membership · simple
    3-membership-detail-global.png Membership · detailed
```

**规格**：宽 **1272 / 1296 px**（424 / 432pt @3x），PNG，白底、**无边框、全直角**，高度随内容。可直接在手机查看或嵌入详情页。

**两套的区别**：
- **套装对比**：国内 / 海外内容不同（币种 ¥/$、赠送时长不同）。
- **会员对比**：功能矩阵全球一致，仅语言不同。

---

## 视觉规范

**字号阶梯（全表统一）**

| 层级 | 字号 | 用途 |
|---|---|---|
| 标题 | 20 | 主标题 |
| 副标题 / 横幅 / 档位名 | 13.5 | 副标题、购机横幅、Basic/Plus/Pro 名 |
| 正文 | 12–13.5 | 功能条目、格值（密度大的简洁版用 12） |
| 说明 | 9.5–10 | 分组标签、注释、脚注、用量单位 |

**配色**：三档三色 —— Basic 灰 / Plus 绿 / Pro 黑金；档位名压**黑底会员卡**（银 / 绿 / 金字）。套装图为单绿渐进。

**造型**：**全部直角**（黑卡、色块、高亮块、标签、横幅均无圆角），贴合运动产品调性；勾选为粗线条深色。

**关键信息**：会员图顶部横幅明示「购买 ATOM 主机即送 Pro + Plus 会员」，预防"买硬件是否还要买会员"的售前疑问；「即将」功能已并入功能列表内联标注。

---

## 源码与再生成（charts/ · docs/）

```
charts/
  kit-compare.html          套装对比（中 + 英）
  membership-simple.html    会员 · 简洁版（中 + 英）
  membership-matrix.html    会员 · 详细版（中 + 英）
docs/
  decisions.md              命名 / 定价 / 会员政策 / 售前口径 / 待决
  regenerate.md             无头 Chrome 出图流程与校验基准
```

图表为纯 HTML/CSS（无依赖）。改数据编辑 `charts/*.html` 顶部 `DATA`，再按 `docs/regenerate.md` 用无头 Chrome 以 `--force-device-scale-factor=3` 导出 @3x。

---

## 待决

见 [`docs/decisions.md`](docs/decisions.md) 第 8 节。主要：「预览 / Preview」的具体定义；内部功能表与本物料口径对齐；防撞彩壳到货（约 9 月）加回套装图。
