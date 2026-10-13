# My Blog

基于 Hugo + PaperMod 的个人博客，部署在 GitHub Pages。

线上地址：https://cata-3.github.io/myblog/

## 本地开发

hugo server --buildDrafts --disableFastRender

浏览器打开 http://127.0.0.1:1313/myblog/

## 写新文章

hugo new content/posts/文章名.md

编辑 content/posts/文章名.md，记得 draft: false 才会发布。

## 发布

git add .
git commit -m "描述改了什么"
git push

GitHub Actions 会自动构建部署，1-2 分钟后线上生效。

## 目录结构

- content/posts/ — 博客文章
- content/notes/ — 学习笔记（含 PDF）
- content/about.md — 关于页
- layouts/ — 自定义模板
- layouts/_shortcodes/pdf.html — PDF 嵌入短代码
- layouts/_partials/post_history.html — 文章 commit 历史
- layouts/_partials/comments.html — Giscus 评论
- static/pdfjs/ — PDF.js 阅读器
- scripts/pre-commit — git hook 备份

## 新电脑恢复

git clone https://github.com/Cata-3/myblog.git
cd myblog
git submodule update --init --recursive
cp scripts/pre-commit .git/hooks/pre-commit
chmod +x .git/hooks/pre-commit

## PDF 笔记

在笔记目录下放 PDF 和 index.md，index.md 里写：

{{< pdf "文件名.pdf" >}}

## 评论

Giscus，基于 GitHub Discussions。

## 统计

- 页面浏览数：vercount
- 后台流量：GoatCounter（https://cata3.goatcounter.com）
