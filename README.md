# ututx.github.io

个人主页源码，由 GitHub Pages 托管发布。

站点地址：<https://ututx.github.io/>

纯静态站点：手写 HTML + CSS，没有框架，也没有构建步骤，克隆下来就能改。

## 页面内容

首页 `index.html` 分四块：

- **hero**：头像、一句话简介，以及 GitHub、macOS-DroidVM 两个入口
- **关于**：在 macOS on DroidVM 方向上的尝试，涉及 UEFI 引导链（UniXNU / DarwinBoot）、设备树（ADT / FDT）、crosvm 与 Gunyah 虚拟化，以及 `.vmpkg` 镜像打包
- **项目**：macOS-DroidVM、vmpkg 工具、本仓库三张卡片
- **笔记**：指向 macOS-DroidVM 仓库里的说明文档

## 目录结构

```
.
├── index.html                  # 首页，全部内容都在这里
├── styles.css                  # 全部样式
├── images/
│   └── create-octocat.png      # 头像
├── README.md                   # 中文说明（本文件）
└── README.en.md                # English README
```

没有 `package.json`、没有构建产物，`git push` 之后 GitHub Pages 直接发布源文件。

## 本地预览

```bash
python3 -m http.server 8000
# 然后打开 http://localhost:8000
```

只改样式的话，直接双击 `index.html` 也能看——站内引用全是相对路径。

## 改哪里

- **配色**：`styles.css` 顶部的 `:root` 变量（`--bg`、`--accent` 等），改一处全站生效
- **文案**：`index.html` 里对应的 `<section>`
- **窄屏**：`styles.css` 末尾的 `@media (max-width: 480px)`
- **页脚年份**：页面底部一小段内联脚本按访问时间写入 `<span id="year">`；HTML 里写死的 `2026` 是脚本被禁用时的兜底值

## 部署

仓库 `master` 分支根目录直接作为 Pages 源，推送到 `master` 后 GitHub 自动重建，通常一分钟内生效。

站点是纯静态文件，不需要 GitHub Actions。注意：免费账号的 GitHub Pages 要求仓库是公开的。

## 相关仓库

- [macOS-DroidVM](https://github.com/ututx/macOS-DroidVM) — 在 DroidVM 里运行 macOS 的镜像构建与引导链调试
- [UniXNU-droidvm](https://github.com/Droid-VM/UniXNU-droidvm) — DroidVM 客户机的 UniXNU 设备仓库（设备树与引导链）
