# Crossgate 1.0.18 更新日志

亲爱的玩家，Crossgate 1.0.18 版本已发布。本次更新重点改善自动战斗、BIN 资源兼容性、世界交互和界面体验。

## 主要更新内容

### 1. 自动战斗

- 完善规则战斗配置、角色规则保存和实时决策链路。
- 自动战斗设置窗口默认关闭，可从战斗指令或系统面板入口打开。
- 收紧未开放模式的行为，避免未就绪能力误启用。

### 2. BIN 资源与运行稳定性

- 发布包 BIN 资源模式调整为 `compatible`，兼容 Raw 与 CGBZ 资源树。
- 修复 CGBZ 资源管理器在 macOS 退出阶段的崩溃问题。
- 保持 macOS 与 Windows 使用一致的 NativeCore 资源读取合同。

### 3. 世界与界面体验

- 修复右键八方向转向、不可达区域就近寻路和 NPC 连续交互问题。
- 优化角色姓名板、BZ 对话框动态尺寸、宠物状态按钮和面板交互音效。
- 修复多窗口场景下散步宠物同步和部分显示状态问题。

### 4. 登录与发布配置

- 发布包继续提供完整 `config.ini` 模板和签名公告文件。
- 统一 macOS、Windows 的版本信息、NativeCore 文件布局和发布资源合同。

## 发布文件

- macOS：`Crossgate for MacOS_1.0.18.zip`
- Windows：`Crossgate for Win_1.0.18.zip`

## 构建信息

- Game commit：`ac38c784fdc53fcfd9294192e0e0d722951a0e13`
- Engine commit：`2dbe4efa17276060a022e4028dc2eee4c7e03d38`
- macOS 发布包 SHA-256：`e4e89d24b8c9943fd4ce1f66f7c139305d4d16735564ab1690f5d16f61d1dd28`
- Windows 公开发布包 SHA-256：`f9049a6c4d64d237e71418e0ff8beb0536dc826bd5115bbae64cbafaf509e2d6`
