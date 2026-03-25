# SVG Studio Export

中文 | [English](./README.md)

[![在线演示](https://img.shields.io/badge/demo-GitHub%20Pages-173149?logo=github&logoColor=white)](https://xujiantong.github.io/svg-studio-export/)
[![Pages 部署](https://github.com/xujiantong/svg-studio-export/actions/workflows/deploy-pages.yml/badge.svg)](https://github.com/xujiantong/svg-studio-export/actions/workflows/deploy-pages.yml)
[![许可证](https://img.shields.io/github/license/xujiantong/svg-studio-export?color=2f855a)](./LICENSE)
[![Star](https://img.shields.io/github/stars/xujiantong/svg-studio-export?style=flat&color=f59e0b)](https://github.com/xujiantong/svg-studio-export/stargazers)
[![最近提交](https://img.shields.io/github/last-commit/xujiantong/svg-studio-export?color=2563eb)](https://github.com/xujiantong/svg-studio-export/commits/main)
[![本地优先](https://img.shields.io/badge/local--first-浏览器原生渲染-ff7d40)](./index.html)

一个给设计师、内容编辑和前端工程师准备的本地优先 SVG 导出工具。

它不走系统缩略图，也不依赖粗糙的后端转换器，而是直接使用浏览器原生 SVG 渲染链路，把 SVG 画到 `Canvas` 再导出 PNG。对于很多“浏览器里正常、导出后跑版”的场景，这种方式通常更接近真实效果。

## 预览

![SVG Studio Export 预览](./assets/preview.png)

## 它能做什么

- 从本地导入一个或多个 SVG 文件
- 批量把 SVG 转成 PNG
- 用倍率、宽度或高度控制导出尺寸
- 选择保留透明背景，或填充自定义背景色
- 给导出文件统一加后缀
- 支持单张下载，也支持全部下载

## 为什么要做这个工具

很多 SVG 转 PNG 的问题，不是“不能转”，而是“转出来不像浏览器里看到的那张图”：

- 中文字体回退后，排版被挤乱
- 不同渲染器下字体和字重表现不一致
- `width`、`height`、`viewBox` 处理不一致，导致画布尺寸不对
- 预览正常，导出却变味

这个项目就是为这种真实工作流准备的：尽量用浏览器本身的渲染结果做导出，而不是再走一层不透明的转换器。

## 核心功能

### 本地优先

- 文件只在本地浏览器里处理
- 不上传服务器
- 纯静态 HTML，开箱即用

### 批量处理

- 支持多文件一次导入
- 支持一键批量转换
- 支持全部下载

### 导出控制

- 用 `1x` 到 `4x` 倍率直接放大
- 也可以手动指定宽度或高度
- 需要时可以关闭透明背景并填充背景色

### 命名规则

- 支持统一后缀，比如 `-export`

## GitHub Pages

仓库内已经带了 GitHub Pages 工作流：

- [`.github/workflows/deploy-pages.yml`](./.github/workflows/deploy-pages.yml)

如果仓库还没有启用 Pages，请确认仓库设置为：

- `Settings` -> `Pages` -> `Build and deployment` -> `Source` -> `GitHub Actions`

预期访问地址：

- [https://xujiantong.github.io/svg-studio-export/](https://xujiantong.github.io/svg-studio-export/)

## 本地启动

```bash
git clone git@github.com:xujiantong/svg-studio-export.git
cd svg-studio-export
python3 -m http.server 8765 --bind 127.0.0.1
```

然后打开：

```text
http://127.0.0.1:8765/
```

## 浏览器支持

- 最佳体验：Chromium 内核浏览器
- 现代桌面浏览器，只要支持 SVG 与 Canvas 即可使用

## 项目结构

```text
.
├── .github/workflows/deploy-pages.yml
├── assets/preview.png
├── index.html
├── LICENSE
├── README.md
└── README.zh-CN.md
```

## 后续可继续扩展

- 同时导出 WebP 和 JPG
- 检查 SVG 依赖字体并提示缺失
- 做成 Electron / Tauri 桌面版

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=xujiantong/svg-studio-export&type=Date)](https://star-history.com/#xujiantong/svg-studio-export&Date)

## 鸣谢

- Badge 使用了 [Shields.io](https://shields.io/)
- Star 趋势图使用了 [Star History](https://star-history.com/)

## License

[MIT](./LICENSE)
