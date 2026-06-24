# Folding Stars 版本规范

项目采用语义化版本号 `V主版本.功能版本.修订版本`，文件夹统一命名为 `Folding-Stars-V主版本.功能版本.修订版本`。

- 修订版本：问题修复、文案或样式微调，例如 `V1.0.1` → `V1.0.2`
- 功能版本：新增向后兼容的功能，例如 `V1.0.2` → `V1.1.0`
- 主版本：重大改版或不兼容的数据结构变化，例如 `V1.9.0` → `V2.0.0`

每次发布必须同步修改以下三处：

1. `index.html` 中的 `APP_VERSION`
2. `version.json` 中的版本、发布日期和更新说明
3. `service-worker.js` 中的 `CACHE_NAME`

可在项目目录运行以下命令一次性同步这些位置：

```powershell
.\scripts\set-version.ps1 -Version 1.0.2 -Notes "本次更新说明"
```

完成修改并验证后，将文件夹改为对应版本名，提交并推送到 GitHub 的 `main` 分支。GitHub Pages 会自动部署；iPhone 主屏幕书签会在检测到高于上次已查看版本的版本号时提示一次，同一版本不会重复提示。
