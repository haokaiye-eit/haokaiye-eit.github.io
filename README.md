# 叶镐恺个人主页

仓库：[haokaiye-eit/haokaiye-eit.github.io](https://github.com/haokaiye-eit/haokaiye-eit.github.io)。网站地址：[haokaiye-eit.github.io](https://haokaiye-eit.github.io/)。

叶镐恺，宁波东方理工大学力学与机械工程学院 2025 级本科生（创校首届）。本网站基于 [ShengqiZhangEIT/shengqizhangEIT.github.io](https://github.com/ShengqiZhangEIT/shengqizhangEIT.github.io) 的模板改造，原模板源自 [JackYansongLi/shiyi-chen-web](https://github.com/JackYansongLi/shiyi-chen-web)。

英文首页直接位于 `/`，其他英文页面使用 `/biography/`、`/research/`、`/publications/`、`/projects/`、`/activities/`；中文页面位于 `/zh/` 及其子路径。页面地址均使用目录形式，不显示 `.html`。

## 本地预览

建议使用 Python 3.12 或更新版本。在仓库根目录运行：

```powershell
python build.py --site-url=
python scripts/check_site.py --site-url=
python -m http.server 8000 --directory dist
```

打开 <http://localhost:8000/>，按 `Ctrl+C` 停止服务。`--site-url=` 将本次构建的发布网址设为空，适合在本机根路径预览。

正式构建使用 `data/site.json` 中配置的 Pages 网址：

```powershell
python build.py
```

生成器更新根目录、`zh/` 及各页面目录下的 `index.html`，同时生成供发布使用的 `dist/`。`dist/` 已被 Git 忽略；工作流在 GitHub 重新构建，无需上传。

## 内容维护

网站以 `data/` 为内容维护入口，不直接修改生成的 HTML：

| 文件 | 用途 |
| --- | --- |
| `data/profile.json` | 中英文个人资料、教育经历、项目与学术活动 |
| `data/publications.json` | 论文数据来源（暂无论文时保持为 `[]`） |
| `data/research.json` | 研究方向及相关论文 ID（暂无内容时保持为 `[]`） |
| `data/site.json` | 正式网址、仓库网址、学术主页链接、内容年份及代表论文 ID |
| `build.py` | 页面布局与中英文呈现逻辑 |
| `assets/` | 样式、交互脚本与字体 |
| `images/portrait.jpg` | 本人肖像（当前为占位图，替换为同名文件即可） |
| `files/cv-zh.pdf`、`files/cv-en.pdf` | 中文、英文简历下载文件（放入后构建会自动显示下载链接） |
| `files/papers/` | 论文全文（有论文后放入，并在 `data/publications.json` 用 `pdf` 字段指向） |

更新 JSON 或下载文件后重新构建并执行检查。论文、项目、荣誉等栏目为空时页面会显示占位说明，添加内容后自动出现。

## GitHub Pages 发布

远端为 `origin`：`git@github.com:haokaiye-eit/haokaiye-eit.github.io.git`。向 `main` 推送后，GitHub Actions 工作流会自动构建并部署到 <https://haokaiye-eit.github.io/>。

```powershell
git add .
git commit -m "Update Haokai Ye personal website"
git push origin main
```

仓库需保持 `haokaiye-eit.github.io` 名称并置于 `haokaiye-eit` 账号下，Pages 来源选择 **GitHub Actions**。

## 资源来源

模板设计资源来自上述参考仓库，原仓库未提供明确的代码许可证。字体位于 `assets/fonts/`，许可文本为 `OFL-Raleway.txt` 与 `OFL-SourceSans.txt`。
