# 说明

## 实现功能

参考 [DangoOCR](https://github.com/PantsuDango/DangoOCR)

## 开发参考

### 安装 MSYS2

- 链接 [MSYS2](https://www.msys2.org/)

- 添加 C/C++ 开发工具链 `mingw-w64-ucrt-x86_64-toolchain`

- 环境变量 `Path` 增加路径 `[msys2 root]/mingw64/bin`

### 安装 vcpkg

- 链接 [vcpkg](https://github.com/microsoft/vcpkg)

- 添加环境变量 `VCPKG_ROOT` = `[vcpkg root]`

- 添加环境变量 `PKG_CONFIG_PATH` = `%VCPKG_ROOT%/installed/x64-windows/lib/pkgconfig`

- 环境变量 `Path` 增加路径 `%VCPKG_ROOT%`, `%VCPKG_ROOT%/installed/x64-windows/bin`

### 安装依赖

- `vcpkg install tesseract:x64-windows`

### 构建相关

- `$env:CGO_ENABLED=1; go build`

- 依赖的 [tesseract](https://github.com/tesseract-ocr/tesseract) 在运行时会读取对应的训练模型，从 [tessdata_fast](https://github.com/tesseract-ocr/tessdata_fast) 自行下载放入执行目录下的 `tessdata` 目录
