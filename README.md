# WanderMate 官网

WanderMate 旅行伴侣匹配与行程规划产品的品牌官网 —— 单页静态站点，零构建依赖。

- **线上地址**：https://wandermate.com.cn
- **隐私政策**：https://wandermate.com.cn/privacy/
- **账号删除说明**：https://wandermate.com.cn/privacy/account-delete.html

---

## 目录结构

```
.
├── index.html          # 单页站点（自包含）
├── assets/
│   ├── img/            # 10 张图片（本地自托管）
│   └── fonts/          # 字体文件 + fonts.css（本地自托管）
└── README.md
```

## 本地资源自托管

站点**不依赖任何第三方 CDN**，图片与字体全部随仓库分发：

| 资源 | 位置 |
|---|---|
| 配图（10 张） | `assets/img/` |
| 字体（DM Mono / Noto Sans SC / Playfair Display） | `assets/fonts/` |

带来的收益：

- **境内访问稳定**：不依赖 `fonts.googleapis.com`（境内被墙）与境外图片 CDN，首屏不再因字体阻塞
- **零外部请求**：`index.html` 中无任何第三方域名引用
- **可离线预览**：直接双击 `index.html` 即可完整渲染

## 本地预览

```bash
python3 -m http.server 8080
# 浏览器打开 http://127.0.0.1:8080
```

## 部署形态

站点自托管于自有服务器，由 nginx 承载并强制 HTTPS：

- 站点根目录：`/www/wwwroot/wandermate.com.cn`
- 静态资源长缓存 30 天（文件名带哈希），`index.html` 不缓存，改完即时生效
- 后端 API 同域挂在 `/api/`（见 `server/`）

## 设计说明

深色电影感「黑金」配色，中文产品叙事，呈现 WanderMate 三条核心体验线：旅伴匹配、共同行程规划、轻量多人协作。
