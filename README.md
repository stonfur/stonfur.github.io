# Ding Shi / 石丁 — Academic Homepage Framework

这是 Ding Shi / 石丁 的个人学术主页框架，计划部署到 <https://stonfur.github.io>。

本项目基于开源 GitHub Pages 个人学术主页项目改造，主要 HTML 布局与视觉基础来自 [ShuaifeiChen273/ShuaifeiChen273.github.io](https://github.com/shuaifeichen273/shuaifeichen273.github.io)：沿用 Jemdoc 风格的左侧分类导航、右侧正文、资料表格、蓝色标题线与紧凑列表。论文的 Journal / Conference 分类和专利的分组组织参考 [liyouSEU/liyouSEU.github.io](https://github.com/liyouseu/liyouseu.github.io)。原项目的 GPL-3.0 `LICENSE` 已保留。

当前版本已根据“成果整理”材料填入 17 篇已发表期刊论文、12 篇会议论文、15 项中国发明专利、1 项已收到授权通知的美国发明专利申请和 3 项主持项目，并已补充证件照、联系方式、中英文个人简介、学术经历、博士学位论文和奖励。29 篇论文及博士学位论文的全文 PDF 存放在 `paper/` 目录；论文题目和学位论文题目可直接点击查看全文，通讯作者以姓名右上角 `*` 标注。在审论文和在审专利按要求不展示，首页不设置 News、Research Interests 或 Awards and Honors 区块。项目中不包含参考主页作者的个人数据、照片或学术成果。

## 页面结构

```text
.
├── index.html               # 首页与个人信息
├── publications.html        # 论文：Journal / Conference，按时间倒序连续编号
├── patents.html             # 专利：中国专利 / 外国专利
├── projects.html            # 项目
├── awards.html              # 奖励与荣誉
├── paper/                   # 论文全文 PDF 与博士学位论文 PDF
├── assets/
│   ├── css/style.css        # 全站样式
│   └── img/
│       ├── profile.jpg      # 首页证件照
│       └── README.md        # 头像替换说明
├── .nojekyll                # 禁用 Jekyll 处理
├── LICENSE                  # 原项目 GPL-3.0 许可证
└── README.md
```

## 修改首页信息

打开 `index.html` 可修改姓名、职称、单位、邮箱、学术主页链接、地址和新闻。首页中英文简介、Academic Experiences（含博士学位论文全文链接）与 Research Projects 已经填写，Research Interests 和 Awards and Honors 区块已按要求删除。保留暂时无法确认的新闻为 `TODO` 即可。

## 添加论文

在 `publications.html` 的 Journal Papers 或 Conference Papers 单一列表中复制一个 `<li>` 条目并替换内容。论文按出版时间倒序排列，显示编号从列表底部的 `[J1]`、`[C1]` 开始向上连续递增。需要突出主页作者时，作者列表使用 `<strong>D. Shi</strong>`；在每位通讯作者姓名后添加 `<sup class="corresponding-marker">*</sup>`，共同通讯作者均需标注。全文 PDF 放入 `paper/` 目录，并将论文题目包裹为指向该 PDF 的链接；不展示 WOS 或 EI 检索号。Google Scholar 主页链接放在论文页标题之后。

未提供的 DOI、Code 或 Slides 链接可以先删除；不要长期保留 `href="#"` 占位链接。

## 添加专利

在 `patents.html` 的“中国专利”或“外国专利”列表中复制一个 `<li>` 条目，填写专利名称、发明人、专利号以及申请、授权日期，并保留条目前的 `[P#]` 或 `[F#]` 编号。中国专利按授权时间倒序排列，不按年份分组；在审专利不展示。

## 添加项目

在 `projects.html` 的 `<ul>` 中复制一个 `<li>` 条目，按“起止时间、角色、项目名称、资助计划、项目编号、经费”的顺序填写；资助计划名称使用 `<span class="project-program">...</span>` 显示为黑色加粗斜体，首页的 Research Projects 使用相同格式。

## 添加奖励

在 `awards.html` 的列表中复制一个 `<li>` 条目，第一行填写时间与英文奖励名称，第二行填写中文名称。

## 替换头像

当前证件照位于 `assets/img/profile.jpg`。替换时沿用该文件名；页面会保持原图纵横比例并适配移动端，不进行裁切。

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
