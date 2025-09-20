# OpenTrace CI Runners

Pre-built container images for building OpenTrace projects across platforms.

## Images

- `ghcr.io/opentracelab/opentracerunners/linux-builder:latest` - Ubuntu 22.04 with all dependencies
- `ghcr.io/opentracelab/opentracerunners/windows-builder:latest` - Windows Server 2022 with MSYS2
- macOS uses GitHub Actions native runners with Homebrew

## Usage

### Linux
```bash
docker run --rm -v $(pwd):/workspace ghcr.io/opentracelab/opentracerunners/linux-builder:latest \
  bash -c "meson setup build && ninja -C build"
```

### Windows
```bash
docker run --rm -v ${PWD}:C:/workspace ghcr.io/opentracelab/opentracerunners/windows-builder:latest \
  C:/msys64/usr/bin/bash.exe -l -c "meson setup build && ninja -C build"
```

### macOS (GitHub Actions)
```yaml
- name: Install dependencies
  run: brew install meson ninja pkg-config glib libusb python@3.11 qt6
```
