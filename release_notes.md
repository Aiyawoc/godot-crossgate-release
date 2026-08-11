# Crossgate 1.0.19 更新日志

亲爱的玩家，Crossgate 1.0.19 版本已发布。本次更新集中改善聊天与窗口交互、世界消息、战斗切换和资源兼容性。

## 主要更新内容

### 1. 聊天与窗口体验

- 统一聊天输入焦点和快捷键路由，减少输入框切换时的误操作。
- 修复多窗口层级、玩家资料与宠物面板连接，以及图鉴详情窗口显示问题。
- 完善 NPC 对照表和图鉴信息展示。

### 2. 世界交互与消息

- 接入服务端留言板消息展示。
- 修复世界交互中错误 TLKH 对象封包，并统一 `zdr` 竖线转义处理。

### 3. 战斗与资源稳定性

- 修复战斗退场地图请求队列溢出和分辨率切换后的场景偏移。
- 改善标准 PNG 图档识别，提升资源加载兼容性。

### 4. 发布配置

- macOS、Windows 使用一致的版本信息、NativeCore 文件布局和签名公告文件。
- Windows 发布包中的 NativeCore DLL 与 exe 同级放置，便于直接启动。

## 发布文件

- macOS：`Crossgate for MacOS_1.0.19.zip`
- Windows：`Crossgate for Win_1.0.19.zip`

## 构建信息

- Game release branch：`5539e268930ac6272160f452a4eef8f3ec103b2b`
- macOS 构建基线：`a69e31e0`
- Engine commit：`2dbe4efa17276060a022e4028dc2eee4c7e03d38`
- macOS 发布包 SHA-256：`c6323919cac08589d8d8fc4a1572a73dd7d24efd351d96011ae8744c3996aa23`
- Windows 发布包 SHA-256：`3759071f3b0c247384824e0eed2d1147a72f7a7eb83d0b15f2beb4dde1973f3a`
