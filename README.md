# 于兆海的个人博客

> 命运长河里挣扎的一条小鱼

个人博客，记录技术学习笔记与生活随想。

在线地址：<https://yuzhaohai.github.io/blog/>

## 技术栈

- **框架**：[Jekyll](https://jekyllrb.com/) + [Chirpy](https://github.com/cotes2020/jekyll-theme-chirpy) 主题
- **部署**：GitHub Pages + GitHub Actions（推送到 `main` 自动构建发布，站点挂载在 `/blog/` 子路径）

## 本地开发

```bash
bundle install          # 首次安装依赖
bundle exec jekyll s    # 启动本地服务 http://localhost:4000/blog/
```

## 目录说明

| 路径 | 说明 |
| --- | --- |
| `_posts/` | 博客文章（文件名格式 `YYYY-MM-DD-标题.md`） |
| `_tabs/` | 侧边栏页面（关于、归档、分类、标签等） |
| `_config.yml` | 站点配置（标题、头像、部署地址等） |
| `assets/img/` | 少量站内资源（头像、favicon） |

## 资源引用

- **图片图床**：文章图片存放在独立仓库 [resources](https://github.com/yuzhaohai/resources)，通过 jsDelivr CDN 引用：
  ```markdown
  ![图片](https://cdn.jsdelivr.net/gh/yuzhaohai/resources@main/poem/xxx.jpg)
  ```
  文章内通过 front matter 的 `media_subpath` 统一指定目录，正文直接写文件名即可。
- **静态工具页**：交互页面存放在独立仓库 [html](https://github.com/yuzhaohai/html)，通过 GitHub Pages 引用，例如 [JSON 树视图](https://yuzhaohai.github.io/html/awsome/json-tree.html)。

## 部署流程

1. 在 `_posts/` 下新增 Markdown 文章
2. `git add -A && git commit -m "..." && git push origin main`
3. GitHub Actions 自动构建并部署到 <https://yuzhaohai.github.io/blog/>
