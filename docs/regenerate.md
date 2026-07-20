# 如何重新生成 PNG

图表是纯 HTML/CSS（无外部依赖、无构建步骤），用无头 Chrome 按 @2x 截图导出。

## 前置

- macOS + Google Chrome
- Python 3（仅用于起本地静态服务器）

## 步骤

**1. 改数据** —— 编辑 `charts/` 下对应 HTML 里的 `DATA` 对象（文案 / 档位 / 配额都在那里）。

**2. 起本地服务器**（不要用 `file://`，见下方注意事项）：

```bash
cd charts && python3 -m http.server 8000
```

**3. 用一个包裹页只保留目标图并测高**，再按实际高度截图。示例脚本（导出套装图中文版）：

```bash
CHROME="/Applications/Google Chrome.app/Contents/MacOS/Google Chrome"

# 包裹页：白底、固定 424px 容器、只保留第 0 张图、把高度写进 <title>
cat > _w.html <<'EOF'
<!doctype html><html><head><meta charset="utf-8"><title>x</title></head><body>
EOF
cat kit-compare.html >> _w.html
cat >> _w.html <<'EOF'
<style>
  body{background:#fff!important}
  .page{width:424px!important;max-width:none!important;margin:0!important;padding:16px!important}
  .page-note,.chart-cap{display:none!important}
  .pair{gap:0!important;justify-content:flex-start!important}
  .chart-wrap{align-items:flex-start!important}
</style>
<script>
  const n = parseInt(new URLSearchParams(location.search).get('chart') || '0');
  [...document.querySelectorAll('.chart-wrap')].forEach((w,i)=>{ if(i!==n) w.remove() });
  requestAnimationFrame(()=>{
    const c = document.querySelector('.chart');
    document.title = 'H=' + Math.ceil(c.getBoundingClientRect().height)
                   + 'OV' + (c.scrollWidth > c.clientWidth + 1 ? 1 : 0) + 'END';
  });
</script></body></html>
EOF

# 测高（同时检查是否横向溢出：OV1 = 有溢出，需修）
H=$("$CHROME" --headless=new --disable-gpu --hide-scrollbars \
      --window-size=424,1200 --virtual-time-budget=6000 \
      --dump-dom "http://localhost:8000/_w.html?chart=0" \
    | grep -o '<title>H=[0-9]\+' | grep -o '[0-9]\+')

# 按实际高度 + 32 留白导出 @2x
"$CHROME" --headless=new --disable-gpu --hide-scrollbars \
  --force-device-scale-factor=2 --window-size=424,$((H+32)) \
  --virtual-time-budget=6000 \
  --screenshot=out.png "http://localhost:8000/_w.html?chart=0"
```

- `?chart=0` = 中文版，`?chart=1` = 英文版（`membership-stack.html` 只有一张，省略参数即可）。
- 会员图容器用 **432px**（图宽 400px），套装图用 **424px**（图宽 392px）。

## 注意事项（都是踩过的坑）

- **无头 Chrome 最小窗宽约 500px**。若内容宽度接近上限，右侧会被裁掉。务必把外层容器固定宽度、内容靠左，并用上面的 `OV` 检查确认无横向溢出。
- **中文乱码**：HTML 是不带 `<head>` 的片段，直接 `file://` 打开会因缺 `<meta charset="utf-8">` 而乱码。用 `python3 -m http.server` 并在包裹页里加 charset。
- **`requestAnimationFrame` 偶发未触发**导致读不到标题，脚本里做 3～5 次重试即可。
- **列宽溢出**：给列容器加 `min-width: 0`，并把长标签缩短，避免 `white-space: nowrap` 的内容撑破网格。

## 现有 PNG 规格

宽 848 / 864 px（424 / 432pt @2x），白底、无边框、手机屏宽，高度随内容。

## 校验基准（改版前的参考高度，CSS 单位）

| 图 | 中文 | 英文 |
|---|---|---|
| kit-compare | 541 | 574 |
| membership-matrix | 930 | 1083 |
| membership-stack | 571 | — |
