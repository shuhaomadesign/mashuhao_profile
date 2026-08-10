# mashuhao_profile

Shuhao Ma 的个人学术网站。目前版本基于 Klein Blue 视觉概念，采用无依赖的静态 HTML，便于快速迭代并可直接发布到 GitHub Pages。

## 项目结构

```text
.
├── index.html              # 网站入口：结构、样式与交互
├── assets/
│   └── images/             # 肖像、项目图、文章配图等
├── docs/
│   └── EDITING_GUIDE.md    # 页面修改地图与协作约定
└── README.md
```

## 本地预览

直接打开 `index.html` 即可预览。若浏览器限制本地功能，可在项目目录运行：

```bash
python3 -m http.server 8000
```

然后访问 `http://localhost:8000`。

## 迭代原则

- 每次集中调整一个页面或一个共享组件。
- 全站颜色、尺寸与布局变量统一维护在 `index.html` 顶部的 `:root`。
- 页面内容按 `about`、`research`、`publications`、`service`、`collaboration` 五个 section 管理。
- 图片统一放入 `assets/images/`，页面中使用相对路径。
- 网站结构明显增大前继续保持轻量；只有在重复内容或页面数量显著增加时再引入构建工具。

详细说明见 [编辑指南](docs/EDITING_GUIDE.md)。

## 发布

仓库当前为 Private。网站准备发布时，可配置 GitHub Pages 或 GitHub Actions 自动部署。

