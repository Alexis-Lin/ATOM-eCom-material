# 开箱快速指南 · Quick Guide

随盒印刷小手册：**8 张正反面 = 16 面**，单面 54 × 85.6 mm（信用卡尺寸），中 / 英各一套单语版。

```
src/quick-guide.html         可交互排版稿（结构与文案的参照源）：
                             EN / 中文 / 双语三模式切换、54 × 85.6 mm 打印 CSS、?page=N&lang=xx 单页模式
exports/
  cn/ en/                    逐页 PNG（1500 px 宽，约 700 dpi）
  quick-guide-print-*.pdf    排版稿导出的印刷 PDF（矢量）
final/                       设计师最终印刷初稿交付板（2026-08 归档，**印刷以此为准**）
docs/
  copy-and-decisions.md      一致性核查、16 页结构、字号系统、双语文案表、全部迭代决策与待办
  en-copy-review.md          英文版审校（准确性/啰嗦/native/一致性）
  en-copy-checklist-final.md 英文版逐页替换清单（终版，含定稿口径）
  print-draft-archive.md     印刷初稿归档记录 + 审校建议采纳情况
```

## 再生成

排版稿改动后（改 `src/quick-guide.html`）：

```bash
cd packaging/quick-guide/src && python3 -m http.server 8017 &
# 每语言：print-to-pdf 出矢量 PDF → pypdfium2 逐页转 PNG（勿用 --screenshot，见 docs 踩坑记录）
```

完整管线与注意事项见 `docs/copy-and-decisions.md` 第 6 节。

## 印刷前待办

见 `docs/copy-and-decisions.md` 第 7 节：`/r/help` 重定向服务上线、企业微信活码替换、
（后续版次）自动静音上线后切换 P15 文案。
