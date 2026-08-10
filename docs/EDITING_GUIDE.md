# 网站编辑指南

这份指南用于后续逐页调整设计与内容时，快速定位修改范围并减少对其他页面的影响。

## 页面修改地图

| 页面 | HTML 区块 | 专属样式关键词 | 主要内容 |
| --- | --- | --- | --- |
| About Me | `#about` | `.about-*`、`.news-*`、`.statement` | 个人简介、研究议题、最新学术动态 |
| Research | `#research` | `.research-*`、`.featured`、`.project` | 研究方向、重点项目 |
| Publications | `#publications` | `.pub-*` | 论文年份、题目、作者、链接 |
| Service | `#service` | `.practice`、`.mini-list` | 教学、研究与学术服务 |
| Collaboration | `#collaboration` | `.collab-*` | 指导意向、合作方向、联系入口 |

固定侧栏位于 `.identity`，包含肖像、职位、地点、邮箱和外部平台链接。顶部导航位于 `.site-nav`。

## 推荐修改方式

1. 内容调整只修改对应 `<section>`，不要复制整个页面。
2. 页面特有视觉调整优先放在对应的 CSS 注释区中。
3. 颜色、导航高度、侧栏宽度等全局值只在 `:root` 中修改。
4. 可复用的卡片和按钮优先扩展现有 class，避免为相同样式创建多个版本。
5. 新增页面时同步更新：顶部导航、`PAGE_IDS` 数组、页面 section 和移动端响应式样式。

## 素材约定

- 肖像：`assets/images/portrait.*`
- 项目图片：`assets/images/projects/<project-name>.*`
- 论文或活动图片：`assets/images/publications/` 或 `assets/images/service/`
- 文件名使用小写英文和连字符，例如 `responsible-automation-cover.webp`。
- 网页照片优先使用 WebP，并保留合理尺寸，避免直接上传超大原图。

## Git 工作流

- 一个明确的页面调整对应一个提交，例如 `design: refine research page`。
- 内容更新和大范围视觉改版尽量分开提交，方便比较和回退。
- 每次推送前检查桌面与手机布局、导航、外部链接和键盘操作。
- `main` 始终保留可预览版本；需要探索多个方案时再创建独立分支。

## 何时拆分文件或引入框架

当前单文件结构适合这版五区块单页网站：打开即可预览，也可直接交给 GitHub Pages。出现以下情况时再拆分：

- 增加独立项目详情页或文章页；
- 页面内容开始从多个位置重复引用；
- 需要自动生成论文列表、博客或多语言内容；
- 需要统一构建、图片优化或持续部署。

届时可迁移到 Astro 等静态站点生成器，并保留当前设计 token、语义结构和素材路径。
