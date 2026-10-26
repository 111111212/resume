# 在线简历 · 王成强

Java 后端开发（AI 应用 / Agent 方向）单页简历，纯静态，零外部依赖。

## 文件

| 文件 | 说明 |
| --- | --- |
| `index.html` | 简历主页（响应式 + 打印样式） |
| `resume.pdf` | 原版 PDF 简历，页面右上角「PDF 简历」按钮指向它 |
| `.nojekyll` | 告诉 GitHub Pages 跳过 Jekyll 处理（必须保留，否则以 `_` 开头的文件会被忽略） |

## 本地预览

直接双击 `index.html` 即可；或在本目录执行：

```bash
python -m http.server 8000
# 打开 http://localhost:8000
```

## 部署到 GitHub Pages

### 方式一：命令行（已配置好 GitHub 凭据时）

```bash
cd resume-site
git init -b main
git add -A
git commit -m "chore: 初始化在线简历"
git remote add origin https://github.com/111111212/resume.git
git push -u origin main
```

推送后在仓库 **Settings → Pages → Build and deployment**：

- Source 选 `Deploy from a branch`
- Branch 选 `main`，目录选 `/ (root)`
- 保存，1～2 分钟后访问 `https://111111212.github.io/resume/`

### 方式二：网页上传

在 GitHub 新建一个 **Public** 仓库 `resume` → 点 `uploading an existing file` → 把本目录三个文件拖进去 → 提交 → 再按上面步骤开启 Pages。

## 注意

- GitHub Pages 免费额度**只对公开仓库开放**。本页含手机号与邮箱，仓库公开即代表这些信息全网可检索、可被爬虫抓取。若不希望暴露，可在 `index.html` 的 `.contact` 区块删掉手机号，或把手机号改成脱敏写法。
- 自定义域名与 HTTPS 均免费；绑定自有域名时在仓库 Settings → Pages 填写，并在 DNS 加 CNAME / A 记录。
