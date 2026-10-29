# 恒逸石化文莱二期：公开事实与图件

资料核验截至 **2026-10-29**。静态网页，涵盖项目记录、官方勘察点、逐年卫星影像、土地面积、采购与当地消息、财报及原始来源。

## 地图与卫星

- 跨年影像在左右对比图中选择，不单独展示缩略图总览；默认左侧2025-06-16、右侧2026-06-06。
- 左右日期可选11景；最新检出的2026-10-24两个窗口云影100%，保留质量说明，不能据其判断施工进度。
- 可切换到 ZB1／ZB25 勘察点周边的局部窗口。
- 二期正式厂区边界尚未核实；勘察点不等于二期地块或主体装置边界。
- 保留放大、鼠标拖动、复位、左右分界及来源筛选。
- 原图未使用生成式增强；图像署名、采集日期、云影比例和口径见网页。

## 目录

- `public/index.html`：网页内容。
- `public/assets/`：去重后的原图、样式及交互脚本；文件名由内容哈希生成。
- `public/documents/`：文莱海事局原始公开 PDF。
- `public/data/source-index.csv`：43条来源追溯记录；页面展示40条，沿用既有自写来源文案的隐藏要求。
- `public/data/imagery-manifest-20261029.json`：逐景采集日期、原始影像链接、裁切网格、质量筛选与文件哈希。
- `research/update-2026-10-29.md`：本轮更新的方法、核验结果与证据范围。
- `wrangler.jsonc`：Cloudflare Pages 配置。

## 本地预览

无需构建：

```sh
python3 -m http.server 8787 --directory public
```

## Cloudflare Pages

Git 仓库：`llchen2026/hengyi-dashboard`；生产分支：`main`。

- 客户页面：https://hengyi-dashboard-rongxin.pages.dev/
- 原页面：https://hengyi-dashboard.pages.dev/
- 两个Pages项目均连接同一仓库main，提交后自动更新；页面标题为“恒逸文莱二期卫星及AI进度监测”。

- 构建命令：留空。
- 输出目录：`public`。
- 运行时不需要 API 密钥或环境变量。

手动部署同一目录：

```sh
npx wrangler@4.151.3 whoami
npx wrangler@4.151.3 pages deploy public --project-name=hengyi-dashboard --branch=main
```

图件、公开文件和引用内容的权利归各原始提供者；逐项来源与署名保留在报告中。
