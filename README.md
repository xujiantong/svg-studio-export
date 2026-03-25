# SVG Studio Export

[中文说明](./README.zh-CN.md) | English

[![Live Demo](https://img.shields.io/badge/demo-GitHub%20Pages-173149?logo=github&logoColor=white)](https://xujiantong.github.io/svg-studio-export/)
[![Deploy Pages](https://github.com/xujiantong/svg-studio-export/actions/workflows/deploy-pages.yml/badge.svg)](https://github.com/xujiantong/svg-studio-export/actions/workflows/deploy-pages.yml)
[![License](https://img.shields.io/github/license/xujiantong/svg-studio-export?color=2f855a)](./LICENSE)
[![Stars](https://img.shields.io/github/stars/xujiantong/svg-studio-export?style=flat&color=f59e0b)](https://github.com/xujiantong/svg-studio-export/stargazers)
[![Last Commit](https://img.shields.io/github/last-commit/xujiantong/svg-studio-export?color=2563eb)](https://github.com/xujiantong/svg-studio-export/commits/main)
[![Local First](https://img.shields.io/badge/local--first-browser%20rendered-ff7d40)](./index.html)

Local-first SVG to PNG export for designers and frontend engineers.

Instead of relying on lossy system converters, SVG Studio Export uses the browser's native SVG rendering path and exports PNG from `Image + Canvas`, which is usually much closer to what you actually see in Chromium.

## Preview

![SVG Studio Export preview](./assets/preview.png)

## What It Does

- Import one or more SVG files from your machine.
- Batch convert SVG to PNG with browser-native rendering.
- Adjust export size with scale, width, or height.
- Keep transparency or export with a solid background color.
- Add a shared suffix to exported file names.
- Download generated PNG files one by one or all at once.

## Why This Exists

If you have ever converted SVG with `sips`, Quick Look, or a generic backend library, you have probably seen at least one of these:

- Chinese text fallback changing the layout
- font rendering drifting away from the browser version
- wrong canvas size from incomplete `width`, `height`, or `viewBox` handling
- exported preview looking different from the actual SVG opened in Chrome

This project is built for the common case where you want a practical, local, browser-based export tool that stays visually close to the original SVG.

## Features

### Local-first conversion

- Files stay on your machine.
- No upload step.
- Works as a static HTML tool.

### Batch workflow

- Import multiple SVG files in one pass.
- Convert all files together.
- Download all generated PNG files at once.

### Export controls

- Scale with preset multipliers from `1x` to `4x`
- Override width or height manually
- Preserve transparent backgrounds
- Fill the background with a custom color when needed

### Naming

- Add a shared export suffix such as `-export`

## GitHub Pages

This repository includes a GitHub Pages workflow at [`.github/workflows/deploy-pages.yml`](./.github/workflows/deploy-pages.yml).

If Pages is not already active for the repository, make sure the repository setting is:

- `Settings` -> `Pages` -> `Build and deployment` -> `Source` -> `GitHub Actions`

The live URL is expected to be:

- [https://xujiantong.github.io/svg-studio-export/](https://xujiantong.github.io/svg-studio-export/)

## Quick Start

Clone the repo and open the tool locally:

```bash
git clone git@github.com:xujiantong/svg-studio-export.git
cd svg-studio-export
python3 -m http.server 8765 --bind 127.0.0.1
```

Then open:

```text
http://127.0.0.1:8765/
```

## Browser Support

- Best experience: Chromium-based browsers
- Works in modern desktop browsers with SVG and Canvas support

## Project Structure

```text
.
├── .github/workflows/deploy-pages.yml
├── assets/preview.png
├── index.html
├── LICENSE
├── README.md
└── README.zh-CN.md
```

## Roadmap

- Export WebP and JPG alongside PNG
- Add better font diagnostics
- Add a desktop build with Electron or Tauri

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=xujiantong/svg-studio-export&type=Date)](https://star-history.com/#xujiantong/svg-studio-export&Date)

## Credits

- Badges powered by [Shields.io](https://shields.io/)
- Star chart powered by [Star History](https://star-history.com/)

## License

[MIT](./LICENSE)
