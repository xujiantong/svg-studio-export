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

- 单张导入 SVG，也支持整文件夹导入
- 批量把 SVG 转成 PNG
- 左右对比原始 SVG 和导出 PNG
- 套用公众号封面、文章配图、16:9 等尺寸预设
- 按前缀、后缀、递增编号统一命名
- 自动处理同名文件，避免输出覆盖
- 一键打包成 ZIP 下载
- 在支持的浏览器里直接写入指定输出目录
- 当你修改导出参数后，自动把旧图标记为“需重转”

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

- 支持目录扫描和嵌套 SVG 导入
- 支持一键批量转换
- 支持 ZIP 打包下载

### 命名规则

- 统一前缀
- 统一后缀
- 递增编号
- 自动避免重名覆盖

### 对比预览

- 左边看原始 SVG
- 右边看导出 PNG
- 能更快发现字体回退、间距漂移、缩放异常

### 导出预设

- 公众号封面 `900 × 383`
- 文章配图 `1080 × 608`
- 16:9 `1200 × 675`
- Full HD `1920 × 1080`

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
- 文件夹导入：现代 Chromium 浏览器支持较好，也带 `webkitdirectory` 兜底
- 写入目录：依赖 File System Access API

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
- 拖拽排序导出顺序
- 检查 SVG 依赖字体并提示缺失
- 做成 Electron / Tauri 桌面版
- 增加文件夹监听自动转换

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=xujiantong/svg-studio-export&type=Date)](https://star-history.com/#xujiantong/svg-studio-export&Date)

## 鸣谢

- Badge 使用了 [Shields.io](https://shields.io/)
- Star 趋势图使用了 [Star History](https://star-history.com/)

## License

[MIT](./LICENSE)
