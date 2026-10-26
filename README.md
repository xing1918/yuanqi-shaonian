# 元气少年 · 线上发布包

「元气少年」——用心理学方式减少手机依赖的手机 APP（PWA）：每日打卡、主动专注、冲动急救、AI 心理倾诉、数据洞察。不靠锁机靠自觉。

## 包内文件

```
├── index.html        应用本体（单文件，含全部功能）
├── manifest.json     PWA 应用清单（名称/图标/全屏模式）
├── sw.js             Service Worker（离线缓存）
├── vercel.json       Vercel 部署配置（缓存策略）
└── icons/            应用图标（192 / 512 / 遮罩自适应 / iOS）
```

## 方式一：GitHub + Vercel（推荐，可长期更新）

1. 注册 [GitHub](https://github.com)，点右上角 `+` → New repository，名称如 `yuanqi-shaonian`，选 Public，创建
2. 仓库页点 `Add file → Upload files`，把本文件夹里的**全部文件（含 icons 文件夹）**拖进去，点 `Commit changes`
3. 用 GitHub 账号登录 [Vercel](https://vercel.com) → `Add New → Project` → 找到刚建的仓库点 `Import`
4. Framework Preset 保持默认（Other），直接点 `Deploy`
5. 约 1 分钟后获得线上地址：`https://你的项目名.vercel.app`

以后要更新应用：重新上传 `index.html` 覆盖，Vercel 会自动重新部署。注意同步把 `sw.js` 第 2 行的缓存版本号 `yqsn-v1` 改成 `yqsn-v2`，用户端才会立即生效。

## 方式二：拖拽秒传（无需 Git，5 分钟上线）

- **Cloudflare Pages**（免费，国内访问较稳）：登录 [dash.cloudflare.com](https://dash.cloudflare.com) → `Workers & Pages → Create → Pages → Upload assets`，把本文件夹直接拖进去
- **Netlify Drop**：打开 [app.netlify.com/drop](https://app.netlify.com/drop)，把文件夹拖进网页即可

## 装到手机（上线后）

手机浏览器打开线上地址：
- 安卓 Chrome：菜单 →「安装应用 / 添加到主屏幕」
- iPhone Safari：分享 →「添加到主屏幕」

桌面即出现「元气少年」图标，点开全屏运行。

## 生成安卓 APK 安装包（可选）

1. 打开 [PWABuilder](https://www.pwabuilder.com)，输入你的线上网址，点 Start
2. 分析完成后选 `Package for stores → Android`
3. 下载 zip，解压后 `app-release-signed.apk` 可直接发给朋友试用，或上架应用商店

## 注意事项

- **数据隐私**：所有打卡、聊天数据只存放在用户设备本地（localStorage），不同设备互不相通，清浏览器数据会清空记录（可先在 App 设置里导出备份）
- **AI 心理咨询师**：需用户在 App「设置」里自行填入 OpenAI 兼容服务的 API Key（推荐智谱 glm-4-flash，有免费额度）；密钥只存用户设备。若所选服务商不允许浏览器直连（CORS 限制），换一家或加代理
- **危机干预**：自伤/轻生倾向的检测与心理援助热线提示（12356）内置在本地代码中，优先于 AI 执行，请勿删除该逻辑
- **免责**：AI 倾诉仅为情绪陪伴与心理科普，不能替代真正的心理咨询或治疗
