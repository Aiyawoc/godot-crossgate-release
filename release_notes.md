# v1.0.10 更新内容

## 发布修复
- 修复 macOS 正式包获取加密 key 时的兼容性问题，提升发布包导出稳定性
- 继续保留 NativeCore 与加密 PCK 的 macOS 发布链路，完善正式包打包结果
- Windows GitHub Actions 发布改为优先通过远端授权接口获取 PCK key，并补齐请求头兼容处理
- Windows CI 支持复用已缓存的 editor 与 template_release，减少重复引擎编译
