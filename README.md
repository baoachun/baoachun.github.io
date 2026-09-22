# Achun Bao

个人学术主页，展示研究方向、教育与工作经历、技能、论文、博客和生活照片。

网站地址：[baoachun.github.io](https://baoachun.github.io/)

## 页面

- **Home · Sidebar**：左侧个人信息、右侧正文（`index.html`）。
- **Home · Classic**：顶部个人信息、下方正文（`classic.html`，访问路径 `/classic/`）。
- **Publications**：论文列表。
- **Blog**：博客文章。
- **Showcase**：照片轮播、生活相册和 Cats。

## 本地运行

需要 Ruby 和 Bundler。在包含 `Gemfile` 的项目根目录运行：

```bash
bundle install --path vendor/bundle
bundle exec jekyll serve
```

打开终端显示的预览地址，默认是 http://localhost:4000/。按 `Ctrl+C` 停止服务。
一般内容修改后会自动重新生成；修改 `_config.yml` 后需要重启服务。

当前项目保留了适配 Ruby 2.6 的 ffi 版本限制。`vendor/`、`.bundle/` 和 `_site/` 不纳入版本控制。

## 修改内容

| 内容 | 文件或目录 |
| --- | --- |
| 姓名、简介、联系方式、教育、工作、奖项、技能 | `_data/profile.yml` |
| 导航名称和链接 | `_data/navigation.yml` |
| 首页模块显示开关和页脚 | `_data/display.yml` |
| 论文条目 | `_publications/` |
| 论文作者显示设置 | `_data/authors.yml` |
| 博客文章 | `_posts/` |
| 相册卡片 | `_showcase/` |
| 轮播照片 | `_showcase/default/photo_collection.md` |
| 生活照片 | `assets/images/etc/` |
| 头像 | `assets/images/photos/portrait.jpg` |
| 学校图标 | `assets/images/badges/` |
| 公共样式 | `assets/css/global.css` |
| 页面组件 | `_includes/widgets/` |

博客文件使用 `YYYY-MM-DD-title.md` 命名，包含 `layout: blog_post`、`title` 和 `date`。
Showcase 条目通过 `show` 控制显示，`group` 设置分组，`width` 设置卡片宽度。

## 构建与发布

```bash
bundle exec jekyll build
```

静态文件生成到 `_site/`。提交源文件并推送到 GitHub 后，由仓库配置的 GitHub Pages 发布方式部署。
本仓库用于用户主页，`_config.yml` 中保持 `baseurl: ""`。

## 致谢与许可证

基于 [Shitong Luo 的 academic-homepage 模板](https://github.com/luost26/academic-homepage) 修改，保留原模板的 [MIT 许可证](LICENSE)。

## 访问统计

使用 GoatCounter 统计访客和页面浏览量，后台：https://achunbao.goatcounter.com/ 。
统计地址在 `_config.yml` 的 `goatcounter` 中配置，共用代码位于 `_includes/analytics.html`。
仅生产构建加载统计脚本，普通本地预览不会发送访问记录。
GitHub Pages 的生产构建会启用统计；自行构建发布时使用：

```bash
JEKYLL_ENV=production bundle exec jekyll build
```

页脚显示全站累计浏览量（不是去重人数）。需在 GoatCounter 站点设置中开启
“Allow adding visitor counts on your website”。计数可能缓存最多四小时；
未启用或请求失败时显示 `—`。本地预览会读取线上计数，但不会增加访问记录。
