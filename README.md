# AEE-Lab · Minimal Mistakes

这是 AEE-Lab（汽车能源电子实验室）的独立 GitHub Pages 网站源码，使用原版 [Minimal Mistakes 4.28.1](https://github.com/mmistakes/minimal-mistakes/tree/4.28.1) 主题。原有网站工程未被修改。

网站包含实验室简介、研究方向、团队成员、项目实践、论文成果、实验室动态及联系方式。已有公开基本资料与实验室 Logo 已沿用，尚未提供的内容保留空栏目，不编造成员、论文或动态。

## 日常更新

在 GitHub 仓库里打开对应文件，点击铅笔按钮编辑，完成后点击 **Commit changes** 保存。GitHub Pages 构建成功后，网页才会更新，通常需要等待片刻。建议先检查文字与文件，再提交。

| 要修改的内容 | 文件或目录 |
| --- | --- |
| 网站名称、页眉、副标题、侧栏简介 | `_config.yml` |
| 实验室介绍、联系方式、研究方向 | `_data/lab.yml` |
| 顶部导航 | `_data/navigation.yml` |
| 团队成员 | `_data/members.yml` |
| 项目实践 | `_data/projects.yml` |
| 论文成果 | `_data/publications.yml` |
| 新动态、文章 | `_posts/` |
| 图片 | `assets/images/` |
| 论文 PDF | `assets/pdf/` |
| 首页结构 | `index.html` |
| 各栏目页正文 | `_pages/` |
| 配色、字体与间距 | `assets/css/main.scss` |

`_config.yml` 的侧栏和页脚邮箱为主题设置；如果更换联系邮箱，请同时修改 `_data/lab.yml` 里的邮箱和 `_config.yml` 的 `mailto:` 链接。首页和联系页自动读取 `_data/lab.yml`，无需重复填写。

### 写一篇动态

在 `_posts/` 新建文件，例如 `2026-11-06-lab-news.md`。文件名必须是 `年-月-日-英文短名.md`，日期改为实际发布日期。内容格式如下（只是示例，网站不会预先发布）：

```markdown
---
title: "填写这篇动态的真实标题"
date: 2026-11-06 10:00:00 +0800
categories:
  - 实验室动态
tags:
  - 嵌入式
excerpt: "一句话摘要。"
---

在这里写正文。支持段落、标题、列表和链接。

![图片说明]({{ '/assets/images/news/example.jpg' | relative_url }})
```

先上传真实图片，再将图片路径替换为自己的文件。上面的 `relative_url` 写法可兼容仓库子路径。图片和 PDF 建议使用简短的英文文件名，避免超大文件。

### 填写成员、项目和论文

对应 `_data/*.yml` 文件顶部有格式示例。添加第一条记录时，删除最后单独一行的 `[]`，取消示例的注释，再替换成真实资料。缩进使用空格，不要用 Tab；含有冒号等符号的文字可用英文双引号包起来。

成员资料支持姓名、身份、分类、研究方向、简介、照片、状态及毕业年份。分类按文件中的出现顺序展示，可将已毕业成员的 `category` 设为“毕业成员”。成员照片、项目图片和论文 PDF 均使用 `assets/` 中的公开文件路径。

### 网站能力

这是静态网站，没有 Halo 那样的独立账号后台和“保存并发布”管理页面。日常通过 GitHub 编辑 Markdown / YAML 文件、上传附件并提交更新。访客不需要 GitHub 账号即可浏览；网站维护者需要仓库编辑权限。

## 发布到 GitHub Pages

源码准备完成不等于已经上线。发布后才会有你的正式访问地址。

1. 使用 **fzu-aee-lab** 组织下的 **fzu-aee-lab.github.io** 公开仓库，默认分支为 **main**。
2. 上传本目录中的网站源码，保留隐藏的 `.github` 目录及其中的 `workflows/pages.yml`。不要上传 `_site`、`vendor`、原网站的数据库、备份 JSON、账号资料或密钥。
3. 在 **Settings → Pages → Build and deployment → Source** 中选择 **GitHub Actions**。
4. 检查 **Actions** 中构建和部署是否成功。正式网址以仓库 **Settings → Pages** 显示的地址为准。
5. 部署成功后，打开 `https://fzu-aee-lab.github.io/`。这是组织的根站点，`_config.yml` 中的 `baseurl` 保持为空。

## 本地预览

安装与 `Gemfile` 匹配的 Ruby 和 Bundler 后，在本目录执行：

```text
bundle install
bundle exec jekyll serve
```

打开终端给出的本地地址即可。没有 Ruby 的电脑可直接使用 GitHub Pages 云端构建，但提交前仍应检查 YAML 格式和所有公开资料。

## 上线前核对

请阅读 `发布前检查.md`。目前已有成员记录包含明显的测试文字，因此未放入公开成员列表；请核对真实姓名、身份、照片及简介后手动补充。旧系统中引用的上传图片当前未随迁移目录提供，未发布失效链接。

主题来源和许可证见 `THEME-LICENSE.txt`。实验室文字与图片应由有权发布的人维护。
