# The Atlas of Birmingham — 静态镜像归档

本仓库是 `https://www.atlasofbirmingham.co.uk/` 的**静态页面镜像**，用于离线归档与内部查阅。

## 抓取信息

| 项 | 值 |
|---|---|
| 源站 | https://www.atlasofbirmingham.co.uk/ |
| 建站平台 | Squarespace（托管式 SaaS，无公开源码） |
| 抓取日期 | 2026-09-28 |
| 页面数 | 142（sitemap 141 + 首页 + 3 个内链发现的分类页） |
| 静态资源 | 1453 个（图片 / CSS / JS / 字体 / 音视频） |
| 总体积 | 约 210 MB / 1592 个文件 |
| 抓取方式 | 按 `robots.txt` 规则抓取，仅抓取允许的公开页面 |

## 目录结构

```
./
├── index.html                      # 首页
├── all-blog/                       # 博客列表 + 每篇文章
├── career-blogs/                   # 职场日志栏目
├── atlasofbirmingham/              # 播客栏目
├── 50-places-1/  little-edward/    # 项目页
├── book-projects/  about/  contact/
├── _external/                      # 来自 CDN 的资源，按域名分目录
│   ├── images.squarespace-cdn.com/
│   ├── static1.squarespace.com/
│   └── use.typekit.net/
└── universal/  assets/  s/         # 站点自身路径下的资源
```

页面路径通过 `目录/index.html` 映射，例如源站 `/all-blog/aston-hall-prhss`
对应本地 `all-blog/aston-hall-prhss/index.html`。

## 本地预览

镜像里的链接已全部改写为**相对路径**，直接双击 `index.html` 即可浏览。
若需更接近线上效果（避免个别浏览器对 `file://` 的限制），起一个本地服务更好：

```bash
python -m http.server 8000
# 然后访问 http://localhost:8000
```

## 已知限制

镜像保存的是**渲染后的静态页面**，以下功能依赖 Squarespace 服务器，在本地**不可用**：

- 表单提交（联系表单、订阅）
- 站内搜索
- 博客分类 / 标签的动态筛选结果
- 后台 CMS 与商品下单
- 部分需要 Squarespace JS 运行时驱动的交互与动画

另有两处源站本身的失效链接被保留原样（抓取时即为 404）：
`/about-1`、`/shop/p/adventurer-yr2xa`。

## 版权说明

站内全部文字、图片、音频及其他内容的**著作权归 The Atlas of Birmingham 所有**。
本仓库仅作离线归档与内部查阅之用，请勿用于公开再分发或商业用途。
