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

- GitHub Pages 免费额度**只对公开仓库开放**，仓库公开即代表页面内容全网可检索、可被爬虫抓取。
- **手机号已脱敏**：页面与 PDF 中均显示为 `176****5265`，明文号码不出现在任何会被提交的文件里（PDF 的文本层也已彻底擦除，无法用复制或 `pdftotext` 提取）。网页上点击该胶囊按钮时，才由脚本还原号码并唤起拨号；PDF 中则需对方主动向你索取。
- 本目录下的 `resume.original.bak` 是**未脱敏的原始 PDF 备份**，已写入 `.gitignore`，不会被提交——手动上传文件到 GitHub 时注意不要把它一起拖进去。
- 邮箱 `895040369@qq.com` 保持明文，作为对外主要联系方式。
- 自定义域名与 HTTPS 均免费；绑定自有域名时在仓库 Settings → Pages 填写，并在 DNS 加 CNAME / A 记录。
