# 主题升级指南

本博客基于 [jekyll-theme-chirpy](https://github.com/cotes2020/jekyll-theme-chirpy) 完整安装方式（方式B），通过 git remote 跟踪上游主题更新。

## 远程仓库配置

- `origin` → 你的博客仓库 (https://github.com/Vince-cyh/Blog.git)
- `upstream` → Chirpy 主题上游 (https://github.com/cotes2020/jekyll-theme-chirpy.git)

## 升级步骤

1. 获取上游最新代码：
   ```bash
   git fetch upstream
   ```

2. 使用 squash merge 将上游更新合并到你的 main 分支：
   ```bash
   git merge --squash upstream/main
   ```

3. 解决冲突（如果有），特别注意以下自定义文件的冲突：
   - `_config.yml` — 个人配置
   - `_data/links.yml` — 友情链接
   - `_data/contact.yml` — 联系方式
   - `_data/share.yml` — 分享平台
   - `_includes/friend-links.html` — 友情链接组件
   - `_layouts/default.html` — 友链面板插入点
   - `_data/locales/zh-CN.yml` — 中文本地化
   - `_data/locales/en.yml` — 英文本地化
   - `_tabs/about.md` — 关于页面
   - `.github/workflows/pages-deploy.yml` — 部署工作流

4. 提交并推送：
   ```bash
   git commit -m "chore: upgrade chirpy theme to latest"
   git push origin main
   ```

## 自定义清单

升级时需要保留的自定义内容：
1. 友情链接面板（friend-links.html + links.yml + default.html）
2. Giscus 评论配置（_config.yml 中 comments.giscus）
3. PWA 配置（_config.yml 中 pwa）
4. 分享平台（_data/share.yml）
5. 联系方式（_data/contact.yml）
6. 关于页面（_tabs/about.md）
7. GitHub Actions 部署（.github/workflows/pages-deploy.yml）
8. 中英双语国际化键（locales 中的 friend_links）
