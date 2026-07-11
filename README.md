# Ding Shi / 石丁 — Academic Homepage Framework

这是 Ding Shi / 石丁 的个人学术主页框架，计划部署到 <https://stonfur.github.io>。

本项目基于开源 GitHub Pages 个人学术主页项目改造，主要 HTML 布局与视觉基础来自 [ShuaifeiChen273/ShuaifeiChen273.github.io](https://github.com/shuaifeichen273/shuaifeichen273.github.io)：沿用 Jemdoc 风格的左侧分类导航、右侧正文、资料表格、蓝色标题线与紧凑列表。论文的 Journal / Conference 分类和专利的分组组织参考 [liyouSEU/liyouSEU.github.io](https://github.com/liyouseu/liyouseu.github.io)。原项目的 GPL-3.0 `LICENSE` 已保留。

当前版本只搭建框架。个人简介、论文、专利、奖励、项目、经历、新闻和学术服务均为 `TODO`，需要由主页所有者填写；项目中不包含参考主页作者的个人数据、照片或学术成果。

## 页面结构

```text
.
├── index.html               # 首页与个人信息
├── publications.html        # 论文：Selected / Journal / Conference
├── patents.html             # 专利：已授权 / 申请中
├── projects.html            # 项目
├── awards.html              # 奖励与荣誉
├── services.html            # 学术服务
├── assets/
│   ├── css/style.css        # 全站样式
│   └── img/README.md        # 头像放置说明
├── .nojekyll                # 禁用 Jekyll 处理
├── LICENSE                  # 原项目 GPL-3.0 许可证
└── README.md
```

## 修改首页信息

打开 `index.html`，搜索 `TODO` 并替换 Title、Affiliation、Email、学术主页链接、英文简介、中文简介、研究兴趣、新闻、经历和奖励。保留不需要立即填写的项目为 `TODO` 即可。

## 添加论文

在 `publications.html` 对应的 Selected Publications、Journal Papers 或 Conference Papers 列表中复制一个 `<li>` 模板并替换内容。需要突出主页作者时，可在作者列表中写成 `<strong>Ding Shi</strong>`。首页的 Selected Publications 使用同一模板。

未提供的 PDF、DOI、Code 或 Slides 链接可以先删除；不要长期保留 `href="#"` 占位链接。

## 添加专利

在 `patents.html` 的“已授权专利”或“申请中专利”列表中复制条目模板，填写专利名称、发明人、专利号或申请号、状态和年份。

## 添加项目

在 `projects.html` 中复制一个 `<div class="item">` 区块，填写项目名称、角色、资助来源、时间和简介。

## 添加奖励

在 `awards.html` 的列表中复制一个 `<li>` 条目，填写年份、奖励名称和授奖单位。

## 替换头像

将自己的照片命名为 `profile.jpg`，放到 `assets/img/`。建议使用方形或接近方形的照片；页面会自动裁切并适配移动端。仓库当前不提供虚构头像，也不包含他人的照片。

## 本地预览

项目无需构建工具。可以直接打开 `index.html`，也可以在项目根目录启动本地服务器：

```bash
python -m http.server 8000
```

然后访问 <http://localhost:8000>。

## 部署到 GitHub Pages

1. 确保 GitHub 仓库名为 `stonfur.github.io`。
2. 将这些文件提交并推送到仓库默认分支（通常为 `main`）。
3. 在仓库 **Settings → Pages** 中确认发布源为默认分支的仓库根目录。
4. 等待 GitHub Pages 发布后访问 <https://stonfur.github.io>。

如果本地已配置本仓库的 `origin`，首次发布可运行：

```bash
git push -u origin main
```

推送前请先确认远端仓库为空或只包含可以安全合并的内容，切勿覆盖已有非空仓库。

## 技术说明

- 纯静态 HTML + CSS，无 React、Vue、Next.js、Jekyll 或其他构建依赖。
- 不使用外部字体、CSS、CDN、统计脚本或追踪脚本。
- 全站只有一套中英混排页面，不包含 `/zh/` 目录或语言切换。
