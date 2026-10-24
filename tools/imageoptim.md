---
type: Tool
title: ImageOptim
description: Free, open-source Mac app that makes JPEG, PNG, SVG and GIF files smaller and strips private metadata such as GPS location.
resource: https://imageoptim.com/mac
tags:
  - images
  - web
  - macos
  - open-source
platforms:
  - macOS
license: GPL-2.0-or-later
pricing: Free
sources:
  - id: imageoptim
    resource: https://imageoptim.com/mac
    title: ImageOptim for Mac
  - id: packages
    resource: https://formulae.brew.sh/cask/imageoptim
    title: "Homebrew: imageoptim; GitHub: ImageOptim/ImageOptim"
---
# ImageOptim

A free, open-source Mac app that makes image files smaller. Drop JPEG, PNG, SVG or animated GIF files on it and it recompresses them in place. It's licensed under GPL v2 or later and needs macOS 11 or later.[^imageoptim]

- **Lossless by default:** files get smaller without changing how they look. Turn on lossy minification for JPEG, SVG, GIF and PNG to get smaller files at some cost in quality.[^imageoptim]
- **Removes metadata:** EXIF data such as GPS position and camera serial number, embedded thumbnails, comments and unneeded colour profiles. You can keep JPEG metadata in Preferences.[^imageoptim]
- **Bundled optimisers:** MozJPEG, pngquant, Pngcrush, 7zip, SVGO and Google Zopfli, plus PNGOUT, which isn't GPL-licensed.[^imageoptim]
- **Other ways to run it:** from the command line, from Sketch, from the Finder's Services menu, or by dropping files on its Dock icon. There's also a separate web service and API.[^imageoptim]

## Install

```sh
brew install --cask imageoptim
```

On 2026-10-24 Homebrew had 1.9.3, and the cask updates itself.[^packages] There's no Windows or Linux version.

## See also

- [Design tools](../concepts/design-tools.md)
- [Paper](./paper.md)

[^imageoptim]: [ImageOptim for Mac](https://imageoptim.com/mac), checked 2026-10-24
[^packages]: Homebrew: [imageoptim](https://formulae.brew.sh/cask/imageoptim); GitHub: [ImageOptim/ImageOptim](https://github.com/ImageOptim/ImageOptim); checked 2026-10-24
