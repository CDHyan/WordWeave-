# WordWeave · 语境词文

一个单文件网页：用自己的 OpenAI 兼容 API Key，按 CEFR 等级 i+1 生成英语分级阅读文章，点词即查释义。

## 目录

| 文件 | 作用 |
|---|---|
| `index.html` | 入口，自动跳到 `wordweave.html`（脚本用 `location.replace`，不会产生多余历史记录） |
| `wordweave.html` | 全部功能都在这个文件里（原生 JS + 原生 CSS，无依赖、无构建） |
| `notice.js` | 使用须知正文，改这个文件即可更新弹窗内容 |

## 本地使用

直接用浏览器打开 `wordweave.html` 即可（`file://` 也能读到 `notice.js`）。

## 部署到 GitHub Pages

1. 新建一个 **Public** 仓库（免费账号的 Pages 只对公开仓库开放）。
2. 把本目录的 3 个文件上传到仓库根目录（网页上可直接拖拽上传，或用下面的 git 命令）。
3. 仓库 → **Settings → Pages** → Source 选 **Deploy from a branch** → Branch 选 **main**，目录选 **/ (root)** → Save。
4. 等 1 分钟左右，访问 `https://<你的用户名>.github.io/<仓库名>/`。

用 git 命令的话：

```bash
git init
git add .
git commit -m "deploy wordweave"
git branch -M main
git remote add origin https://github.com/<你的用户名>/<仓库名>.git
git push -u origin main
```

仓库若命名为 `<用户名>.github.io`，访问地址就是 `https://<用户名>.github.io/`。

## 隐私

不收集、不上传任何数据。API Key、文章、生词本、词典缓存全部只存在使用者本机的 localStorage。换浏览器或换设备时，用页面里的「设置 → 备份与恢复」导出/导入 JSON 备份文件。
